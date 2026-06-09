# PplFreeToLookasideList

- ea: `0x140011b90`
- end: `0x140011bbf`
- name: `PplFreeToLookasideList`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400089d0`
- `0x140012980`
- `0x140012ea0`
- `0x140013150`
- `0x1400199fc`
- `0x14001a398`
- `0x14001b4b4`

## callees

- `0x1400091a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011bac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011bac`

## pseudocode

```c
void __fastcall PplFreeToLookasideList(__int64 a1, void *a2)
{
  void *v2; // rbx
  struct _LOOKASIDE_LIST_EX *ListIndex; // rax

  v2 = a2;
  LODWORD(a2) = HIDWORD(KeGetPcr()[1].LockArray);
  ListIndex = (struct _LOOKASIDE_LIST_EX *)PplpRetrieveListIndex(a1, a2);
  ExFreeToLookasideListEx(ListIndex, v2);
}

```

## disassembly

```asm
0x140011b90  push    rbx
0x140011b92  sub     rsp, 20h
0x140011b96  mov     rbx, rdx
0x140011b99  mov     edx, gs:1A4h
0x140011ba1  call    PplpRetrieveListIndex
0x140011ba6  mov     rdx, rbx; Entry
0x140011ba9  mov     rcx, rax; Lookaside
0x140011bac  call    cs:__imp_ExFreeToLookasideListEx
0x140011bb3  nop     dword ptr [rax+rax+00h]
0x140011bb8  add     rsp, 20h
0x140011bbc  pop     rbx
0x140011bbd  retn
```
