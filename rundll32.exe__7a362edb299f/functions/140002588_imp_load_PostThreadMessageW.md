# __imp_load_PostThreadMessageW

- ea: `0x140002588`
- end: `0x140002594`
- name: `__imp_load_PostThreadMessageW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002509`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x140002588`

## pseudocode

```c
__int64 load_PostThreadMessageW()
{
  return _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll();
}

```

## disassembly

```asm
0x140002588  lea     rax, __imp_PostThreadMessageW
0x14000258f  jmp     __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll
```
