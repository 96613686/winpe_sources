# __imp_load_CoImpersonateClient

- ea: `0x1800027dc`
- end: `0x1800027e8`
- name: `__imp_load_CoImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002271`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800027dc`

## pseudocode

```c
__int64 load_CoImpersonateClient()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800027dc  lea     rax, __imp_CoImpersonateClient
0x1800027e3  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
