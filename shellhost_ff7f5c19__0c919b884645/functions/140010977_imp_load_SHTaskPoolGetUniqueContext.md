# __imp_load_SHTaskPoolGetUniqueContext

- ea: `0x140010977`
- end: `0x140010983`
- name: `__imp_load_SHTaskPoolGetUniqueContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1400108e6`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x140010977`

## pseudocode

```c
__int64 load_SHTaskPoolGetUniqueContext()
{
  return _tailMerge_api_ms_win_shcore_taskpool_l1_1_0_dll();
}

```

## disassembly

```asm
0x140010977  lea     rax, __imp_SHTaskPoolGetUniqueContext
0x14001097e  jmp     __tailMerge_api_ms_win_shcore_taskpool_l1_1_0_dll
```
