# __imp_load_DuplicateToken

- ea: `0x1800099bd`
- end: `0x1800099c9`
- name: `__imp_load_DuplicateToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000992c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800099bd`

## pseudocode

```c
__int64 load_DuplicateToken()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800099bd  lea     rax, __imp_DuplicateToken
0x1800099c4  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
