# __imp_load_RegisterServiceCtrlHandlerW

- ea: `0x1400056a9`
- end: `0x1400056b5`
- name: `__imp_load_RegisterServiceCtrlHandlerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x14000562a`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1400056a9`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerW()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400056a9  lea     rax, __imp_RegisterServiceCtrlHandlerW
0x1400056b0  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
