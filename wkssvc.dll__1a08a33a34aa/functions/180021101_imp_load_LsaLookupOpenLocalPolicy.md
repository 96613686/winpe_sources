# __imp_load_LsaLookupOpenLocalPolicy

- ea: `0x180021101`
- end: `0x18002110d`
- name: `__imp_load_LsaLookupOpenLocalPolicy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180020c87`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180021101`

## pseudocode

```c
__int64 load_LsaLookupOpenLocalPolicy()
{
  return _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021101  lea     rax, __imp_LsaLookupOpenLocalPolicy
0x180021108  jmp     __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll
```
