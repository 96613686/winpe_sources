# __imp_load_GetNamedSecurityInfoW

- ea: `0x180003168`
- end: `0x180003174`
- name: `__imp_load_GetNamedSecurityInfoW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800030e9`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180003168`

## pseudocode

```c
__int64 load_GetNamedSecurityInfoW()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003168  lea     rax, __imp_GetNamedSecurityInfoW
0x18000316f  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
