# __imp_load_StartServiceW

- ea: `0x180003415`
- end: `0x180003421`
- name: `__imp_load_StartServiceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003384`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180003415`

## pseudocode

```c
__int64 load_StartServiceW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003415  lea     rax, __imp_StartServiceW
0x18000341c  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
