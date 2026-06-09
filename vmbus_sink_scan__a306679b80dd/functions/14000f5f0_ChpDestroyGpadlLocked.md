# ChpDestroyGpadlLocked

- ea: `0x14000f5f0`
- end: `0x14000f6bc`
- name: `ChpDestroyGpadlLocked`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000f158`
- `0x14000f6c4`
- `0x14000f86c`

## callees

- `0x14000f5f0`
- `0x14000f90c`
- `0x140010fd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f645`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f685`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f645`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f685`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6a4`
- `ntoskrnl!IoFreeMdl` at `0x14000f669`
- `ntoskrnl!IoFreeMdl` at `0x14000f669`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000f634`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000f634`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000f625`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000f625`
- `ntoskrnl!MmUnlockPages` at `0x14000f65a`
- `ntoskrnl!MmUnlockPages` at `0x14000f65a`

## pseudocode

```c
void __fastcall ChpDestroyGpadlLocked(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // rbx
  void *v5; // rcx

  if ( *(_QWORD *)(a2 + 56) )
    ChpRemoveGpadlLocked();
  v3 = *(_DWORD *)(a2 + 68);
  if ( (v3 & 1) != 0 )
  {
    v4 = *(_QWORD *)(a2 + 24);
    if ( (v3 & 4) != 0 )
    {
      if ( (*(_BYTE *)(v4 + 10) & 1) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v4 + 24), *(PMDL *)(a2 + 24));
      MmFreePagesFromMdl((PMDL)v4);
      ExFreePoolWithTag((PVOID)v4, 0);
    }
    else
    {
      if ( (v3 & 2) != 0 )
        MmUnlockPages(*(PMDL *)(a2 + 24));
      IoFreeMdl((PMDL)v4);
    }
  }
  v5 = *(void **)(a2 + 40);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x73756256u);
  if ( *(_QWORD *)(a2 + 112) )
    ChFreeSendMessage();
  ExFreePoolWithTag((PVOID)a2, 0x73756256u);
}

```

## disassembly

```asm
0x14000f5f0  mov     [rsp+arg_0], rbx
0x14000f5f5  push    rdi
0x14000f5f6  sub     rsp, 20h
0x14000f5fa  cmp     qword ptr [rdx+38h], 0
0x14000f5ff  mov     rdi, rdx
0x14000f602  jz      short loc_14000F609
0x14000f604  call    ChpRemoveGpadlLocked
0x14000f609  mov     eax, [rdi+44h]
0x14000f60c  test    al, 1
0x14000f60e  jz      short loc_14000F675
0x14000f610  mov     rbx, [rdi+18h]
0x14000f614  test    al, 4
0x14000f616  jz      short loc_14000F653
0x14000f618  test    byte ptr [rbx+0Ah], 1
0x14000f61c  jz      short loc_14000F631
0x14000f61e  mov     rcx, [rbx+18h]; BaseAddress
0x14000f622  mov     rdx, rbx; MemoryDescriptorList
0x14000f625  call    cs:__imp_MmUnmapLockedPages
0x14000f62c  nop     dword ptr [rax+rax+00h]
0x14000f631  mov     rcx, rbx; MemoryDescriptorList
0x14000f634  call    cs:__imp_MmFreePagesFromMdl
0x14000f63b  nop     dword ptr [rax+rax+00h]
0x14000f640  xor     edx, edx; Tag
0x14000f642  mov     rcx, rbx; P
0x14000f645  call    cs:__imp_ExFreePoolWithTag
0x14000f64c  nop     dword ptr [rax+rax+00h]
0x14000f651  jmp     short loc_14000F675
0x14000f653  test    al, 2
0x14000f655  jz      short loc_14000F666
0x14000f657  mov     rcx, rbx; MemoryDescriptorList
0x14000f65a  call    cs:__imp_MmUnlockPages
0x14000f661  nop     dword ptr [rax+rax+00h]
0x14000f666  mov     rcx, rbx; Mdl
0x14000f669  call    cs:__imp_IoFreeMdl
0x14000f670  nop     dword ptr [rax+rax+00h]
0x14000f675  mov     rcx, [rdi+28h]; P
0x14000f679  mov     ebx, 73756256h
0x14000f67e  test    rcx, rcx
0x14000f681  jz      short loc_14000F691
0x14000f683  mov     edx, ebx; Tag
0x14000f685  call    cs:__imp_ExFreePoolWithTag
0x14000f68c  nop     dword ptr [rax+rax+00h]
0x14000f691  mov     rcx, [rdi+70h]
0x14000f695  test    rcx, rcx
0x14000f698  jz      short loc_14000F69F
0x14000f69a  call    ChFreeSendMessage
0x14000f69f  mov     edx, ebx; Tag
0x14000f6a1  mov     rcx, rdi; P
0x14000f6a4  call    cs:__imp_ExFreePoolWithTag
0x14000f6ab  nop     dword ptr [rax+rax+00h]
0x14000f6b0  mov     rbx, [rsp+28h+arg_0]
0x14000f6b5  add     rsp, 20h
0x14000f6b9  pop     rdi
0x14000f6ba  retn
```
