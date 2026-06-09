# __imp_load_CreateUri

- ea: `0x14002e9cb`
- end: `0x14002e9d7`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002e94c`

## import_xrefs

- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x14002e9cb`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_ext_ms_win_core_iuri_l1_1_0_dll();
}

```

## disassembly

```asm
0x14002e9cb  lea     rax, __imp_CreateUri
0x14002e9d2  jmp     __tailMerge_ext_ms_win_core_iuri_l1_1_0_dll
```
