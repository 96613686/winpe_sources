# __imp_load_CreateUri

- ea: `0x14002d7fb`
- end: `0x14002d807`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002d77c`

## import_xrefs

- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x14002d7fb`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_ext_ms_win_core_iuri_l1_1_0_dll();
}

```

## disassembly

```asm
0x14002d7fb  lea     rax, __imp_CreateUri
0x14002d802  jmp     __tailMerge_ext_ms_win_core_iuri_l1_1_0_dll
```
