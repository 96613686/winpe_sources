# __imp_load_EnumThreadWindows

- ea: `0x140008f42`
- end: `0x140008f4e`
- name: `__imp_load_EnumThreadWindows`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140008ec3`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!EnumThreadWindows` at `0x140008f42`

## pseudocode

```c
__int64 load_EnumThreadWindows()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x140008f42  lea     rax, __imp_EnumThreadWindows
0x140008f49  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
