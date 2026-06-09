# PplpGenericFreeFunction

- ea: `0x14000be50`
- end: `0x14000be70`
- name: `PplpGenericFreeFunction`
- size: `32`
- prototype: `FREE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000be5e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000be5e`

## pseudocode

```c
void __fastcall PplpGenericFreeFunction(PVOID Buffer, PLOOKASIDE_LIST_EX Lookaside)
{
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment, Buffer);
}

```

## disassembly

```asm
0x14000be50  sub     rsp, 28h
0x14000be54  mov     rax, rdx
0x14000be57  mov     rdx, rcx; Entry
0x14000be5a  mov     rcx, [rax+60h]; Lookaside
0x14000be5e  call    cs:__imp_ExFreeToLookasideListEx
0x14000be65  nop     dword ptr [rax+rax+00h]
0x14000be6a  add     rsp, 28h
0x14000be6e  retn
```
