# VhdmpiExtractRawScsiUserBuffer(_VHD_RAW_SCSI *)

- ea: `0x140046668`
- end: `0x1400468a8`
- name: `?VhdmpiExtractRawScsiUserBuffer@@YAJPEAU_VHD_RAW_SCSI@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(struct _VHD_RAW_SCSI *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140047608`

## callees

- `0x140046668`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140046881`
- `ntoskrnl!IoFreeMdl` at `0x140046881`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140046827`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140046827`
- `ntoskrnl!IoAllocateMdl` at `0x140046715`
- `ntoskrnl!IoAllocateMdl` at `0x140046715`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400467af`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400467af`
- `ntoskrnl!MmUnlockPages` at `0x140046872`
- `ntoskrnl!MmUnlockPages` at `0x140046872`

## pseudocode

```c
__int64 __fastcall VhdmpiExtractRawScsiUserBuffer(struct _VHD_RAW_SCSI *a1)
{
  __int64 v2; // r13
  ULONG v3; // edx
  unsigned int v4; // ebx
  char v5; // r14
  unsigned int v6; // ebx
  LOCK_OPERATION v7; // esi
  __int64 v8; // r15
  PMDL Mdl; // rdi
  bool v10; // zf
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  PVOID v15; // rax

  v2 = *((_QWORD *)a1 + 13);
  v3 = *(_DWORD *)(v2 + 12);
  if ( !v3 )
    return 0;
  v5 = 0;
  v6 = *(unsigned __int8 *)(v2 + 24);
  if ( v6 > 0x5A )
  {
    if ( v6 > 0x89 )
    {
      if ( v6 != 138 && v6 != 147 )
      {
        if ( v6 == 158 || v6 == 168 )
          goto LABEL_12;
        if ( v6 != 170 )
          goto LABEL_33;
      }
      goto LABEL_17;
    }
    if ( v6 == 137 )
      goto LABEL_17;
    if ( v6 != 94 )
    {
      if ( v6 != 95 && v6 != 131 )
      {
        if ( v6 == 132 || v6 == 136 )
          goto LABEL_12;
        goto LABEL_33;
      }
      goto LABEL_17;
    }
LABEL_12:
    v7 = IoWriteAccess;
    goto LABEL_18;
  }
  if ( v6 == 90 )
    goto LABEL_12;
  if ( v6 > 0x1D )
  {
    if ( v6 == 37 || v6 == 40 )
      goto LABEL_12;
    if ( v6 != 42 && v6 - 65 > 1 )
      goto LABEL_33;
LABEL_17:
    v7 = IoReadAccess;
LABEL_18:
    v8 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL);
    Mdl = IoAllocateMdl(*(PVOID *)(v2 + 16), v3, 0, 0, 0);
    if ( !Mdl )
    {
LABEL_19:
      v4 = -1073741670;
      goto LABEL_52;
    }
    MmProbeAndLockPages(Mdl, *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL) + 64LL), v7);
    v5 = 1;
    if ( v6 > 0x88 )
    {
      v11 = v6 - 137;
      if ( !v11 )
        goto LABEL_51;
      v12 = v11 - 1;
      if ( !v12 )
        goto LABEL_51;
      v13 = v12 - 9;
      if ( !v13 )
        goto LABEL_51;
      v14 = v13 - 21;
      if ( !v14 )
        goto LABEL_51;
      v10 = v14 == 2;
    }
    else
    {
      if ( v6 == 136 || v6 == 8 || v6 == 10 || v6 == 40 || v6 == 42 )
        goto LABEL_51;
      v10 = v6 == 65;
    }
    if ( !v10 )
    {
      v15 = (Mdl->MdlFlags & 5) != 0
          ? Mdl->MappedSystemVa
          : MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000010u);
      *(_QWORD *)(v8 + 24) = v15;
      if ( !v15 )
        goto LABEL_19;
    }
LABEL_51:
    *(_DWORD *)(v8 + 16) = *(_DWORD *)(v2 + 12);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 72LL) = Mdl;
    return 0;
  }
  switch ( v6 )
  {
    case 0x1Du:
      goto LABEL_17;
    case 3u:
    case 8u:
      goto LABEL_12;
    case 0xAu:
      goto LABEL_17;
    case 0x12u:
    case 0x1Au:
      goto LABEL_12;
  }
LABEL_33:
  Mdl = 0;
  v4 = -1073741637;
LABEL_52:
  if ( Mdl )
  {
    if ( v5 )
      MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
  }
  return v4;
}

```

## disassembly

```asm
0x140046668  mov     [rsp+arg_10], rbx
0x14004666d  mov     [rsp+arg_18], rsi
0x140046672  push    rdi
0x140046673  push    r12
0x140046675  push    r13
0x140046677  push    r14
0x140046679  push    r15
0x14004667b  sub     rsp, 30h
0x14004667f  mov     r12, rcx
0x140046682  mov     r13, [rcx+68h]
0x140046686  mov     edx, [r13+0Ch]; Length
0x14004668a  test    edx, edx
0x14004668c  jnz     short loc_140046695
0x14004668e  xor     ebx, ebx
0x140046690  jmp     loc_14004688D
0x140046695  xor     r14b, r14b
0x140046698  mov     [rsp+58h+arg_0], r14b
0x14004669d  movzx   ebx, byte ptr [r13+18h]
0x1400466a2  cmp     ebx, 5Ah ; 'Z'
0x1400466a5  ja      loc_140046738
0x1400466ab  jz      short loc_1400466D1
0x1400466ad  cmp     ebx, 1Dh
0x1400466b0  ja      short loc_1400466D8
0x1400466b2  jz      short loc_1400466F7
0x1400466b4  cmp     ebx, 3
0x1400466b7  jz      short loc_1400466D1
0x1400466b9  cmp     ebx, 8
0x1400466bc  jz      short loc_1400466D1
0x1400466be  cmp     ebx, 0Ah
0x1400466c1  jz      short loc_1400466F7
0x1400466c3  cmp     ebx, 12h
0x1400466c6  jz      short loc_1400466D1
0x1400466c8  cmp     ebx, 1Ah
0x1400466cb  jnz     loc_140046791
0x1400466d1  mov     esi, 1
0x1400466d6  jmp     short loc_1400466F9
0x1400466d8  mov     ecx, ebx
0x1400466da  sub     ecx, 25h ; '%'
0x1400466dd  jz      short loc_1400466D1
0x1400466df  sub     ecx, 3
0x1400466e2  jz      short loc_1400466D1
0x1400466e4  sub     ecx, 2
0x1400466e7  jz      short loc_1400466F7
0x1400466e9  sub     ecx, 17h
0x1400466ec  jz      short loc_1400466F7
0x1400466ee  cmp     ecx, 1
0x1400466f1  jnz     loc_140046791
0x1400466f7  xor     esi, esi
0x1400466f9  mov     rax, [r12+8]
0x1400466fe  mov     r15, [rax+18h]
0x140046702  mov     [rsp+58h+Irp], 0; Irp
0x14004670b  xor     r9d, r9d; ChargeQuota
0x14004670e  xor     r8d, r8d; SecondaryBuffer
0x140046711  mov     rcx, [r13+10h]; VirtualAddress
0x140046715  call    cs:__imp_IoAllocateMdl
0x14004671c  nop     dword ptr [rax+rax+00h]
0x140046721  mov     rdi, rax
0x140046724  mov     [rsp+58h+arg_8], rax
0x140046729  test    rax, rax
0x14004672c  jnz     short loc_14004679D
0x14004672e  mov     ebx, 0C000009Ah
0x140046733  jmp     loc_140046865
0x140046738  cmp     ebx, 89h
0x14004673e  ja      short loc_140046767
0x140046740  jz      short loc_1400466F7
0x140046742  mov     ecx, ebx
0x140046744  sub     ecx, 5Eh ; '^'
0x140046747  jz      short loc_1400466D1
0x140046749  sub     ecx, 1
0x14004674c  jz      short loc_1400466F7
0x14004674e  sub     ecx, 24h ; '$'
0x140046751  jz      short loc_1400466F7
0x140046753  sub     ecx, 1
0x140046756  jz      loc_1400466D1
0x14004675c  cmp     ecx, 4
0x14004675f  jz      loc_1400466D1
0x140046765  jmp     short loc_140046791
0x140046767  mov     ecx, ebx
0x140046769  sub     ecx, 8Ah
0x14004676f  jz      short loc_1400466F7
0x140046771  sub     ecx, 9
0x140046774  jz      short loc_1400466F7
0x140046776  sub     ecx, 0Bh
0x140046779  jz      loc_1400466D1
0x14004677f  sub     ecx, 0Ah
0x140046782  jz      loc_1400466D1
0x140046788  cmp     ecx, 2
0x14004678b  jz      loc_1400466F7
0x140046791  xor     edi, edi
0x140046793  mov     ebx, 0C00000BBh
0x140046798  jmp     loc_140046865
0x14004679d  mov     rax, [r12+8]
0x1400467a2  mov     rdx, [rax+60h]
0x1400467a6  mov     r8d, esi; Operation
0x1400467a9  mov     dl, [rdx+40h]; AccessMode
0x1400467ac  mov     rcx, rdi; MemoryDescriptorList
0x1400467af  call    cs:__imp_MmProbeAndLockPages
0x1400467b6  nop     dword ptr [rax+rax+00h]
0x1400467bb  nop
0x1400467bc  mov     r14b, 1
0x1400467bf  mov     eax, 88h
0x1400467c4  cmp     ebx, eax
0x1400467c6  ja      short loc_1400467E3
0x1400467c8  jz      short loc_140046840
0x1400467ca  cmp     ebx, 8
0x1400467cd  jz      short loc_140046840
0x1400467cf  cmp     ebx, 0Ah
0x1400467d2  jz      short loc_140046840
0x1400467d4  cmp     ebx, 28h ; '('
0x1400467d7  jz      short loc_140046840
0x1400467d9  cmp     ebx, 2Ah ; '*'
0x1400467dc  jz      short loc_140046840
0x1400467de  cmp     ebx, 41h ; 'A'
0x1400467e1  jmp     short loc_1400467FD
0x1400467e3  sub     ebx, 89h
0x1400467e9  jz      short loc_140046840
0x1400467eb  sub     ebx, 1
0x1400467ee  jz      short loc_140046840
0x1400467f0  sub     ebx, 9
0x1400467f3  jz      short loc_140046840
0x1400467f5  sub     ebx, 15h
0x1400467f8  jz      short loc_140046840
0x1400467fa  cmp     ebx, 2
0x1400467fd  jz      short loc_140046840
0x1400467ff  test    byte ptr [rdi+0Ah], 5
0x140046803  jz      short loc_14004680B
0x140046805  mov     rax, [rdi+18h]
0x140046809  jmp     short loc_140046833
0x14004680b  mov     [rsp+58h+Priority], 40000010h; Priority
0x140046813  mov     dword ptr [rsp+58h+Irp], 0; BugCheckOnFailure
0x14004681b  xor     r9d, r9d; RequestedAddress
0x14004681e  xor     edx, edx; AccessMode
0x140046820  lea     r8d, [r9+1]; CacheType
0x140046824  mov     rcx, rdi; MemoryDescriptorList
0x140046827  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004682e  nop     dword ptr [rax+rax+00h]
0x140046833  mov     [r15+18h], rax
0x140046837  test    rax, rax
0x14004683a  jz      loc_14004672E
0x140046840  mov     eax, [r13+0Ch]
0x140046844  mov     [r15+10h], eax
0x140046848  mov     rax, [r12+8]
0x14004684d  mov     [rax+48h], rdi
0x140046851  xor     ebx, ebx
0x140046853  jmp     short loc_140046861
0x140046855  mov     ebx, eax
0x140046857  mov     rdi, [rsp+58h+arg_8]
0x14004685c  mov     r14b, [rsp+58h+arg_0]
0x140046861  test    ebx, ebx
0x140046863  jns     short loc_14004688D
0x140046865  test    rdi, rdi
0x140046868  jz      short loc_14004688D
0x14004686a  test    r14b, r14b
0x14004686d  jz      short loc_14004687E
0x14004686f  mov     rcx, rdi; MemoryDescriptorList
0x140046872  call    cs:__imp_MmUnlockPages
0x140046879  nop     dword ptr [rax+rax+00h]
0x14004687e  mov     rcx, rdi; Mdl
0x140046881  call    cs:__imp_IoFreeMdl
0x140046888  nop     dword ptr [rax+rax+00h]
0x14004688d  mov     eax, ebx
0x14004688f  mov     rbx, [rsp+58h+arg_10]
0x140046894  mov     rsi, [rsp+58h+arg_18]
0x140046899  add     rsp, 30h
0x14004689d  pop     r15
0x14004689f  pop     r14
0x1400468a1  pop     r13
0x1400468a3  pop     r12
0x1400468a5  pop     rdi
0x1400468a6  retn
```
