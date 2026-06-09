# VhdmpiSrbPartCheckZero

- ea: `0x140011630`
- end: `0x140011779`
- name: `VhdmpiSrbPartCheckZero`
- size: `329`
- prototype: `__int64 __fastcall(struct VHD_SRB_PART *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140015210`
- `0x14001c080`

## callees

- `0x140011630`
- `0x140011780`
- `0x140016f88`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14001173a`
- `ntoskrnl!IoFreeMdl` at `0x14001173a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001170b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001170b`
- `ntoskrnl!IoAllocateMdl` at `0x1400116b9`
- `ntoskrnl!IoAllocateMdl` at `0x1400116b9`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400116dd`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400116dd`

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
0x140011630  push    rbx
0x140011632  push    rbp
0x140011633  push    rsi
0x140011634  push    rdi
0x140011635  push    r14
0x140011637  push    r15
0x140011639  sub     rsp, 38h
0x14001163d  mov     rdi, rcx
0x140011640  mov     r14d, r8d
0x140011643  mov     rcx, [rcx]
0x140011646  mov     rsi, r9
0x140011649  mov     byte ptr [r9], 0
0x14001164d  mov     r8d, edx
0x140011650  mov     eax, [rcx+40h]
0x140011653  test    al, 10h
0x140011655  jnz     loc_14001175B
0x14001165b  mov     eax, [rcx+3Ch]
0x14001165e  cmp     eax, 4
0x140011661  jz      loc_140011746
0x140011667  cmp     eax, 7
0x14001166a  jz      loc_140011746
0x140011670  mov     rcx, [rdi]
0x140011673  mov     rax, [rcx+20h]
0x140011677  mov     rbp, [rcx+48h]
0x14001167b  cmp     [rdi+58h], rax
0x14001167f  jnz     short loc_14001168F
0x140011681  test    edx, edx
0x140011683  jnz     short loc_14001168F
0x140011685  cmp     r14d, [rcx+34h]
0x140011689  jz      loc_140011756
0x14001168f  mov     r15d, [rdi+58h]
0x140011693  xor     r9d, r9d; ChargeQuota
0x140011696  sub     r15d, [rcx+20h]
0x14001169a  mov     edx, r14d; Length
0x14001169d  mov     eax, [rbp+2Ch]
0x1400116a0  add     r15, rax
0x1400116a3  mov     [rsp+68h+Irp], 0; Irp
0x1400116ac  add     r15, [rbp+20h]
0x1400116b0  add     r15, r8
0x1400116b3  xor     r8d, r8d; SecondaryBuffer
0x1400116b6  mov     rcx, r15; VirtualAddress
0x1400116b9  call    cs:__imp_IoAllocateMdl
0x1400116c0  nop     dword ptr [rax+rax+00h]
0x1400116c5  mov     rbx, rax
0x1400116c8  test    rax, rax
0x1400116cb  jz      loc_140011772
0x1400116d1  mov     r9d, r14d; Length
0x1400116d4  mov     r8, r15; VirtualAddress
0x1400116d7  mov     rdx, rax; TargetMdl
0x1400116da  mov     rcx, rbp; SourceMdl
0x1400116dd  call    cs:__imp_IoBuildPartialMdl
0x1400116e4  nop     dword ptr [rax+rax+00h]
0x1400116e9  test    byte ptr [rbx+0Ah], 5
0x1400116ed  jnz     short loc_140011761
0x1400116ef  xor     r9d, r9d; RequestedAddress
0x1400116f2  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400116fa  xor     edx, edx; AccessMode
0x1400116fc  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x140011704  mov     rcx, rbx; MemoryDescriptorList
0x140011707  lea     r8d, [r9+1]; CacheType
0x14001170b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011712  nop     dword ptr [rax+rax+00h]
0x140011717  test    rax, rax
0x14001171a  jz      short loc_140011767
0x14001171c  mov     edx, r14d
0x14001171f  mov     rcx, rax
0x140011722  call    VhdmpiIsBufferZero
0x140011727  test    al, al
0x140011729  jz      short loc_14001172E
0x14001172b  mov     byte ptr [rsi], 1
0x14001172e  mov     rax, [rdi]
0x140011731  cmp     rbx, [rax+48h]
0x140011735  jz      short loc_140011746
0x140011737  mov     rcx, rbx; Mdl
0x14001173a  call    cs:__imp_IoFreeMdl
0x140011741  nop     dword ptr [rax+rax+00h]
0x140011746  xor     eax, eax
0x140011748  add     rsp, 38h
0x14001174c  pop     r15
0x14001174e  pop     r14
0x140011750  pop     rdi
0x140011751  pop     rsi
0x140011752  pop     rbp
0x140011753  pop     rbx
0x140011754  retn
0x140011756  mov     rbx, rbp
0x140011759  jmp     short loc_1400116E9
0x14001175b  mov     byte ptr [r9], 1
0x14001175f  jmp     short loc_140011746
0x140011761  mov     rax, [rbx+18h]
0x140011765  jmp     short loc_140011717
0x140011767  mov     rdx, rbx; struct _MDL *
0x14001176a  mov     rcx, rdi; struct VHD_SRB_PART *
0x14001176d  call    ?VhdmpiSrbPartFreeMdl@@YAXPEAUVHD_SRB_PART@@PEAU_MDL@@@Z; VhdmpiSrbPartFreeMdl(VHD_SRB_PART *,_MDL *)
0x140011772  mov     eax, 0C000009Ah
0x140011777  jmp     short loc_140011748
```
