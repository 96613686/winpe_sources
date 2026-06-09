# __imp_load_CLSIDFromString

- ea: `0x180009945`
- end: `0x180009951`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800090ab`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009945`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009945  lea     rax, __imp_CLSIDFromString
0x18000994c  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
