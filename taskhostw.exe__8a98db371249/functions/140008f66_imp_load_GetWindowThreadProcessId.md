# __imp_load_GetWindowThreadProcessId

- ea: `0x140008f66`
- end: `0x140008f72`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140008ec3`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140008f66`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x140008f66  lea     rax, __imp_GetWindowThreadProcessId
0x140008f6d  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
