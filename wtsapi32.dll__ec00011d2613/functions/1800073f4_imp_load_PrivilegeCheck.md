# __imp_load_PrivilegeCheck

- ea: `0x1800073f4`
- end: `0x180007400`
- name: `__imp_load_PrivilegeCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007375`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800073f4`

## pseudocode

```c
__int64 load_PrivilegeCheck()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800073f4  lea     rax, __imp_PrivilegeCheck
0x1800073fb  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
