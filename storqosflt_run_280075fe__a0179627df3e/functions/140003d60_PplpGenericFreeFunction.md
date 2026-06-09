# PplpGenericFreeFunction

- ea: `0x140003d60`
- end: `0x140003d80`
- name: `PplpGenericFreeFunction`
- size: `32`
- prototype: `FREE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140003d6e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140003d6e`

## pseudocode

```c
void __fastcall PplpGenericFreeFunction(PVOID Buffer, PLOOKASIDE_LIST_EX Lookaside)
{
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment, Buffer);
}

```

## disassembly

```asm
0x140003d60  sub     rsp, 28h
0x140003d64  mov     rax, rdx
0x140003d67  mov     rdx, rcx; Entry
0x140003d6a  mov     rcx, [rax+60h]; Lookaside
0x140003d6e  call    cs:__imp_ExFreeToLookasideListEx
0x140003d75  nop     dword ptr [rax+rax+00h]
0x140003d7a  add     rsp, 28h
0x140003d7e  retn
```
