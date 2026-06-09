# OutUninitializeQueue

- ea: `0x14000a030`
- end: `0x14000a157`
- name: `OutUninitializeQueue`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400069c0`
- `0x140009b80`

## callees

- `0x14000a030`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a0a7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a057`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a080`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a057`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a080`
- `ntoskrnl!IoFreeMdl` at `0x14000a0ee`
- `ntoskrnl!IoFreeMdl` at `0x14000a139`
- `ntoskrnl!IoFreeMdl` at `0x14000a0ee`
- `ntoskrnl!IoFreeMdl` at `0x14000a139`
- `ntoskrnl!MmFreeMappingAddress` at `0x14000a0cb`
- `ntoskrnl!MmFreeMappingAddress` at `0x14000a116`
- `ntoskrnl!MmFreeMappingAddress` at `0x14000a0cb`
- `ntoskrnl!MmFreeMappingAddress` at `0x14000a116`

## pseudocode

```c
void __fastcall OutUninitializeQueue(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  struct _MDL *v5; // rcx
  void *v6; // rcx
  struct _MDL *v7; // rcx

  v2 = *(void **)(a1 + 712);
  if ( v2 != (void *)(a1 + 744) && v2 )
    ExFreePoolWithTag(v2, *(_DWORD *)(a1 + 728));
  v3 = *(void **)(a1 + 752);
  *(_QWORD *)(a1 + 712) = 0;
  if ( v3 )
  {
    ExFreePoolWithTag(v3, *(_DWORD *)(a1 + 728));
    *(_QWORD *)(a1 + 752) = 0;
  }
  if ( *(_BYTE *)(a1 + 448) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 320));
    *(_BYTE *)(a1 + 448) = 0;
  }
  v4 = *(void **)(a1 + 648);
  if ( v4 )
  {
    MmFreeMappingAddress(v4, 0x636D6B56u);
    *(_QWORD *)(a1 + 648) = 0;
  }
  v5 = *(struct _MDL **)(a1 + 656);
  if ( v5 )
  {
    IoFreeMdl(v5);
    *(_QWORD *)(a1 + 656) = 0;
  }
  v6 = *(void **)(a1 + 760);
  if ( v6 )
  {
    MmFreeMappingAddress(v6, 0x636D6B56u);
    *(_QWORD *)(a1 + 760) = 0;
  }
  v7 = *(struct _MDL **)(a1 + 768);
  if ( v7 )
  {
    IoFreeMdl(v7);
    *(_QWORD *)(a1 + 768) = 0;
  }
}

```

## disassembly

```asm
0x14000a030  push    rbx
0x14000a032  sub     rsp, 20h
0x14000a036  mov     rbx, rcx
0x14000a039  mov     rcx, [rcx+2C8h]; P
0x14000a040  lea     rax, [rbx+2E8h]
0x14000a047  cmp     rcx, rax
0x14000a04a  jz      short loc_14000A063
0x14000a04c  test    rcx, rcx
0x14000a04f  jz      short loc_14000A063
0x14000a051  mov     edx, [rbx+2D8h]; Tag
0x14000a057  call    cs:__imp_ExFreePoolWithTag
0x14000a05e  nop     dword ptr [rax+rax+00h]
0x14000a063  mov     rcx, [rbx+2F0h]; P
0x14000a06a  mov     qword ptr [rbx+2C8h], 0
0x14000a075  test    rcx, rcx
0x14000a078  jz      short loc_14000A097
0x14000a07a  mov     edx, [rbx+2D8h]; Tag
0x14000a080  call    cs:__imp_ExFreePoolWithTag
0x14000a087  nop     dword ptr [rax+rax+00h]
0x14000a08c  mov     qword ptr [rbx+2F0h], 0
0x14000a097  cmp     byte ptr [rbx+1C0h], 0
0x14000a09e  jz      short loc_14000A0BA
0x14000a0a0  lea     rcx, [rbx+140h]; Lookaside
0x14000a0a7  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a0ae  nop     dword ptr [rax+rax+00h]
0x14000a0b3  mov     byte ptr [rbx+1C0h], 0
0x14000a0ba  mov     rcx, [rbx+288h]; BaseAddress
0x14000a0c1  test    rcx, rcx
0x14000a0c4  jz      short loc_14000A0E2
0x14000a0c6  mov     edx, 636D6B56h; PoolTag
0x14000a0cb  call    cs:__imp_MmFreeMappingAddress
0x14000a0d2  nop     dword ptr [rax+rax+00h]
0x14000a0d7  mov     qword ptr [rbx+288h], 0
0x14000a0e2  mov     rcx, [rbx+290h]; Mdl
0x14000a0e9  test    rcx, rcx
0x14000a0ec  jz      short loc_14000A105
0x14000a0ee  call    cs:__imp_IoFreeMdl
0x14000a0f5  nop     dword ptr [rax+rax+00h]
0x14000a0fa  mov     qword ptr [rbx+290h], 0
0x14000a105  mov     rcx, [rbx+2F8h]; BaseAddress
0x14000a10c  test    rcx, rcx
0x14000a10f  jz      short loc_14000A12D
0x14000a111  mov     edx, 636D6B56h; PoolTag
0x14000a116  call    cs:__imp_MmFreeMappingAddress
0x14000a11d  nop     dword ptr [rax+rax+00h]
0x14000a122  mov     qword ptr [rbx+2F8h], 0
0x14000a12d  mov     rcx, [rbx+300h]; Mdl
0x14000a134  test    rcx, rcx
0x14000a137  jz      short loc_14000A150
0x14000a139  call    cs:__imp_IoFreeMdl
0x14000a140  nop     dword ptr [rax+rax+00h]
0x14000a145  mov     qword ptr [rbx+300h], 0
0x14000a150  add     rsp, 20h
0x14000a154  pop     rbx
0x14000a155  retn
```
