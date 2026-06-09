# __imp_load_SetNamedSecurityInfoW

- ea: `0x18000416a`
- end: `0x180004176`
- name: `__imp_load_SetNamedSecurityInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800040c7`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000416a`

## pseudocode

```c
__int64 load_SetNamedSecurityInfoW()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000416a  lea     rax, __imp_SetNamedSecurityInfoW
0x180004171  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
