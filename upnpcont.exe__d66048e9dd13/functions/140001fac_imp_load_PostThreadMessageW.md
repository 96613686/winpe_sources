# __imp_load_PostThreadMessageW

- ea: `0x140001fac`
- end: `0x140001fb8`
- name: `__imp_load_PostThreadMessageW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001f2d`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x140001fac`

## pseudocode

```c
__int64 load_PostThreadMessageW()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x140001fac  lea     rax, __imp_PostThreadMessageW
0x140001fb3  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll
```
