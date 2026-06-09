# __imp_load_EnumServicesStatusExW

- ea: `0x180003aba`
- end: `0x180003ac6`
- name: `__imp_load_EnumServicesStatusExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003a3b`

## import_xrefs

- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180003aba`

## pseudocode

```c
__int64 load_EnumServicesStatusExW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_1_dll();
}

```

## disassembly

```asm
0x180003aba  lea     rax, __imp_EnumServicesStatusExW
0x180003ac1  jmp     __tailMerge_api_ms_win_service_core_l1_1_1_dll
```
