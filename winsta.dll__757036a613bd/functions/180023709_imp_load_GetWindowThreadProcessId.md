# __imp_load_GetWindowThreadProcessId

- ea: `0x180023709`
- end: `0x180023715`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180023678`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180023709`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x180023709  lea     rax, __imp_GetWindowThreadProcessId
0x180023710  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
