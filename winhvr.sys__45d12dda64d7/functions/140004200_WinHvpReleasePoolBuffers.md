# WinHvpReleasePoolBuffers

- ea: `0x140004200`
- end: `0x140004229`
- name: `WinHvpReleasePoolBuffers`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004217`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004217`

## pseudocode

```c
void __fastcall WinHvpReleasePoolBuffers(__int64 a1)
{
  ExFreeToNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside + ((unsigned __int64)*(unsigned __int16 *)(a1 + 32) << 7)),
    *(PVOID *)(a1 + 40));
}

```

## disassembly

```asm
0x140004200  sub     rsp, 28h
0x140004204  mov     rdx, [rcx+28h]; Entry
0x140004208  movzx   ecx, word ptr [rcx+20h]
0x14000420c  shl     rcx, 7
0x140004210  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140004217  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000421e  nop     dword ptr [rax+rax+00h]
0x140004223  add     rsp, 28h
0x140004227  retn
```
