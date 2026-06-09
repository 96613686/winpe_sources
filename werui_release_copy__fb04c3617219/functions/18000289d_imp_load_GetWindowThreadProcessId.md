# __imp_load_GetWindowThreadProcessId

- ea: `0x18000289d`
- end: `0x1800028a9`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800027e8`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000289d`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000289d  lea     rax, __imp_GetWindowThreadProcessId
0x1800028a4  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
