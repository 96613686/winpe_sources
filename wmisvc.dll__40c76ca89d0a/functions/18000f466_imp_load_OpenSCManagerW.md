# __imp_load_OpenSCManagerW

- ea: `0x18000f466`
- end: `0x18000f472`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000f3e7`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f466`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f466  lea     rax, __imp_OpenSCManagerW
0x18000f46d  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
