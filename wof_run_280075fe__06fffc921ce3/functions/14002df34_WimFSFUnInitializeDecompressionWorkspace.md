# WimFSFUnInitializeDecompressionWorkspace

- ea: `0x14002df34`
- end: `0x14002dfb2`
- name: `WimFSFUnInitializeDecompressionWorkspace`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022e2c`

## callees

- `0x14002df34`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002df88`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002df9b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002df88`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002df9b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df4f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df62`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df75`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df4f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df62`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002df75`

## pseudocode

```c
void __fastcall WimFSFUnInitializeDecompressionWorkspace(__int64 a1)
{
  if ( (*(_DWORD *)(a1 + 96) & 2) != 0 && (*(_DWORD *)(a1 + 100) & 1) != 0 )
  {
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 128));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 512));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 320));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 640));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 768));
    *(_DWORD *)(a1 + 100) &= ~1u;
  }
}

```

## disassembly

```asm
0x14002df34  push    rbx
0x14002df36  sub     rsp, 20h
0x14002df3a  mov     eax, [rcx+60h]
0x14002df3d  mov     rbx, rcx
0x14002df40  test    al, 2
0x14002df42  jz      short loc_14002DFAB
0x14002df44  mov     eax, [rcx+64h]
0x14002df47  test    al, 1
0x14002df49  jz      short loc_14002DFAB
0x14002df4b  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14002df4f  call    cs:__imp_ExDeletePagedLookasideList
0x14002df56  nop     dword ptr [rax+rax+00h]
0x14002df5b  lea     rcx, [rbx+200h]; Lookaside
0x14002df62  call    cs:__imp_ExDeletePagedLookasideList
0x14002df69  nop     dword ptr [rax+rax+00h]
0x14002df6e  lea     rcx, [rbx+140h]; Lookaside
0x14002df75  call    cs:__imp_ExDeletePagedLookasideList
0x14002df7c  nop     dword ptr [rax+rax+00h]
0x14002df81  lea     rcx, [rbx+280h]; Lookaside
0x14002df88  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002df8f  nop     dword ptr [rax+rax+00h]
0x14002df94  lea     rcx, [rbx+300h]; Lookaside
0x14002df9b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002dfa2  nop     dword ptr [rax+rax+00h]
0x14002dfa7  and     dword ptr [rbx+64h], 0FFFFFFFEh
0x14002dfab  add     rsp, 20h
0x14002dfaf  pop     rbx
0x14002dfb0  retn
```
