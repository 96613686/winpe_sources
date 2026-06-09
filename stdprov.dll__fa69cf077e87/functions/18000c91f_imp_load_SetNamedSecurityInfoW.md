# __imp_load_SetNamedSecurityInfoW

- ea: `0x18000c91f`
- end: `0x18000c92b`
- name: `__imp_load_SetNamedSecurityInfoW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000c88e`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000c91f`

## pseudocode

```c
__int64 load_SetNamedSecurityInfoW()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c91f  lea     rax, __imp_SetNamedSecurityInfoW
0x18000c926  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
