# PplpGenericAllocateFunction

- ea: `0x14000be30`
- end: `0x14000be4a`
- name: `PplpGenericAllocateFunction`
- size: `26`
- prototype: `ALLOCATE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000be38`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000be38`

## pseudocode

```c
PVOID __fastcall PplpGenericAllocateFunction(
        POOL_TYPE PoolType,
        SIZE_T NumberOfBytes,
        ULONG Tag,
        PLOOKASIDE_LIST_EX Lookaside)
{
  return ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment);
}

```

## disassembly

```asm
0x14000be30  sub     rsp, 28h
0x14000be34  mov     rcx, [r9+60h]; Lookaside
0x14000be38  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000be3f  nop     dword ptr [rax+rax+00h]
0x14000be44  add     rsp, 28h
0x14000be48  retn
```
