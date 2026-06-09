# __imp_load_CoImpersonateClient

- ea: `0x18001b468`
- end: `0x18001b474`
- name: `__imp_load_CoImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001b100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001b468`

## pseudocode

```c
__int64 load_CoImpersonateClient()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001b468  lea     rax, __imp_CoImpersonateClient
0x18001b46f  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
