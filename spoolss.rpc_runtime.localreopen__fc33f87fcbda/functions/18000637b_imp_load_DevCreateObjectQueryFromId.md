# __imp_load_DevCreateObjectQueryFromId

- ea: `0x18000637b`
- end: `0x180006387`
- name: `__imp_load_DevCreateObjectQueryFromId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800062ea`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x18000637b`

## pseudocode

```c
__int64 load_DevCreateObjectQueryFromId()
{
  return _tailMerge_api_ms_win_devices_query_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000637b  lea     rax, __imp_DevCreateObjectQueryFromId
0x180006382  jmp     __tailMerge_api_ms_win_devices_query_l1_1_0_dll
```
