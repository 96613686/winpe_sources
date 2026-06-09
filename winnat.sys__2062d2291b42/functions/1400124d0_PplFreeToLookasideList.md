# PplFreeToLookasideList

- ea: `0x1400124d0`
- end: `0x1400124ff`
- name: `PplFreeToLookasideList`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400089d0`
- `0x1400132c0`
- `0x1400137e0`
- `0x140013a90`
- `0x140019edc`
- `0x14001a878`
- `0x14001b994`

## callees

- `0x1400091a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400124ec`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400124ec`

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
0x1400124d0  push    rbx
0x1400124d2  sub     rsp, 20h
0x1400124d6  mov     rbx, rdx
0x1400124d9  mov     edx, gs:1A4h
0x1400124e1  call    PplpRetrieveListIndex
0x1400124e6  mov     rdx, rbx; Entry
0x1400124e9  mov     rcx, rax; Lookaside
0x1400124ec  call    cs:__imp_ExFreeToLookasideListEx
0x1400124f3  nop     dword ptr [rax+rax+00h]
0x1400124f8  add     rsp, 20h
0x1400124fc  pop     rbx
0x1400124fd  retn
```
