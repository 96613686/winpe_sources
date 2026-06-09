# __imp_load_QueryServiceConfigW

- ea: `0x18001ed38`
- end: `0x18001ed44`
- name: `__imp_load_QueryServiceConfigW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001e9c2`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001ed38`

## pseudocode

```c
__int64 load_QueryServiceConfigW()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x18001ed38  lea     rax, __imp_QueryServiceConfigW
0x18001ed3f  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
