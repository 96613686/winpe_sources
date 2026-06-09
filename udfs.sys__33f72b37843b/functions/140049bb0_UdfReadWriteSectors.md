# UdfReadWriteSectors

- ea: `0x140049bb0`
- end: `0x140049f19`
- name: `UdfReadWriteSectors`
- size: `873`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x14000dc18`
- `0x140017c08`
- `0x14002cf5c`
- `0x14002eb9c`
- `0x140039938`
- `0x14003a274`
- `0x14003aa44`
- `0x14003b79c`
- `0x14003c2e4`
- `0x1400483a8`
- `0x1400491d0`
- `0x140049500`
- `0x14004e020`

## callees

- `0x140009014`
- `0x14000c36c`
- `0x14000ca10`
- `0x14000ca54`
- `0x1400120ec`
- `0x140049bb0`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140049e21`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140049e21`
- `ntoskrnl!ExRaiseStatus` at `0x140049edb`
- `ntoskrnl!ExRaiseStatus` at `0x140049edb`
- `ntoskrnl!IoFreeMdl` at `0x140049cb4`
- `ntoskrnl!IoFreeMdl` at `0x140049cb4`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140049c58`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140049c58`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140049c8a`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140049c8a`
- `ntoskrnl!IoFreeIrp` at `0x140049ccf`
- `ntoskrnl!IoFreeIrp` at `0x140049ccf`
- `ntoskrnl!MmUnlockPages` at `0x140049ca4`
- `ntoskrnl!MmUnlockPages` at `0x140049ca4`

## pseudocode

```c
__int64 __fastcall UdfReadWriteSectors(
        __int64 a1,
        union _LARGE_INTEGER a2,
        __int64 a3,
        char a4,
        PVOID Buffer,
        PDEVICE_OBJECT DeviceObject,
        char a7)
{
  ULONG v8; // r14d
  union _LARGE_INTEGER v9; // r10
  char v11; // di
  struct _DEVICE_OBJECT *v12; // rsi
  PVOID v13; // r15
  __int64 v14; // r8
  __int64 v15; // rcx
  union _LARGE_INTEGER *StartingOffset; // rbx
  PIRP v17; // rax
  IRP *v18; // rbx
  int v19; // eax
  struct _MDL *MdlAddress; // rcx
  int v21; // esi
  struct _MDL *Next; // rdi
  __int64 v23; // r8
  __int64 result; // rax
  __int64 v25; // r9
  int v26; // eax
  __int64 v27; // r8
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // [rsp+40h] [rbp-48h] BYREF
  __int64 Lbn; // [rsp+90h] [rbp+8h] BYREF
  union _LARGE_INTEGER v31; // [rsp+98h] [rbp+10h] BYREF

  v31 = a2;
  v29 = 0;
  v8 = a3;
  v9 = a2;
  v11 = a7;
  v12 = DeviceObject;
  v13 = Buffer;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
  {
    v25 = 89;
    if ( !a7 )
      v25 = 78;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))WPP_SF_ciDqq)(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      (union _LARGE_INTEGER)a2.QuadPart,
      a3,
      v25,
      (union _LARGE_INTEGER)a2.QuadPart,
      a3,
      Buffer,
      DeviceObject,
      v29);
    v9 = v31;
  }
  v14 = *(_QWORD *)(a1 + 16);
  if ( v14 && (*(_DWORD *)(v14 + 48) & 0x80000) != 0 )
  {
    Lbn = 0;
    if ( !FsRtlLookupLargeMcbEntry(
            *(PLARGE_MCB *)(*(_QWORD *)(v14 + 16) + 48LL),
            (unsigned int)((unsigned __int64)v9.QuadPart >> *(_DWORD *)(v14 + 72)),
            &Lbn,
            0,
            0,
            0,
            0)
      || Lbn == -1 )
    {
      v9 = v31;
    }
    else
    {
      v9.QuadPart = (unsigned int)((_DWORD)Lbn << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL));
      v31 = v9;
    }
  }
  v15 = *(_QWORD *)(a1 + 16);
  if ( !v15 )
  {
    StartingOffset = &v31;
LABEL_5:
    v17 = IoBuildAsynchronousFsdRequest((unsigned int)(v11 != 0) + 3, v12, v13, v8, StartingOffset, &UdfGarbageIosb);
    v18 = v17;
    if ( v17 )
    {
      v17->Tail.Overlay.CurrentStackLocation[-1].Flags |= 2u;
      if ( v11 )
        v17->Tail.Overlay.CurrentStackLocation[-1].Flags |= 4u;
      v19 = IoSynchronousCallDriver(v12, v17);
      MdlAddress = v18->MdlAddress;
      v21 = v19;
      if ( MdlAddress )
      {
        do
        {
          Next = MdlAddress->Next;
          MmUnlockPages(MdlAddress);
          IoFreeMdl(v18->MdlAddress);
          v18->MdlAddress = Next;
          MdlAddress = Next;
        }
        while ( Next );
      }
      IoFreeIrp(v18);
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          17,
          WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids);
      }
      if ( v21 < 0 && !a4 )
      {
        LOBYTE(v23) = 1;
        UdfRaiseStatusEx(a1, (unsigned int)v21, v23);
      }
      return (unsigned int)v21;
    }
    else
    {
      if ( !a4 )
      {
        *(_DWORD *)(a1 + 24) = -1073741670;
        ExRaiseStatus(-1073741670);
      }
      return 3221225626LL;
    }
  }
  v26 = *(_DWORD *)(v15 + 48);
  if ( (v26 & 0x2000) == 0 )
  {
    StartingOffset = &v31;
    if ( (v26 & 8) != 0 )
    {
      StartingOffset = (union _LARGE_INTEGER *)&v29;
      v28 = v9.QuadPart
          + ((unsigned __int64)(7 * ((unsigned int)((unsigned __int64)v9.QuadPart >> *(_DWORD *)(v15 + 72)) >> 5)) << *(_DWORD *)(v15 + 72));
      v29 = v28;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
      {
        WPP_SF_q(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          16,
          WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids,
          v28);
      }
    }
    goto LABEL_5;
  }
  result = UdfRmwReadWriteSectors(a1, v11, v11 != 0 ? 3 : 0);
  if ( (int)result < 0 && !a4 )
  {
    LOBYTE(v27) = 1;
    UdfRaiseStatusEx(a1, (unsigned int)result, v27);
  }
  return result;
}

```

## disassembly

```asm
0x140049bb0  mov     qword ptr [rsp+arg_8], rdx
0x140049bb5  push    rbp
0x140049bb6  push    rsi
0x140049bb7  push    rdi
0x140049bb8  push    r12
0x140049bba  push    r13
0x140049bbc  push    r14
0x140049bbe  push    r15
0x140049bc0  sub     rsp, 50h
0x140049bc4  movzx   r12d, r9b
0x140049bc8  mov     [rsp+88h+var_48], 0
0x140049bd1  mov     r14d, r8d
0x140049bd4  mov     r10, rdx
0x140049bd7  mov     rbp, rcx
0x140049bda  mov     rcx, cs:WPP_GLOBAL_Control
0x140049be1  lea     r13, WPP_GLOBAL_Control
0x140049be8  movzx   edi, [rsp+88h+arg_30]
0x140049bf0  mov     rsi, [rsp+88h+DeviceObject]
0x140049bf8  mov     r15, [rsp+88h+Buffer]
0x140049c00  cmp     rcx, r13
0x140049c03  jnz     loc_140049D0A
0x140049c09  mov     r8, [rbp+10h]
0x140049c0d  test    r8, r8
0x140049c10  jnz     loc_140049DCF
0x140049c16  mov     rcx, [rbp+10h]
0x140049c1a  mov     [rsp+88h+arg_10], rbx
0x140049c22  test    rcx, rcx
0x140049c25  jnz     loc_140049D75
0x140049c2b  lea     rbx, [rsp+88h+arg_8]
0x140049c33  xor     ecx, ecx
0x140049c35  lea     rax, UdfGarbageIosb
0x140049c3c  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x140049c41  test    dil, dil
0x140049c44  mov     r9d, r14d; Length
0x140049c47  mov     [rsp+88h+StartingOffset], rbx; StartingOffset
0x140049c4c  setnz   cl
0x140049c4f  mov     r8, r15; Buffer
0x140049c52  add     ecx, 3; MajorFunction
0x140049c55  mov     rdx, rsi; DeviceObject
0x140049c58  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x140049c5f  nop     dword ptr [rax+rax+00h]
0x140049c64  mov     rbx, rax
0x140049c67  test    rax, rax
0x140049c6a  jz      loc_140049ECA
0x140049c70  mov     rax, [rax+0B8h]
0x140049c77  or      byte ptr [rax-46h], 2
0x140049c7b  test    dil, dil
0x140049c7e  jnz     loc_140049EF2
0x140049c84  mov     rdx, rbx
0x140049c87  mov     rcx, rsi
0x140049c8a  call    cs:__imp_IoSynchronousCallDriver
0x140049c91  nop     dword ptr [rax+rax+00h]
0x140049c96  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140049c9a  mov     esi, eax
0x140049c9c  test    rcx, rcx
0x140049c9f  jz      short loc_140049CCC
0x140049ca1  mov     rdi, [rcx]
0x140049ca4  call    cs:__imp_MmUnlockPages
0x140049cab  nop     dword ptr [rax+rax+00h]
0x140049cb0  mov     rcx, [rbx+8]; Mdl
0x140049cb4  call    cs:__imp_IoFreeMdl
0x140049cbb  nop     dword ptr [rax+rax+00h]
0x140049cc0  mov     [rbx+8], rdi
0x140049cc4  mov     rcx, rdi
0x140049cc7  test    rdi, rdi
0x140049cca  jnz     short loc_140049CA1
0x140049ccc  mov     rcx, rbx; Irp
0x140049ccf  call    cs:__imp_IoFreeIrp
0x140049cd6  nop     dword ptr [rax+rax+00h]
0x140049cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ce2  cmp     rcx, r13
0x140049ce5  jnz     short loc_140049D51
0x140049ce7  test    esi, esi
0x140049ce9  js      loc_140049F02
0x140049cef  mov     eax, esi
0x140049cf1  mov     rbx, [rsp+88h+arg_10]
0x140049cf9  add     rsp, 50h
0x140049cfd  pop     r15
0x140049cff  pop     r14
0x140049d01  pop     r13
0x140049d03  pop     r12
0x140049d05  pop     rdi
0x140049d06  pop     rsi
0x140049d07  pop     rbp
0x140049d08  retn
0x140049d0a  mov     eax, [rcx+2Ch]
0x140049d0d  test    al, 40h
0x140049d0f  jz      loc_140049C09
0x140049d15  mov     rcx, [rcx+18h]
0x140049d19  test    dil, dil
0x140049d1c  mov     [rsp+88h+var_50], rsi
0x140049d21  mov     eax, 4Eh ; 'N'
0x140049d26  mov     r9d, 59h ; 'Y'
0x140049d2c  mov     [rsp+88h+Index], r15
0x140049d31  cmovz   r9d, eax
0x140049d35  mov     dword ptr [rsp+88h+IoStatusBlock], r14d
0x140049d3a  mov     [rsp+88h+StartingOffset], rdx
0x140049d3f  call    WPP_SF_ciDqq
0x140049d44  mov     r10, qword ptr [rsp+88h+arg_8]
0x140049d4c  jmp     loc_140049C09
0x140049d51  mov     eax, [rcx+2Ch]
0x140049d54  test    al, 40h
0x140049d56  jz      short loc_140049CE7
0x140049d58  mov     rcx, [rcx+18h]
0x140049d5c  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140049d63  mov     edx, 11h
0x140049d68  mov     r9d, esi
0x140049d6b  call    WPP_SF_d
0x140049d70  jmp     loc_140049CE7
0x140049d75  mov     eax, [rcx+30h]
0x140049d78  bt      eax, 0Dh
0x140049d7c  jnb     loc_140049E65
0x140049d82  mov     ecx, [rcx+48h]
0x140049d85  movzx   eax, dil
0x140049d89  neg     al
0x140049d8b  mov     r9, r15
0x140049d8e  sbb     edx, edx
0x140049d90  shr     r14d, cl
0x140049d93  and     edx, 3
0x140049d96  shr     r10, cl
0x140049d99  mov     dword ptr [rsp+88h+IoStatusBlock], edx
0x140049d9d  mov     r8d, r14d
0x140049da0  mov     edx, r10d
0x140049da3  mov     byte ptr [rsp+88h+StartingOffset], dil
0x140049da8  mov     rcx, rbp
0x140049dab  call    UdfRmwReadWriteSectors
0x140049db0  test    eax, eax
0x140049db2  jns     loc_140049CF1
0x140049db8  test    r12b, r12b
0x140049dbb  jnz     loc_140049CF1
0x140049dc1  mov     r8b, 1
0x140049dc4  mov     edx, eax
0x140049dc6  mov     rcx, rbp
0x140049dc9  call    UdfRaiseStatusEx
0x140049dcf  test    dword ptr [r8+30h], 80000h
0x140049dd7  jz      loc_140049C16
0x140049ddd  mov     [rsp+88h+Lbn], 0
0x140049de9  xor     r9d, r9d; SectorCountFromLbn
0x140049dec  mov     ecx, [r8+48h]
0x140049df0  shr     r10, cl
0x140049df3  mov     rcx, [r8+10h]
0x140049df7  lea     r8, [rsp+88h+Lbn]; Lbn
0x140049dff  mov     [rsp+88h+Index], 0; Index
0x140049e08  mov     edx, r10d; Vbn
0x140049e0b  mov     [rsp+88h+IoStatusBlock], 0; SectorCountFromStartingLbn
0x140049e14  mov     rcx, [rcx+30h]; Mcb
0x140049e18  mov     [rsp+88h+StartingOffset], 0; StartingLbn
0x140049e21  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140049e28  nop     dword ptr [rax+rax+00h]
0x140049e2d  test    al, al
0x140049e2f  jz      short loc_140049E58
0x140049e31  mov     rax, [rsp+88h+Lbn]
0x140049e39  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140049e3d  jz      short loc_140049E58
0x140049e3f  mov     rcx, [rbp+10h]
0x140049e43  mov     ecx, [rcx+48h]
0x140049e46  shl     eax, cl
0x140049e48  mov     r10d, eax
0x140049e4b  mov     qword ptr [rsp+88h+arg_8], r10
0x140049e53  jmp     loc_140049C16
0x140049e58  mov     r10, qword ptr [rsp+88h+arg_8]
0x140049e60  jmp     loc_140049C16
0x140049e65  lea     rbx, [rsp+88h+arg_8]
0x140049e6d  test    al, 8
0x140049e6f  jz      loc_140049C33
0x140049e75  mov     ecx, [rcx+48h]
0x140049e78  lea     rbx, [rsp+88h+var_48]
0x140049e7d  mov     rax, r10
0x140049e80  shr     rax, cl
0x140049e83  shr     eax, 5
0x140049e86  imul    r9d, eax, 7
0x140049e8a  shl     r9, cl
0x140049e8d  add     r9, r10
0x140049e90  mov     [rsp+88h+var_48], r9
0x140049e95  mov     rcx, cs:WPP_GLOBAL_Control
0x140049e9c  cmp     rcx, r13
0x140049e9f  jz      loc_140049C33
0x140049ea5  mov     eax, [rcx+2Ch]
0x140049ea8  test    al, 40h
0x140049eaa  jz      loc_140049C33
0x140049eb0  mov     rcx, [rcx+18h]
0x140049eb4  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140049ebb  mov     edx, 10h
0x140049ec0  call    WPP_SF_q
0x140049ec5  jmp     loc_140049C33
0x140049eca  test    r12b, r12b
0x140049ecd  jnz     short loc_140049EE8
0x140049ecf  mov     ecx, 0C000009Ah; Status
0x140049ed4  mov     dword ptr [rbp+18h], 0C000009Ah
0x140049edb  call    cs:__imp_ExRaiseStatus
0x140049ee8  mov     eax, 0C000009Ah
0x140049eed  jmp     loc_140049CF1
0x140049ef2  mov     rax, [rbx+0B8h]
0x140049ef9  or      byte ptr [rax-46h], 4
0x140049efd  jmp     loc_140049C84
0x140049f02  test    r12b, r12b
0x140049f05  jnz     loc_140049CEF
0x140049f0b  mov     r8b, 1
0x140049f0e  mov     edx, esi
0x140049f10  mov     rcx, rbp
0x140049f13  call    UdfRaiseStatusEx
```
