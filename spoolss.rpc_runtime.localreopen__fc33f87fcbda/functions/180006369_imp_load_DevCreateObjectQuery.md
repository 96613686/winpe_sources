# __imp_load_DevCreateObjectQuery

- ea: `0x180006369`
- end: `0x180006375`
- name: `__imp_load_DevCreateObjectQuery`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800062ea`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180006369`

## pseudocode

```c
__int64 load_DevCreateObjectQuery()
{
  return _tailMerge_api_ms_win_devices_query_l1_1_0_dll();
}

```

## disassembly

```asm
0x180006369  lea     rax, __imp_DevCreateObjectQuery
0x180006370  jmp     __tailMerge_api_ms_win_devices_query_l1_1_0_dll
```
