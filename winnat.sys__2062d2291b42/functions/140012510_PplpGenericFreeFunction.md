# PplpGenericFreeFunction

- ea: `0x140012510`
- end: `0x140012530`
- name: `PplpGenericFreeFunction`
- size: `32`
- prototype: `FREE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001251e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001251e`

## pseudocode

```c
void __fastcall PplpGenericFreeFunction(PVOID Buffer, PLOOKASIDE_LIST_EX Lookaside)
{
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment, Buffer);
}

```

## disassembly

```asm
0x140012510  sub     rsp, 28h
0x140012514  mov     rax, rdx
0x140012517  mov     rdx, rcx; Entry
0x14001251a  mov     rcx, [rax+60h]; Lookaside
0x14001251e  call    cs:__imp_ExFreeToLookasideListEx
0x140012525  nop     dword ptr [rax+rax+00h]
0x14001252a  add     rsp, 28h
0x14001252e  retn
```
