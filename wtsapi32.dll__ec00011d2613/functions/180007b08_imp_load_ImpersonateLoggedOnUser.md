# __imp_load_ImpersonateLoggedOnUser

- ea: `0x180007b08`
- end: `0x180007b14`
- name: `__imp_load_ImpersonateLoggedOnUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007375`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007b08`

## pseudocode

```c
__int64 load_ImpersonateLoggedOnUser()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180007b08  lea     rax, __imp_ImpersonateLoggedOnUser
0x180007b0f  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
