# __imp_load_RemovePropW

- ea: `0x180003640`
- end: `0x18000364c`
- name: `__imp_load_RemovePropW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800034e9`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x180003640`

## pseudocode

```c
__int64 load_RemovePropW()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003640  lea     rax, __imp_RemovePropW
0x180003647  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll
```
