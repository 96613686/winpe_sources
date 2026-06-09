# PplpGenericAllocateFunction

- ea: `0x14000b750`
- end: `0x14000b76a`
- name: `PplpGenericAllocateFunction`
- size: `26`
- prototype: `PVOID __fastcall(POOL_TYPE PoolType, SIZE_T NumberOfBytes, ULONG Tag, PLOOKASIDE_LIST_EX Lookaside)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000b758`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000b758`

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
0x14000b750  sub     rsp, 28h
0x14000b754  mov     rcx, [r9+60h]; Lookaside
0x14000b758  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000b75f  nop     dword ptr [rax+rax+00h]
0x14000b764  add     rsp, 28h
0x14000b768  retn
```
