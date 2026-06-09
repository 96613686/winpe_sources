# WanpFreeDriverStructures

- ea: `0x140003960`
- end: `0x1400039bf`
- name: `WanpFreeDriverStructures`
- size: `95`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000353c`
- `0x14001a078`

## callees

- `0x140003960`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000399a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400039ad`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000399a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400039ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003972`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003972`

## pseudocode

```c
void WanpFreeDriverStructures()
{
  if ( g_puipConnTable )
  {
    ExFreePoolWithTag(g_puipConnTable, 0);
    g_puipConnTable = 0;
    g_ulConnTableSize = 0;
  }
  ExDeleteNPagedLookasideList(&g_llConnBlocks);
  ExDeleteNPagedLookasideList(&g_llNotificationBlocks);
}

```

## disassembly

```asm
0x140003960  sub     rsp, 28h
0x140003964  mov     rcx, cs:g_puipConnTable; P
0x14000396b  test    rcx, rcx
0x14000396e  jz      short loc_140003993
0x140003970  xor     edx, edx; Tag
0x140003972  call    cs:__imp_ExFreePoolWithTag
0x140003979  nop     dword ptr [rax+rax+00h]
0x14000397e  mov     cs:g_puipConnTable, 0
0x140003989  mov     cs:g_ulConnTableSize, 0
0x140003993  lea     rcx, g_llConnBlocks; Lookaside
0x14000399a  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400039a1  nop     dword ptr [rax+rax+00h]
0x1400039a6  lea     rcx, g_llNotificationBlocks; Lookaside
0x1400039ad  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400039b4  nop     dword ptr [rax+rax+00h]
0x1400039b9  add     rsp, 28h
0x1400039bd  retn
```
