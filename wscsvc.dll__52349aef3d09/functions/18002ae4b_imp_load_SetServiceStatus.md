# __imp_load_SetServiceStatus

- ea: `0x18002ae4b`
- end: `0x18002ae57`
- name: `__imp_load_SetServiceStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002adcc`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002ae4b`

## pseudocode

```c
__int64 load_SetServiceStatus()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002ae4b  lea     rax, __imp_SetServiceStatus
0x18002ae52  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
