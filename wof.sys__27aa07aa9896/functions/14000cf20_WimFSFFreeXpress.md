# WimFSFFreeXpress

- ea: `0x14000cf20`
- end: `0x14000cf5c`
- name: `WimFSFFreeXpress`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140009000`

## callees

- `0x14000cf20`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000cf37`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000cf37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf4a`

## pseudocode

```c
void __fastcall WimFSFFreeXpress(__int64 a1, __int64 a2)
{
  if ( *(_DWORD *)(a2 - 4) == 1 )
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 320), (PVOID)(a2 - 4));
  else
    ExFreePoolWithTag((PVOID)(a2 - 4), 0);
}

```

## disassembly

```asm
0x14000cf20  sub     rsp, 28h
0x14000cf24  lea     rax, [rdx-4]
0x14000cf28  cmp     dword ptr [rax], 1
0x14000cf2b  jnz     short loc_14000CF45
0x14000cf2d  add     rcx, 140h; Lookaside
0x14000cf34  mov     rdx, rax; Entry
0x14000cf37  call    cs:__imp_ExFreeToPagedLookasideList
0x14000cf3e  nop     dword ptr [rax+rax+00h]
0x14000cf43  jmp     short loc_14000CF56
0x14000cf45  xor     edx, edx; Tag
0x14000cf47  mov     rcx, rax; P
0x14000cf4a  call    cs:__imp_ExFreePoolWithTag
0x14000cf51  nop     dword ptr [rax+rax+00h]
0x14000cf56  add     rsp, 28h
0x14000cf5a  retn
```
