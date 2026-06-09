# __imp_load_CoImpersonateClient

- ea: `0x1800024a3`
- end: `0x1800024af`
- name: `__imp_load_CoImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002328`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800024a3`

## pseudocode

```c
__int64 load_CoImpersonateClient()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800024a3  lea     rax, __imp_CoImpersonateClient
0x1800024aa  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
