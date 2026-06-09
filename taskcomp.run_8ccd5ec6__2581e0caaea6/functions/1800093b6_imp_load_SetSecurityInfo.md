# __imp_load_SetSecurityInfo

- ea: `0x1800093b6`
- end: `0x1800093c2`
- name: `__imp_load_SetSecurityInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180008eb0`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800093b6`

## pseudocode

```c
__int64 load_SetSecurityInfo()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800093b6  lea     rax, __imp_SetSecurityInfo
0x1800093bd  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
