# __imp_load_QueryServiceConfigW

- ea: `0x180005e9e`
- end: `0x180005eaa`
- name: `__imp_load_QueryServiceConfigW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005d82`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180005e9e`

## pseudocode

```c
__int64 load_QueryServiceConfigW()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x180005e9e  lea     rax, __imp_QueryServiceConfigW
0x180005ea5  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
