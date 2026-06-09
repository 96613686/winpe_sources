# VhdmpiReadVirtualDiskData(_VHD_HANDLE_CONTEXT *,_IRP *)

- ea: `0x1400cb980`
- end: `0x1400cbcfb`
- name: `?VhdmpiReadVirtualDiskData@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001a608`

## callees

- `0x14001b108`
- `0x14001f9ac`
- `0x14002269c`
- `0x140026acc`
- `0x1400278a8`
- `0x140033ac4`
- `0x14005e100`
- `0x1400b6da8`
- `0x1400b6ff8`
- `0x1400cb980`
- `0x1400e8844`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1400cbb5e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400cbb5e`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x1400cbb8a`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x1400cbb8a`
- `ntoskrnl!RtlSetBits` at `0x1400cbc5a`
- `ntoskrnl!RtlSetBits` at `0x1400cbc5a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cbb27`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cbb27`
- `ntoskrnl!RtlAreBitsSet` at `0x1400cbc85`
- `ntoskrnl!RtlAreBitsSet` at `0x1400cbc85`

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
  started = VhdmpiValidateMetadataAccessForHandle(a1, 1);
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
0x1400cb980  mov     [rsp-8+arg_8], rbx
0x1400cb985  push    rbp
0x1400cb986  push    rsi
0x1400cb987  push    rdi
0x1400cb988  push    r12
0x1400cb98a  push    r13
0x1400cb98c  push    r14
0x1400cb98e  push    r15
0x1400cb990  lea     rbp, [rsp-90h]
0x1400cb998  sub     rsp, 190h
0x1400cb99f  mov     r15, rdx
0x1400cb9a2  mov     rbx, rcx
0x1400cb9a5  xorps   xmm0, xmm0
0x1400cb9a8  lea     rcx, [rsp+1C0h+var_150]; void *
0x1400cb9ad  xor     edx, edx; Val
0x1400cb9af  mov     r8d, 120h; Size
0x1400cb9b5  movups  xmmword ptr [rsp+1C0h+BitMapHeader.SizeOfBitMap], xmm0
0x1400cb9ba  call    memset
0x1400cb9bf  mov     rdi, [rbx+38h]
0x1400cb9c3  xor     sil, sil
0x1400cb9c6  mov     [rbp+0C0h+StartingRunIndex], 0
0x1400cb9d0  mov     eax, [rdi+104h]
0x1400cb9d6  test    eax, eax
0x1400cb9d8  jz      short loc_1400CB9E4
0x1400cb9da  mov     ebx, 0C0000128h
0x1400cb9df  jmp     loc_1400CBCBA
0x1400cb9e4  cmp     [rdi+55h], sil
0x1400cb9e8  jz      short loc_1400CB9F4
0x1400cb9ea  mov     ebx, 0C0000010h
0x1400cb9ef  jmp     loc_1400CBCBA
0x1400cb9f4  mov     dl, 1; unsigned __int8
0x1400cb9f6  mov     rcx, rbx; struct _VHD_HANDLE_CONTEXT *
0x1400cb9f9  call    ?VhdmpiValidateMetadataAccessForHandle@@YAJPEAU_VHD_HANDLE_CONTEXT@@E@Z; VhdmpiValidateMetadataAccessForHandle(_VHD_HANDLE_CONTEXT *,uchar)
0x1400cb9fe  mov     ebx, eax
0x1400cba00  test    eax, eax
0x1400cba02  js      loc_1400CBCBA
0x1400cba08  mov     eax, 1
0x1400cba0d  lock xadd [rdi+120h], rax
0x1400cba16  inc     rax
0x1400cba19  cmp     rax, 1
0x1400cba1d  jg      short loc_1400CBA26
0x1400cba1f  mov     ecx, 0Eh
0x1400cba24  int     29h; Win8: RtlFailFast(ecx)
0x1400cba26  lea     rcx, [rdi+80h]
0x1400cba2d  mov     [rbp+0C0h+arg_0], dl
0x1400cba33  call    VhdmpiAcquirePassiveLockShared
0x1400cba38  mov     rcx, [r15+0B8h]
0x1400cba3f  cmp     dword ptr [rcx+10h], 10h
0x1400cba43  jb      loc_1400CBCAE
0x1400cba49  mov     r13, [r15+18h]
0x1400cba4d  xor     edx, edx
0x1400cba4f  mov     r8d, [rdi+48h]
0x1400cba53  mov     [rsp+1C0h+var_170], r13
0x1400cba58  mov     rax, [r13+0]
0x1400cba5c  div     r8
0x1400cba5f  test    rdx, rdx
0x1400cba62  jnz     loc_1400CBCAE
0x1400cba68  mov     r14d, [r13+8]
0x1400cba6c  mov     eax, r14d
0x1400cba6f  div     r8d
0x1400cba72  test    edx, edx
0x1400cba74  jnz     loc_1400CBCAE
0x1400cba7a  test    r14d, r14d
0x1400cba7d  jz      loc_1400CBCAE
0x1400cba83  mov     rdx, [r15+8]
0x1400cba87  test    rdx, rdx
0x1400cba8a  jz      loc_1400CBCAE
0x1400cba90  mov     eax, [rcx+8]
0x1400cba93  mov     esi, r14d
0x1400cba96  shr     esi, 9
0x1400cba99  mov     qword ptr [rsp+1C0h+Length], rsi
0x1400cba9e  cmp     eax, r14d
0x1400cbaa1  jb      loc_1400CBCA7
0x1400cbaa7  lea     r12d, [rsi+7]
0x1400cbaab  sub     eax, r14d
0x1400cbaae  shr     r12d, 3
0x1400cbab2  add     r12d, 3
0x1400cbab6  and     r12d, 0FFFFFFFCh
0x1400cbaba  cmp     eax, r12d
0x1400cbabd  jb      loc_1400CBCA7
0x1400cbac3  mov     rax, [rdi+90h]
0x1400cbaca  lea     rcx, [rsp+1C0h+var_150]
0x1400cbacf  mov     [rsp+1C0h+var_190], 0
0x1400cbad8  mov     r9d, 1
0x1400cbade  mov     qword ptr [rsp+1C0h+Priority], rax
0x1400cbae3  mov     r8d, r14d
0x1400cbae6  mov     [rsp+1C0h+BugCheckOnFailure], esi
0x1400cbaea  mov     [rsp+1C0h+var_168], rax
0x1400cbaef  call    VhdmpiInitializeInternalIoContextWithDataBuffer
0x1400cbaf4  mov     ebx, eax
0x1400cbaf6  test    eax, eax
0x1400cbaf8  js      loc_1400CBCB3
0x1400cbafe  mov     rcx, [r15+8]; MemoryDescriptorList
0x1400cbb02  test    byte ptr [rcx+0Ah], 5
0x1400cbb06  jz      short loc_1400CBB0E
0x1400cbb08  mov     rax, [rcx+18h]
0x1400cbb0c  jmp     short loc_1400CBB33
0x1400cbb0e  xor     r9d, r9d; RequestedAddress
0x1400cbb11  mov     [rsp+1C0h+Priority], 40000010h; Priority
0x1400cbb19  xor     edx, edx; AccessMode
0x1400cbb1b  mov     [rsp+1C0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400cbb23  lea     r8d, [r9+1]; CacheType
0x1400cbb27  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400cbb2e  nop     dword ptr [rax+rax+00h]
0x1400cbb33  mov     [rsp+1C0h+var_150], rax
0x1400cbb38  test    rax, rax
0x1400cbb3b  jnz     short loc_1400CBB47
0x1400cbb3d  mov     ebx, 0C000009Ah
0x1400cbb42  jmp     loc_1400CBCB3
0x1400cbb47  test    al, 3
0x1400cbb49  jnz     loc_1400CBCAE
0x1400cbb4f  mov     edx, [r13+8]
0x1400cbb53  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbb58  add     rdx, rax; BitMapBuffer
0x1400cbb5b  mov     r8d, esi; SizeOfBitMap
0x1400cbb5e  call    cs:__imp_RtlInitializeBitMap
0x1400cbb65  nop     dword ptr [rax+rax+00h]
0x1400cbb6a  xor     ecx, ecx
0x1400cbb6c  mov     [rbp+0C0h+StartingRunIndex], 0
0x1400cbb76  mov     edx, [rbp+0C0h+StartingRunIndex]
0x1400cbb7c  lea     r8, [rbp+0C0h+StartingRunIndex]; StartingRunIndex
0x1400cbb83  add     edx, ecx; FromIndex
0x1400cbb85  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbb8a  call    cs:__imp_RtlFindNextForwardRunClear
0x1400cbb91  nop     dword ptr [rax+rax+00h]
0x1400cbb96  mov     [rbp+0C0h+arg_18], eax
0x1400cbb9c  test    eax, eax
0x1400cbb9e  jz      loc_1400CBC79
0x1400cbba4  mov     ecx, [rbp+0C0h+StartingRunIndex]
0x1400cbbaa  mov     r13d, eax
0x1400cbbad  mov     rax, [rsp+1C0h+var_170]
0x1400cbbb2  mov     r8d, 2
0x1400cbbb8  mov     rdx, [rsp+1C0h+var_168]
0x1400cbbbd  shl     ecx, 9
0x1400cbbc0  mov     r9d, ecx
0x1400cbbc3  add     r9, [rax]
0x1400cbbc6  lea     rax, [rsp+1C0h+var_150]
0x1400cbbcb  mov     esi, ecx
0x1400cbbcd  mov     rcx, rdi
0x1400cbbd0  mov     [rsp+1C0h+var_190], rax
0x1400cbbd5  shl     r13d, 9
0x1400cbbd9  mov     [rsp+1C0h+Priority], esi
0x1400cbbdd  mov     [rsp+1C0h+BugCheckOnFailure], r13d
0x1400cbbe2  call    VhdmpiInternalStartIo
0x1400cbbe7  mov     ebx, eax
0x1400cbbe9  cmp     eax, 103h
0x1400cbbee  jnz     short loc_1400CBBFC
0x1400cbbf0  lea     rcx, [rsp+1C0h+var_150]
0x1400cbbf5  call    VhdmpiWaitForInternalIo
0x1400cbbfa  mov     ebx, eax
0x1400cbbfc  test    ebx, ebx
0x1400cbbfe  js      loc_1400CBCB3
0x1400cbc04  mov     ecx, [rbp+0C0h+arg_18]
0x1400cbc0a  add     r13d, esi
0x1400cbc0d  cmp     esi, r13d
0x1400cbc10  jnb     loc_1400CBB76
0x1400cbc16  mov     rcx, [rbp+0C0h+var_138]
0x1400cbc1a  mov     edx, esi
0x1400cbc1c  mov     r9d, esi
0x1400cbc1f  call    VhdmpiGetIoSegmentForBufferOffset
0x1400cbc24  mov     rbx, rax
0x1400cbc27  mov     ecx, [rax]
0x1400cbc29  cmp     ecx, 4
0x1400cbc2c  jz      short loc_1400CBC66
0x1400cbc2e  dec     ecx
0x1400cbc30  cmp     ecx, 2
0x1400cbc33  ja      short loc_1400CBC48
0x1400cbc35  mov     rcx, [rsp+1C0h+var_150]
0x1400cbc3a  xor     edx, edx; Val
0x1400cbc3c  mov     r8d, [rax+4]; Size
0x1400cbc40  add     rcx, r9; void *
0x1400cbc43  call    memset
0x1400cbc48  mov     r8d, [rbx+4]
0x1400cbc4c  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbc51  mov     edx, esi
0x1400cbc53  shr     r8d, 9; NumberToSet
0x1400cbc57  shr     edx, 9; StartingIndex
0x1400cbc5a  call    cs:__imp_RtlSetBits
0x1400cbc61  nop     dword ptr [rax+rax+00h]
0x1400cbc66  add     esi, [rbx+4]
0x1400cbc69  cmp     esi, r13d
0x1400cbc6c  jb      short loc_1400CBC16
0x1400cbc6e  mov     ecx, [rbp+0C0h+arg_18]
0x1400cbc74  jmp     loc_1400CBB76
0x1400cbc79  mov     r8d, [rsp+1C0h+Length]; Length
0x1400cbc7e  lea     rcx, [rsp+1C0h+BitMapHeader]; BitMapHeader
0x1400cbc83  xor     edx, edx; StartingIndex
0x1400cbc85  call    cs:__imp_RtlAreBitsSet
0x1400cbc8c  nop     dword ptr [rax+rax+00h]
0x1400cbc91  neg     al
0x1400cbc93  lea     ecx, [r12+r14]
0x1400cbc97  mov     [r15+38h], rcx
0x1400cbc9b  sbb     ebx, ebx
0x1400cbc9d  not     ebx
0x1400cbc9f  and     ebx, 80000005h
0x1400cbca5  jmp     short loc_1400CBCB3
0x1400cbca7  mov     ebx, 0C0000023h
0x1400cbcac  jmp     short loc_1400CBCB3
0x1400cbcae  mov     ebx, 0C000000Dh
0x1400cbcb3  mov     sil, [rbp+0C0h+arg_0]
0x1400cbcba  lea     rcx, [rsp+1C0h+var_150]; void *
0x1400cbcbf  call    VhdmpiCleanupInternalIoContextWithDataBuffer
0x1400cbcc4  test    sil, sil
0x1400cbcc7  jz      short loc_1400CBCDD
0x1400cbcc9  lea     rcx, [rdi+80h]
0x1400cbcd0  call    VhdmpiReleasePassiveLockShared
0x1400cbcd5  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400cbcd8  call    VhdmpiReleaseVirtualDisk
0x1400cbcdd  mov     eax, ebx
0x1400cbcdf  mov     rbx, [rsp+1C0h+arg_8]
0x1400cbce7  add     rsp, 190h
0x1400cbcee  pop     r15
0x1400cbcf0  pop     r14
0x1400cbcf2  pop     r13
0x1400cbcf4  pop     r12
0x1400cbcf6  pop     rdi
0x1400cbcf7  pop     rsi
0x1400cbcf8  pop     rbp
0x1400cbcf9  retn
```
