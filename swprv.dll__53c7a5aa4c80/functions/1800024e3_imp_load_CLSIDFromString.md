# __imp_load_CLSIDFromString

- ea: `0x1800024e3`
- end: `0x1800024ef`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002271`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800024e3`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800024e3  lea     rax, __imp_CLSIDFromString
0x1800024ea  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
