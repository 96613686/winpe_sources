# __imp_load_RegisterServiceCtrlHandlerW

- ea: `0x140005a89`
- end: `0x140005a95`
- name: `__imp_load_RegisterServiceCtrlHandlerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140005a0a`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x140005a89`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerW()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x140005a89  lea     rax, __imp_RegisterServiceCtrlHandlerW
0x140005a90  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
