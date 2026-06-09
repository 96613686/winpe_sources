# UdfDeleteCcb

- ea: `0x140056780`
- end: `0x1400567c5`
- name: `UdfDeleteCcb`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140050ee0`

## callees

- `0x140056780`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140056794`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056794`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400567b2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400567b2`

## pseudocode

```c
void __fastcall UdfDeleteCcb(__int64 a1, _QWORD *a2)
{
  void *v2; // rcx

  v2 = (void *)a2[6];
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    a2[6] = 0;
  }
  ExFreeToPagedLookasideList(&UdfCcbLookasideList, a2);
}

```

## disassembly

```asm
0x140056780  push    rbx
0x140056782  sub     rsp, 20h
0x140056786  mov     rcx, [rdx+30h]; P
0x14005678a  mov     rbx, rdx
0x14005678d  test    rcx, rcx
0x140056790  jz      short loc_1400567A8
0x140056792  xor     edx, edx; Tag
0x140056794  call    cs:__imp_ExFreePoolWithTag
0x14005679b  nop     dword ptr [rax+rax+00h]
0x1400567a0  mov     qword ptr [rbx+30h], 0
0x1400567a8  mov     rdx, rbx; Entry
0x1400567ab  lea     rcx, UdfCcbLookasideList; Lookaside
0x1400567b2  call    cs:__imp_ExFreeToPagedLookasideList
0x1400567b9  nop     dword ptr [rax+rax+00h]
0x1400567be  add     rsp, 20h
0x1400567c2  pop     rbx
0x1400567c3  retn
```
