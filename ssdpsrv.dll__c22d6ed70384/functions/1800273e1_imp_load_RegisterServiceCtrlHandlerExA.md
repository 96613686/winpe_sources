# __imp_load_RegisterServiceCtrlHandlerExA

- ea: `0x1800273e1`
- end: `0x1800273ed`
- name: `__imp_load_RegisterServiceCtrlHandlerExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180027362`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x1800273e1`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerExA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800273e1  lea     rax, __imp_RegisterServiceCtrlHandlerExA
0x1800273e8  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
