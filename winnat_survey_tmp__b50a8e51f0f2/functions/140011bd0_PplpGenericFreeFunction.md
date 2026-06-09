# PplpGenericFreeFunction

- ea: `0x140011bd0`
- end: `0x140011bf0`
- name: `PplpGenericFreeFunction`
- size: `32`
- prototype: `FREE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011bde`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011bde`

## pseudocode

```c
void __fastcall PplpGenericFreeFunction(PVOID Buffer, PLOOKASIDE_LIST_EX Lookaside)
{
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment, Buffer);
}

```

## disassembly

```asm
0x140011bd0  sub     rsp, 28h
0x140011bd4  mov     rax, rdx
0x140011bd7  mov     rdx, rcx; Entry
0x140011bda  mov     rcx, [rax+60h]; Lookaside
0x140011bde  call    cs:__imp_ExFreeToLookasideListEx
0x140011be5  nop     dword ptr [rax+rax+00h]
0x140011bea  add     rsp, 28h
0x140011bee  retn
```
