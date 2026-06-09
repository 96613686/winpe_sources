# VhdmpiSrbPartCheckZero

- ea: `0x140012960`
- end: `0x140012aa9`
- name: `VhdmpiSrbPartCheckZero`
- size: `329`
- prototype: `__int64 __fastcall(struct VHD_SRB_PART *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400156b0`
- `0x14001c4a0`

## callees

- `0x140012960`
- `0x140012ab0`
- `0x140017428`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140012a6a`
- `ntoskrnl!IoFreeMdl` at `0x140012a6a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012a3b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012a3b`
- `ntoskrnl!IoAllocateMdl` at `0x1400129e9`
- `ntoskrnl!IoAllocateMdl` at `0x1400129e9`
- `ntoskrnl!IoBuildPartialMdl` at `0x140012a0d`
- `ntoskrnl!IoBuildPartialMdl` at `0x140012a0d`

## pseudocode

```c
__int64 __fastcall VhdmpiSrbPartCheckZero(struct VHD_SRB_PART *a1, unsigned int a2, ULONG a3, _BYTE *a4)
{
  __int64 v6; // rcx
  int v8; // eax
  __int64 v9; // rcx
  struct _MDL *v10; // rbp
  char *v11; // r15
  struct _MDL *Mdl; // rax
  struct _MDL *v13; // rbx
  PVOID MappedSystemVa; // rax

  v6 = *(_QWORD *)a1;
  *a4 = 0;
  if ( (*(_DWORD *)(v6 + 64) & 0x10) != 0 )
  {
    *a4 = 1;
    return 0;
  }
  v8 = *(_DWORD *)(v6 + 60);
  if ( v8 == 4 || v8 == 7 )
    return 0;
  v9 = *(_QWORD *)a1;
  v10 = *(struct _MDL **)(*(_QWORD *)a1 + 72LL);
  if ( *((_QWORD *)a1 + 11) == *(_QWORD *)(*(_QWORD *)a1 + 32LL) && !a2 && a3 == *(_DWORD *)(v9 + 52) )
  {
    v13 = *(struct _MDL **)(*(_QWORD *)a1 + 72LL);
  }
  else
  {
    v11 = (char *)v10->StartVa
        + v10->ByteOffset
        + (unsigned __int64)(unsigned int)(*((_DWORD *)a1 + 22) - *(_DWORD *)(v9 + 32))
        + a2;
    Mdl = IoAllocateMdl(v11, a3, 0, 0, 0);
    v13 = Mdl;
    if ( !Mdl )
      return 3221225626LL;
    IoBuildPartialMdl(v10, Mdl, v11, a3);
  }
  if ( (v13->MdlFlags & 5) != 0 )
    MappedSystemVa = v13->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v13, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    if ( (unsigned __int8)VhdmpiIsBufferZero(MappedSystemVa, a3) )
      *a4 = 1;
    if ( v13 != *(struct _MDL **)(*(_QWORD *)a1 + 72LL) )
      IoFreeMdl(v13);
    return 0;
  }
  VhdmpiSrbPartFreeMdl(a1, v13);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140012960  push    rbx
0x140012962  push    rbp
0x140012963  push    rsi
0x140012964  push    rdi
0x140012965  push    r14
0x140012967  push    r15
0x140012969  sub     rsp, 38h
0x14001296d  mov     rdi, rcx
0x140012970  mov     r14d, r8d
0x140012973  mov     rcx, [rcx]
0x140012976  mov     rsi, r9
0x140012979  mov     byte ptr [r9], 0
0x14001297d  mov     r8d, edx
0x140012980  mov     eax, [rcx+40h]
0x140012983  test    al, 10h
0x140012985  jnz     loc_140012A8B
0x14001298b  mov     eax, [rcx+3Ch]
0x14001298e  cmp     eax, 4
0x140012991  jz      loc_140012A76
0x140012997  cmp     eax, 7
0x14001299a  jz      loc_140012A76
0x1400129a0  mov     rcx, [rdi]
0x1400129a3  mov     rax, [rcx+20h]
0x1400129a7  mov     rbp, [rcx+48h]
0x1400129ab  cmp     [rdi+58h], rax
0x1400129af  jnz     short loc_1400129BF
0x1400129b1  test    edx, edx
0x1400129b3  jnz     short loc_1400129BF
0x1400129b5  cmp     r14d, [rcx+34h]
0x1400129b9  jz      loc_140012A86
0x1400129bf  mov     r15d, [rdi+58h]
0x1400129c3  xor     r9d, r9d; ChargeQuota
0x1400129c6  sub     r15d, [rcx+20h]
0x1400129ca  mov     edx, r14d; Length
0x1400129cd  mov     eax, [rbp+2Ch]
0x1400129d0  add     r15, rax
0x1400129d3  mov     [rsp+68h+Irp], 0; Irp
0x1400129dc  add     r15, [rbp+20h]
0x1400129e0  add     r15, r8
0x1400129e3  xor     r8d, r8d; SecondaryBuffer
0x1400129e6  mov     rcx, r15; VirtualAddress
0x1400129e9  call    cs:__imp_IoAllocateMdl
0x1400129f0  nop     dword ptr [rax+rax+00h]
0x1400129f5  mov     rbx, rax
0x1400129f8  test    rax, rax
0x1400129fb  jz      loc_140012AA2
0x140012a01  mov     r9d, r14d; Length
0x140012a04  mov     r8, r15; VirtualAddress
0x140012a07  mov     rdx, rax; TargetMdl
0x140012a0a  mov     rcx, rbp; SourceMdl
0x140012a0d  call    cs:__imp_IoBuildPartialMdl
0x140012a14  nop     dword ptr [rax+rax+00h]
0x140012a19  test    byte ptr [rbx+0Ah], 5
0x140012a1d  jnz     short loc_140012A91
0x140012a1f  xor     r9d, r9d; RequestedAddress
0x140012a22  mov     [rsp+68h+Priority], 40000010h; Priority
0x140012a2a  xor     edx, edx; AccessMode
0x140012a2c  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x140012a34  mov     rcx, rbx; MemoryDescriptorList
0x140012a37  lea     r8d, [r9+1]; CacheType
0x140012a3b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012a42  nop     dword ptr [rax+rax+00h]
0x140012a47  test    rax, rax
0x140012a4a  jz      short loc_140012A97
0x140012a4c  mov     edx, r14d
0x140012a4f  mov     rcx, rax
0x140012a52  call    VhdmpiIsBufferZero
0x140012a57  test    al, al
0x140012a59  jz      short loc_140012A5E
0x140012a5b  mov     byte ptr [rsi], 1
0x140012a5e  mov     rax, [rdi]
0x140012a61  cmp     rbx, [rax+48h]
0x140012a65  jz      short loc_140012A76
0x140012a67  mov     rcx, rbx; Mdl
0x140012a6a  call    cs:__imp_IoFreeMdl
0x140012a71  nop     dword ptr [rax+rax+00h]
0x140012a76  xor     eax, eax
0x140012a78  add     rsp, 38h
0x140012a7c  pop     r15
0x140012a7e  pop     r14
0x140012a80  pop     rdi
0x140012a81  pop     rsi
0x140012a82  pop     rbp
0x140012a83  pop     rbx
0x140012a84  retn
0x140012a86  mov     rbx, rbp
0x140012a89  jmp     short loc_140012A19
0x140012a8b  mov     byte ptr [r9], 1
0x140012a8f  jmp     short loc_140012A76
0x140012a91  mov     rax, [rbx+18h]
0x140012a95  jmp     short loc_140012A47
0x140012a97  mov     rdx, rbx; struct _MDL *
0x140012a9a  mov     rcx, rdi; struct VHD_SRB_PART *
0x140012a9d  call    ?VhdmpiSrbPartFreeMdl@@YAXPEAUVHD_SRB_PART@@PEAU_MDL@@@Z; VhdmpiSrbPartFreeMdl(VHD_SRB_PART *,_MDL *)
0x140012aa2  mov     eax, 0C000009Ah
0x140012aa7  jmp     short loc_140012A78
```
