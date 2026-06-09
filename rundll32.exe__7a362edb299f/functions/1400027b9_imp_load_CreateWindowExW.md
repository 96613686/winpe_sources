# __imp_load_CreateWindowExW

- ea: `0x1400027b9`
- end: `0x1400027c5`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002728`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x1400027b9`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400027b9  lea     rax, __imp_CreateWindowExW
0x1400027c0  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
