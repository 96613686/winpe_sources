# __imp_load_LsaOpenPolicy

- ea: `0x180002fb0`
- end: `0x180002fbc`
- name: `__imp_load_LsaOpenPolicy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002f31`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180002fb0`

## pseudocode

```c
__int64 load_LsaOpenPolicy()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002fb0  lea     rax, __imp_LsaOpenPolicy
0x180002fb7  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
