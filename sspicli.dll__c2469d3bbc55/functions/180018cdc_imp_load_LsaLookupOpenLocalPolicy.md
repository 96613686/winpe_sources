# __imp_load_LsaLookupOpenLocalPolicy

- ea: `0x180018cdc`
- end: `0x180018ce8`
- name: `__imp_load_LsaLookupOpenLocalPolicy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180018c5d`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180018cdc`

## pseudocode

```c
__int64 load_LsaLookupOpenLocalPolicy()
{
  return _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll();
}

```

## disassembly

```asm
0x180018cdc  lea     rax, __imp_LsaLookupOpenLocalPolicy
0x180018ce3  jmp     __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll
```
