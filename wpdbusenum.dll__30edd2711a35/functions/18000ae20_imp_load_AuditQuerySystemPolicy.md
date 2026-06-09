# __imp_load_AuditQuerySystemPolicy

- ea: `0x18000ae20`
- end: `0x18000ae2c`
- name: `__imp_load_AuditQuerySystemPolicy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ad8f`

## import_xrefs

- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18000ae20`

## pseudocode

```c
__int64 load_AuditQuerySystemPolicy()
{
  return _tailMerge_api_ms_win_security_audit_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ae20  lea     rax, __imp_AuditQuerySystemPolicy
0x18000ae27  jmp     __tailMerge_api_ms_win_security_audit_l1_1_0_dll
```
