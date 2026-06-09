# UdfFreeLcb

- ea: `0x14000c5c8`
- end: `0x14000c62e`
- name: `UdfFreeLcb`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002cca0`
- `0x140050a8c`

## callees

- `0x140004340`
- `0x14000c5c8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000c614`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000c614`

## pseudocode

```c
void __fastcall UdfFreeLcb(PVOID *a1)
{
  _DWORD *v2; // rcx
  _QWORD *v3; // rcx

  v2 = *a1;
  if ( (v2[17] & 4) != 0 )
    UdfFreePool(v2 + 56);
  v3 = (char *)*a1 + 88;
  if ( *v3 )
    UdfFreePool(v3);
  if ( (*((_DWORD *)*a1 + 17) & 1) != 0 )
  {
    UdfFreePool(a1);
  }
  else
  {
    ExFreeToPagedLookasideList(&UdfLcbLookasideList, *a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x14000c5c8  push    rbx
0x14000c5ca  sub     rsp, 20h
0x14000c5ce  mov     rbx, rcx
0x14000c5d1  mov     rcx, [rcx]
0x14000c5d4  mov     eax, [rcx+44h]
0x14000c5d7  test    al, 4
0x14000c5d9  jz      short loc_14000C5E7
0x14000c5db  add     rcx, 0E0h
0x14000c5e2  call    UdfFreePool
0x14000c5e7  mov     rcx, [rbx]
0x14000c5ea  add     rcx, 58h ; 'X'
0x14000c5ee  cmp     qword ptr [rcx], 0
0x14000c5f2  jz      short loc_14000C5F9
0x14000c5f4  call    UdfFreePool
0x14000c5f9  mov     rdx, [rbx]; Entry
0x14000c5fc  mov     eax, [rdx+44h]
0x14000c5ff  test    al, 1
0x14000c601  jz      short loc_14000C60D
0x14000c603  mov     rcx, rbx
0x14000c606  call    UdfFreePool
0x14000c60b  jmp     short loc_14000C627
0x14000c60d  lea     rcx, UdfLcbLookasideList; Lookaside
0x14000c614  call    cs:__imp_ExFreeToPagedLookasideList
0x14000c61b  nop     dword ptr [rax+rax+00h]
0x14000c620  mov     qword ptr [rbx], 0
0x14000c627  add     rsp, 20h
0x14000c62b  pop     rbx
0x14000c62c  retn
```
