# __imp_load_CreateWindowExA

- ea: `0x18000da98`
- end: `0x18000daa4`
- name: `__imp_load_CreateWindowExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000da07`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x18000da98`

## pseudocode

```c
__int64 load_CreateWindowExA()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000da98  lea     rax, __imp_CreateWindowExA
0x18000da9f  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
