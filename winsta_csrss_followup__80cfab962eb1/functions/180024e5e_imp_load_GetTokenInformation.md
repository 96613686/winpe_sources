# __imp_load_GetTokenInformation

- ea: `0x180024e5e`
- end: `0x180024e6a`
- name: `__imp_load_GetTokenInformation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024ddf`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024e5e`

## pseudocode

```c
__int64 load_GetTokenInformation()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180024e5e  lea     rax, __imp_GetTokenInformation
0x180024e65  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
