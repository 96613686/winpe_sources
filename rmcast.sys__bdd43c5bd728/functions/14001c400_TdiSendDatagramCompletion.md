# TdiSendDatagramCompletion

- ea: `0x14001c400`
- end: `0x14001c4c0`
- name: `TdiSendDatagramCompletion`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400151b0`
- `0x14001c400`
- `0x14001ce30`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c484`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c484`
- `ntoskrnl!IoFreeMdl` at `0x14001c494`
- `ntoskrnl!IoFreeMdl` at `0x14001c494`
- `ntoskrnl!IoFreeIrp` at `0x14001c4a3`
- `ntoskrnl!IoFreeIrp` at `0x14001c4a3`
- `ntoskrnl!MmUnlockPages` at `0x14001c46e`
- `ntoskrnl!MmUnlockPages` at `0x14001c46e`

## pseudocode

```c
__int64 __fastcall TdiSendDatagramCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_DDq(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
      *(unsigned int *)(a2 + 48),
      *(_DWORD *)(a2 + 56),
      a2);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a3 + 72))(
    *(_QWORD *)(a3 + 80),
    *(_QWORD *)(a3 + 88),
    *(unsigned int *)(a2 + 48));
  if ( *(_BYTE *)(a3 + 96) )
    MmUnlockPages(*(PMDL *)(a2 + 8));
  ExFreeToNPagedLookasideList(&Lookaside, (PVOID)a3);
  IoFreeMdl(*(PMDL *)(a2 + 8));
  IoFreeIrp((PIRP)a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001c400  mov     [rsp+arg_0], rbx
0x14001c405  push    rdi
0x14001c406  sub     rsp, 30h
0x14001c40a  mov     rdi, r8
0x14001c40d  mov     rbx, rdx
0x14001c410  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c417  lea     rax, WPP_GLOBAL_Control
0x14001c41e  cmp     rcx, rax
0x14001c421  jz      short loc_14001C44F
0x14001c423  mov     eax, [rcx+2Ch]
0x14001c426  test    al, 10h
0x14001c428  jz      short loc_14001C44F
0x14001c42a  mov     eax, [rbx+38h]
0x14001c42d  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001c434  mov     r9d, [rbx+30h]
0x14001c438  mov     edx, 1Bh
0x14001c43d  mov     rcx, [rcx+18h]
0x14001c441  mov     [rsp+38h+var_10], rbx
0x14001c446  mov     [rsp+38h+var_18], eax
0x14001c44a  call    WPP_SF_DDq
0x14001c44f  mov     rax, [rdi+48h]
0x14001c453  mov     r8d, [rbx+30h]
0x14001c457  mov     rdx, [rdi+58h]
0x14001c45b  mov     rcx, [rdi+50h]
0x14001c45f  call    _guard_dispatch_icall
0x14001c464  cmp     byte ptr [rdi+60h], 0
0x14001c468  jz      short loc_14001C47A
0x14001c46a  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14001c46e  call    cs:__imp_MmUnlockPages
0x14001c475  nop     dword ptr [rax+rax+00h]
0x14001c47a  mov     rdx, rdi; Entry
0x14001c47d  lea     rcx, Lookaside; Lookaside
0x14001c484  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c48b  nop     dword ptr [rax+rax+00h]
0x14001c490  mov     rcx, [rbx+8]; Mdl
0x14001c494  call    cs:__imp_IoFreeMdl
0x14001c49b  nop     dword ptr [rax+rax+00h]
0x14001c4a0  mov     rcx, rbx; Irp
0x14001c4a3  call    cs:__imp_IoFreeIrp
0x14001c4aa  nop     dword ptr [rax+rax+00h]
0x14001c4af  mov     rbx, [rsp+38h+arg_0]
0x14001c4b4  mov     eax, 0C0000016h
0x14001c4b9  add     rsp, 30h
0x14001c4bd  pop     rdi
0x14001c4be  retn
```
