# __imp_load_SetSecurityInfo

- ea: `0x180008ed6`
- end: `0x180008ee2`
- name: `__imp_load_SetSecurityInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800089d0`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180008ed6`

## pseudocode

```c
__int64 load_SetSecurityInfo()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008ed6  lea     rax, __imp_SetSecurityInfo
0x180008edd  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
