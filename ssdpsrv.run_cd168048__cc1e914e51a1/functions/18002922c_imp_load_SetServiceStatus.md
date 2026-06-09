# __imp_load_SetServiceStatus

- ea: `0x18002922c`
- end: `0x180029238`
- name: `__imp_load_SetServiceStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800291ad`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002922c`

## pseudocode

```c
__int64 load_SetServiceStatus()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002922c  lea     rax, __imp_SetServiceStatus
0x180029233  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
