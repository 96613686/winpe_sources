# PplAllocateFromLookasideList

- ea: `0x140009178`
- end: `0x14000919e`
- name: `PplAllocateFromLookasideList`
- size: `38`
- prototype: `PVOID __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140009034`
- `0x140009b04`
- `0x140012980`
- `0x140012ea0`

## callees

- `0x1400091a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000918c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000918c`

## pseudocode

```c
PVOID __fastcall PplAllocateFromLookasideList(__int64 a1, __int64 a2)
{
  struct _LOOKASIDE_LIST_EX *ListIndex; // rax

  LODWORD(a2) = HIDWORD(KeGetPcr()[1].LockArray);
  ListIndex = (struct _LOOKASIDE_LIST_EX *)PplpRetrieveListIndex(a1, a2);
  return ExAllocateFromLookasideListEx(ListIndex);
}

```

## disassembly

```asm
0x140009178  sub     rsp, 28h
0x14000917c  mov     edx, gs:1A4h
0x140009184  call    PplpRetrieveListIndex
0x140009189  mov     rcx, rax; Lookaside
0x14000918c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140009193  nop     dword ptr [rax+rax+00h]
0x140009198  add     rsp, 28h
0x14000919c  retn
```
