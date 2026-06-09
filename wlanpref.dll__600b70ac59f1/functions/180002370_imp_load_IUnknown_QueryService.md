# __imp_load_IUnknown_QueryService

- ea: `0x180002370`
- end: `0x18000237c`
- name: `__imp_load_IUnknown_QueryService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022df`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180002370`

## pseudocode

```c
__int64 load_IUnknown_QueryService()
{
  return _tailMerge_api_ms_win_shcore_comhelpers_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002370  lea     rax, __imp_IUnknown_QueryService
0x180002377  jmp     __tailMerge_api_ms_win_shcore_comhelpers_l1_1_0_dll
```
