# __imp_load_PostThreadMessageA

- ea: `0x18000d744`
- end: `0x18000d750`
- name: `__imp_load_PostThreadMessageA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d617`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x18000d744`

## pseudocode

```c
__int64 load_PostThreadMessageA()
{
  return _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000d744  lea     rax, __imp_PostThreadMessageA
0x18000d74b  jmp     __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll
```
