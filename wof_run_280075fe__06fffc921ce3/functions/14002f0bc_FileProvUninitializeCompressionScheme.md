# FileProvUninitializeCompressionScheme

- ea: `0x14002f0bc`
- end: `0x14002f12e`
- name: `FileProvUninitializeCompressionScheme`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ec90`

## callees

- `0x14002f0bc`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f108`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f11b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f108`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f11b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f0cf`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f0e2`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f0f5`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f0cf`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f0e2`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f0f5`

## pseudocode

```c
void __fastcall FileProvUninitializeCompressionScheme(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 16) )
  {
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 64));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 192));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 384));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 512));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 640));
  }
}

```

## disassembly

```asm
0x14002f0bc  push    rbx
0x14002f0be  sub     rsp, 20h
0x14002f0c2  cmp     byte ptr [rcx+10h], 0
0x14002f0c6  mov     rbx, rcx
0x14002f0c9  jz      short loc_14002F127
0x14002f0cb  add     rcx, 40h ; '@'; Lookaside
0x14002f0cf  call    cs:__imp_ExDeletePagedLookasideList
0x14002f0d6  nop     dword ptr [rax+rax+00h]
0x14002f0db  lea     rcx, [rbx+0C0h]; Lookaside
0x14002f0e2  call    cs:__imp_ExDeletePagedLookasideList
0x14002f0e9  nop     dword ptr [rax+rax+00h]
0x14002f0ee  lea     rcx, [rbx+180h]; Lookaside
0x14002f0f5  call    cs:__imp_ExDeletePagedLookasideList
0x14002f0fc  nop     dword ptr [rax+rax+00h]
0x14002f101  lea     rcx, [rbx+200h]; Lookaside
0x14002f108  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002f10f  nop     dword ptr [rax+rax+00h]
0x14002f114  lea     rcx, [rbx+280h]; Lookaside
0x14002f11b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002f122  nop     dword ptr [rax+rax+00h]
0x14002f127  add     rsp, 20h
0x14002f12b  pop     rbx
0x14002f12c  retn
```
