# __imp_load_LsaOpenPolicy

- ea: `0x18001fb96`
- end: `0x18001fba2`
- name: `__imp_load_LsaOpenPolicy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001fb17`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001fb96`

## pseudocode

```c
__int64 load_LsaOpenPolicy()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001fb96  lea     rax, __imp_LsaOpenPolicy
0x18001fb9d  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
