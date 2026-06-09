# VhdmpiReadVirtualDiskData(_VHD_HANDLE_CONTEXT *,_IRP *)

- ea: `0x1400cb990`
- end: `0x1400cbd0b`
- name: `?VhdmpiReadVirtualDiskData@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001a1e8`

## callees

- `0x14001ace8`
- `0x14001f58c`
- `0x14002227c`
- `0x1400266ac`
- `0x140027388`
- `0x140033604`
- `0x14005dd00`
- `0x1400b6dc0`
- `0x1400b7010`
- `0x1400cb990`
- `0x1400e88b4`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1400cbb6e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400cbb6e`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x1400cbb9a`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x1400cbb9a`
- `ntoskrnl!RtlSetBits` at `0x1400cbc6a`
- `ntoskrnl!RtlSetBits` at `0x1400cbc6a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cbb37`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cbb37`
- `ntoskrnl!RtlAreBitsSet` at `0x1400cbc95`
- `ntoskrnl!RtlAreBitsSet` at `0x1400cbc95`

## pseudocode

```c
__int64 __fastcall VhdmpiReadVirtualDiskData(struct _VHD_HANDLE_CONTEXT *a1, struct _IRP *a2)
{
  __int64 v4; // rdi
  char v5; // si
  signed int started; // ebx
  char v7; // dl
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IRP *MasterIrp; // r13
  unsigned __int64 v10; // r8
  ULONG MdlAddress; // r14d
  PMDL v12; // rdx
  ULONG v13; // eax
  ULONG v14; // esi
  unsigned int v15; // r12d
  PMDL v16; // rcx
  char *MappedSystemVa; // rax
  int v18; // ecx
  ULONG NextForwardRunClear; // eax
  ULONG v20; // esi
  ULONG v21; // r13d
  __int64 v22; // r8
  ULONG v23; // r13d
  _DWORD *IoSegmentForBufferOffset; // rax
  __int64 v25; // r9
  _DWORD *v26; // rbx
  BOOLEAN v27; // al
  struct _RTL_BITMAP BitMapHeader; // [rsp+40h] [rbp-C0h] BYREF
  struct _IRP *v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  ULONG Length[4]; // [rsp+60h] [rbp-A0h]
  _QWORD v33[42]; // [rsp+70h] [rbp-90h] BYREF
  char v34; // [rsp+1D0h] [rbp+D0h]
  ULONG StartingRunIndex; // [rsp+1E0h] [rbp+E0h] BYREF
  ULONG v36; // [rsp+1E8h] [rbp+E8h]

  BitMapHeader = 0;
  memset(v33, 0, 0x120u);
  v4 = *((_QWORD *)a1 + 7);
  v5 = 0;
  StartingRunIndex = 0;
  if ( *(_DWORD *)(v4 + 260) )
  {
    started = -1073741528;
    goto LABEL_38;
  }
  if ( *(_BYTE *)(v4 + 85) )
  {
    started = -1073741808;
    goto LABEL_38;
  }
  started = VhdmpiValidateMetadataAccessForHandle(a1, 1u);
  if ( started >= 0 )
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 288)) <= 1 )
      __fastfail(0xEu);
    v34 = v7;
    VhdmpiAcquirePassiveLockShared(v4 + 128);
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->Parameters.Create.Options >= 0x10 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      v10 = *(unsigned int *)(v4 + 72);
      v30 = MasterIrp;
      if ( !(*(_QWORD *)&MasterIrp->Type % v10) )
      {
        MdlAddress = (ULONG)MasterIrp->MdlAddress;
        if ( !(MdlAddress % (unsigned int)v10) )
        {
          if ( MdlAddress )
          {
            v12 = a2->MdlAddress;
            if ( v12 )
            {
              v13 = CurrentStackLocation->Parameters.Read.Length;
              v14 = MdlAddress >> 9;
              *(_QWORD *)Length = MdlAddress >> 9;
              if ( v13 < MdlAddress || (v15 = (((v14 + 7) >> 3) + 3) & 0xFFFFFFFC, v13 - MdlAddress < v15) )
              {
                started = -1073741789;
                goto LABEL_37;
              }
              v31 = *(_QWORD *)(v4 + 144);
              started = VhdmpiInitializeInternalIoContextWithDataBuffer(
                          v33,
                          v12,
                          MdlAddress,
                          1,
                          MdlAddress >> 9,
                          v31,
                          0);
              if ( started < 0 )
              {
LABEL_37:
                v5 = v34;
                goto LABEL_38;
              }
              v16 = a2->MdlAddress;
              if ( (v16->MdlFlags & 5) != 0 )
                MappedSystemVa = (char *)v16->MappedSystemVa;
              else
                MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v16, 0, MmCached, 0, 0, 0x40000010u);
              v33[0] = MappedSystemVa;
              if ( !MappedSystemVa )
              {
                started = -1073741670;
                goto LABEL_37;
              }
              if ( ((unsigned __int8)MappedSystemVa & 3) == 0 )
              {
                RtlInitializeBitMap(&BitMapHeader, (PULONG)&MappedSystemVa[LODWORD(MasterIrp->MdlAddress)], v14);
                v18 = 0;
                StartingRunIndex = 0;
                while ( 1 )
                {
                  NextForwardRunClear = RtlFindNextForwardRunClear(
                                          &BitMapHeader,
                                          v18 + StartingRunIndex,
                                          &StartingRunIndex);
                  v36 = NextForwardRunClear;
                  if ( !NextForwardRunClear )
                    break;
                  v20 = StartingRunIndex << 9;
                  v21 = NextForwardRunClear << 9;
                  started = VhdmpiInternalStartIo(
                              v4,
                              v31,
                              2,
                              *(_DWORD *)&v30->Type + (StartingRunIndex << 9),
                              NextForwardRunClear << 9,
                              StartingRunIndex << 9,
                              (__int64)v33);
                  if ( started == 259 )
                    started = VhdmpiWaitForInternalIo(v33);
                  if ( started < 0 )
                    goto LABEL_37;
                  v18 = v36;
                  v23 = v20 + v21;
                  if ( v20 < v23 )
                  {
                    do
                    {
                      IoSegmentForBufferOffset = (_DWORD *)VhdmpiGetIoSegmentForBufferOffset(v33[3], v20, v22, v20);
                      v26 = IoSegmentForBufferOffset;
                      if ( *IoSegmentForBufferOffset != 4 )
                      {
                        if ( (unsigned int)(*IoSegmentForBufferOffset - 1) <= 2 )
                          memset((void *)(v25 + v33[0]), 0, (unsigned int)IoSegmentForBufferOffset[1]);
                        RtlSetBits(&BitMapHeader, v20 >> 9, v26[1] >> 9);
                      }
                      v20 += v26[1];
                    }
                    while ( v20 < v23 );
                    v18 = v36;
                  }
                }
                v27 = RtlAreBitsSet(&BitMapHeader, 0, Length[0]);
                a2->IoStatus.Information = v15 + MdlAddress;
                started = v27 == 0 ? 0x80000005 : 0;
                goto LABEL_37;
              }
            }
          }
        }
      }
    }
    started = -1073741811;
    goto LABEL_37;
  }
LABEL_38:
  VhdmpiCleanupInternalIoContextWithDataBuffer(v33);
  if ( v5 )
  {
    VhdmpiReleasePassiveLockShared(v4 + 128);
    VhdmpiReleaseVirtualDisk((struct _VHD_VIRTUAL_DISK *)v4);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400cb990  mov     [rsp-8+arg_8], rbx
0x1400cb995  push    rbp
0x1400cb996  push    rsi
0x1400cb997  push    rdi
0x1400cb998  push    r12
0x1400cb99a  push    r13
0x1400cb99c  push    r14
0x1400cb99e  push    r15
0x1400cb9a0  lea     rbp, [rsp-90h]
0x1400cb9a8  sub     rsp, 190h
0x1400cb9af  mov     r15, rdx
0x1400cb9b2  mov     rbx, rcx
0x1400cb9b5  xorps   xmm0, xmm0
0x1400cb9b8  lea     rcx, [rsp+1C0h+var_150]; void *
0x1400cb9bd  xor     edx, edx; Val
0x1400cb9bf  mov     r8d, 120h; Size
0x1400cb9c5  movups  xmmword ptr [rsp+1C0h+BitMapHeader.SizeOfBitMap], xmm0
0x1400cb9ca  call    memset
0x1400cb9cf  mov     rdi, [rbx+38h]
0x1400cb9d3  xor     sil, sil
0x1400cb9d6  mov     [rbp+0C0h+StartingRunIndex], 0
0x1400cb9e0  mov     eax, [rdi+104h]
0x1400cb9e6  test    eax, eax
0x1400cb9e8  jz      short loc_1400CB9F4
0x1400cb9ea  mov     ebx, 0C0000128h
0x1400cb9ef  jmp     loc_1400CBCCA
0x1400cb9f4  cmp     [rdi+55h], sil
0x1400cb9f8  jz      short loc_1400CBA04
0x1400cb9fa  mov     ebx, 0C0000010h
0x1400cb9ff  jmp     loc_1400CBCCA
0x1400cba04  mov     dl, 1; unsigned __int8
0x1400cba06  mov     rcx, rbx; struct _VHD_HANDLE_CONTEXT *
0x1400cba09  call    ?VhdmpiValidateMetadataAccessForHandle@@YAJPEAU_VHD_HANDLE_CONTEXT@@E@Z; VhdmpiValidateMetadataAccessForHandle(_VHD_HANDLE_CONTEXT *,uchar)
0x1400cba0e  mov     ebx, eax
0x1400cba10  test    eax, eax
0x1400cba12  js      loc_1400CBCCA
0x1400cba18  mov     eax, 1
0x1400cba1d  lock xadd [rdi+120h], rax
0x1400cba26  inc     rax
0x1400cba29  cmp     rax, 1
0x1400cba2d  jg      short loc_1400CBA36
0x1400cba2f  mov     ecx, 0Eh
0x1400cba34  int     29h; Win8: RtlFailFast(ecx)
0x1400cba36  lea     rcx, [rdi+80h]
0x1400cba3d  mov     [rbp+0C0h+arg_0], dl
0x1400cba43  call    VhdmpiAcquirePassiveLockShared
0x1400cba48  mov     rcx, [r15+0B8h]
0x1400cba4f  cmp     dword ptr [rcx+10h], 10h
0x1400cba53  jb      loc_1400CBCBE
0x1400cba59  mov     r13, [r15+18h]
0x1400cba5d  xor     edx, edx
0x1400cba5f  mov     r8d, [rdi+48h]
0x1400cba63  mov     [rsp+1C0h+var_170], r13
0x1400cba68  mov     rax, [r13+0]
0x1400cba6c  div     r8
0x1400cba6f  test    rdx, rdx
0x1400cba72  jnz     loc_1400CBCBE
0x1400cba78  mov     r14d, [r13+8]
0x1400cba7c  mov     eax, r14d
0x1400cba7f  div     r8d
0x1400cba82  test    edx, edx
0x1400cba84  jnz     loc_1400CBCBE
0x1400cba8a  test    r14d, r14d
0x1400cba8d  jz      loc_1400CBCBE
0x1400cba93  mov     rdx, [r15+8]
0x1400cba97  test    rdx, rdx
0x1400cba9a  jz      loc_1400CBCBE
0x1400cbaa0  mov     eax, [rcx+8]
0x1400cbaa3  mov     esi, r14d
0x1400cbaa6  shr     esi, 9
0x1400cbaa9  mov     qword ptr [rsp+1C0h+Length], rsi
0x1400cbaae  cmp     eax, r14d
0x1400cbab1  jb      loc_1400CBCB7
0x1400cbab7  lea     r12d, [rsi+7]
0x1400cbabb  sub     eax, r14d
0x1400cbabe  shr     r12d, 3
0x1400cbac2  add     r12d, 3
0x1400cbac6  and     r12d, 0FFFFFFFCh
0x1400cbaca  cmp     eax, r12d
0x1400cbacd  jb      loc_1400CBCB7
0x1400cbad3  mov     rax, [rdi+90h]
0x1400cbada  lea     rcx, [rsp+1C0h+var_150]
0x1400cbadf  mov     [rsp+1C0h+var_190], 0
0x1400cbae8  mov     r9d, 1
0x1400cbaee  mov     qword ptr [rsp+1C0h+Priority], rax
0x1400cbaf3  mov     r8d, r14d
0x1400cbaf6  mov     [rsp+1C0h+BugCheckOnFailure], esi
0x1400cbafa  mov     [rsp+1C0h+var_168], rax
0x1400cbaff  call    VhdmpiInitializeInternalIoContextWithDataBuffer
0x1400cbb04  mov     ebx, eax
0x1400cbb06  test    eax, eax
0x1400cbb08  js      loc_1400CBCC3
0x1400cbb0e  mov     rcx, [r15+8]; MemoryDescriptorList
0x1400cbb12  test    byte ptr [rcx+0Ah], 5
0x1400cbb16  jz      short loc_1400CBB1E
0x1400cbb18  mov     rax, [rcx+18h]
0x1400cbb1c  jmp     short loc_1400CBB43
0x1400cbb1e  xor     r9d, r9d; RequestedAddress
0x1400cbb21  mov     [rsp+1C0h+Priority], 40000010h; Priority
0x1400cbb29  xor     edx, edx; AccessMode
0x1400cbb2b  mov     [rsp+1C0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400cbb33  lea     r8d, [r9+1]; CacheType
0x1400cbb37  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400cbb3e  nop     dword ptr [rax+rax+00h]
0x1400cbb43  mov     [rsp+1C0h+var_150], rax
0x1400cbb48  test    rax, rax
0x1400cbb4b  jnz     short loc_1400CBB57
0x1400cbb4d  mov     ebx, 0C000009Ah
0x1400cbb52  jmp     loc_1400CBCC3
0x1400cbb57  test    al, 3
0x1400cbb59  jnz     loc_1400CBCBE
0x1400cbb5f  mov     edx, [r13+8]
0x1400cbb63  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbb68  add     rdx, rax; BitMapBuffer
0x1400cbb6b  mov     r8d, esi; SizeOfBitMap
0x1400cbb6e  call    cs:__imp_RtlInitializeBitMap
0x1400cbb75  nop     dword ptr [rax+rax+00h]
0x1400cbb7a  xor     ecx, ecx
0x1400cbb7c  mov     [rbp+0C0h+StartingRunIndex], 0
0x1400cbb86  mov     edx, [rbp+0C0h+StartingRunIndex]
0x1400cbb8c  lea     r8, [rbp+0C0h+StartingRunIndex]; StartingRunIndex
0x1400cbb93  add     edx, ecx; FromIndex
0x1400cbb95  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbb9a  call    cs:__imp_RtlFindNextForwardRunClear
0x1400cbba1  nop     dword ptr [rax+rax+00h]
0x1400cbba6  mov     [rbp+0C0h+arg_18], eax
0x1400cbbac  test    eax, eax
0x1400cbbae  jz      loc_1400CBC89
0x1400cbbb4  mov     ecx, [rbp+0C0h+StartingRunIndex]
0x1400cbbba  mov     r13d, eax
0x1400cbbbd  mov     rax, [rsp+1C0h+var_170]
0x1400cbbc2  mov     r8d, 2
0x1400cbbc8  mov     rdx, [rsp+1C0h+var_168]
0x1400cbbcd  shl     ecx, 9
0x1400cbbd0  mov     r9d, ecx
0x1400cbbd3  add     r9, [rax]
0x1400cbbd6  lea     rax, [rsp+1C0h+var_150]
0x1400cbbdb  mov     esi, ecx
0x1400cbbdd  mov     rcx, rdi
0x1400cbbe0  mov     [rsp+1C0h+var_190], rax
0x1400cbbe5  shl     r13d, 9
0x1400cbbe9  mov     [rsp+1C0h+Priority], esi
0x1400cbbed  mov     [rsp+1C0h+BugCheckOnFailure], r13d
0x1400cbbf2  call    VhdmpiInternalStartIo
0x1400cbbf7  mov     ebx, eax
0x1400cbbf9  cmp     eax, 103h
0x1400cbbfe  jnz     short loc_1400CBC0C
0x1400cbc00  lea     rcx, [rsp+1C0h+var_150]
0x1400cbc05  call    VhdmpiWaitForInternalIo
0x1400cbc0a  mov     ebx, eax
0x1400cbc0c  test    ebx, ebx
0x1400cbc0e  js      loc_1400CBCC3
0x1400cbc14  mov     ecx, [rbp+0C0h+arg_18]
0x1400cbc1a  add     r13d, esi
0x1400cbc1d  cmp     esi, r13d
0x1400cbc20  jnb     loc_1400CBB86
0x1400cbc26  mov     rcx, [rbp+0C0h+var_138]
0x1400cbc2a  mov     edx, esi
0x1400cbc2c  mov     r9d, esi
0x1400cbc2f  call    VhdmpiGetIoSegmentForBufferOffset
0x1400cbc34  mov     rbx, rax
0x1400cbc37  mov     ecx, [rax]
0x1400cbc39  cmp     ecx, 4
0x1400cbc3c  jz      short loc_1400CBC76
0x1400cbc3e  dec     ecx
0x1400cbc40  cmp     ecx, 2
0x1400cbc43  ja      short loc_1400CBC58
0x1400cbc45  mov     rcx, [rsp+1C0h+var_150]
0x1400cbc4a  xor     edx, edx; Val
0x1400cbc4c  mov     r8d, [rax+4]; Size
0x1400cbc50  add     rcx, r9; void *
0x1400cbc53  call    memset
0x1400cbc58  mov     r8d, [rbx+4]
0x1400cbc5c  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbc61  mov     edx, esi
0x1400cbc63  shr     r8d, 9; NumberToSet
0x1400cbc67  shr     edx, 9; StartingIndex
0x1400cbc6a  call    cs:__imp_RtlSetBits
0x1400cbc71  nop     dword ptr [rax+rax+00h]
0x1400cbc76  add     esi, [rbx+4]
0x1400cbc79  cmp     esi, r13d
0x1400cbc7c  jb      short loc_1400CBC26
0x1400cbc7e  mov     ecx, [rbp+0C0h+arg_18]
0x1400cbc84  jmp     loc_1400CBB86
0x1400cbc89  mov     r8d, [rsp+1C0h+Length]; Length
0x1400cbc8e  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbc93  xor     edx, edx; StartingIndex
0x1400cbc95  call    cs:__imp_RtlAreBitsSet
0x1400cbc9c  nop     dword ptr [rax+rax+00h]
0x1400cbca1  neg     al
0x1400cbca3  lea     ecx, [r12+r14]
0x1400cbca7  mov     [r15+38h], rcx
0x1400cbcab  sbb     ebx, ebx
0x1400cbcad  not     ebx
0x1400cbcaf  and     ebx, 80000005h
0x1400cbcb5  jmp     short loc_1400CBCC3
0x1400cbcb7  mov     ebx, 0C0000023h
0x1400cbcbc  jmp     short loc_1400CBCC3
0x1400cbcbe  mov     ebx, 0C000000Dh
0x1400cbcc3  mov     sil, [rbp+0C0h+arg_0]
0x1400cbcca  lea     rcx, [rsp+1C0h+var_150]; void *
0x1400cbccf  call    VhdmpiCleanupInternalIoContextWithDataBuffer
0x1400cbcd4  test    sil, sil
0x1400cbcd7  jz      short loc_1400CBCED
0x1400cbcd9  lea     rcx, [rdi+80h]
0x1400cbce0  call    VhdmpiReleasePassiveLockShared
0x1400cbce5  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400cbce8  call    VhdmpiReleaseVirtualDisk
0x1400cbced  mov     eax, ebx
0x1400cbcef  mov     rbx, [rsp+1C0h+arg_8]
0x1400cbcf7  add     rsp, 190h
0x1400cbcfe  pop     r15
0x1400cbd00  pop     r14
0x1400cbd02  pop     r13
0x1400cbd04  pop     r12
0x1400cbd06  pop     rdi
0x1400cbd07  pop     rsi
0x1400cbd08  pop     rbp
0x1400cbd09  retn
```
