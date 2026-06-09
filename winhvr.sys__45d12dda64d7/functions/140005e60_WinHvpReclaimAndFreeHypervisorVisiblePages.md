# WinHvpReclaimAndFreeHypervisorVisiblePages

- ea: `0x140005e60`
- end: `0x140005eba`
- name: `WinHvpReclaimAndFreeHypervisorVisiblePages`
- size: `90`
- prototype: `__int64 __fastcall(PMDL MemoryDescriptorList)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140005af8`
- `0x140005be4`
- `0x140005d3c`

## callees

- `0x140005e60`
- `0x14000b024`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x140005e7d`
- `ntoskrnl!MmUnmapLockedPages` at `0x140005e7d`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140005e9a`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140005e9a`

## pseudocode

```c
__int64 __fastcall WinHvpReclaimAndFreeHypervisorVisiblePages(PMDL MemoryDescriptorList, char a2)
{
  if ( (MemoryDescriptorList->MdlFlags & 1) != 0 )
    MmUnmapLockedPages(MemoryDescriptorList->MappedSystemVa, MemoryDescriptorList);
  if ( a2 )
    MemoryDescriptorList->MdlFlags &= ~0x800u;
  MmFreePagesFromMdl(MemoryDescriptorList);
  return WinHvpFreePool(MemoryDescriptorList);
}

```

## disassembly

```asm
0x140005e60  mov     [rsp+arg_0], rbx
0x140005e65  push    rdi
0x140005e66  sub     rsp, 20h
0x140005e6a  test    byte ptr [rcx+0Ah], 1
0x140005e6e  mov     dil, dl
0x140005e71  mov     rbx, rcx
0x140005e74  jz      short loc_140005E89
0x140005e76  mov     rdx, rcx; MemoryDescriptorList
0x140005e79  mov     rcx, [rcx+18h]; BaseAddress
0x140005e7d  call    cs:__imp_MmUnmapLockedPages
0x140005e84  nop     dword ptr [rax+rax+00h]
0x140005e89  test    dil, dil
0x140005e8c  jz      short loc_140005E97
0x140005e8e  mov     eax, 0FFFFF7FFh
0x140005e93  and     [rbx+0Ah], ax
0x140005e97  mov     rcx, rbx; MemoryDescriptorList
0x140005e9a  call    cs:__imp_MmFreePagesFromMdl
0x140005ea1  nop     dword ptr [rax+rax+00h]
0x140005ea6  mov     rcx, rbx
0x140005ea9  call    WinHvpFreePool
0x140005eae  mov     rbx, [rsp+28h+arg_0]
0x140005eb3  add     rsp, 20h
0x140005eb7  pop     rdi
0x140005eb8  retn
```
