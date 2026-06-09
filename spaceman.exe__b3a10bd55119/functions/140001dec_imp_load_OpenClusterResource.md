# __imp_load_OpenClusterResource

- ea: `0x140001dec`
- end: `0x140001df8`
- name: `__imp_load_OpenClusterResource`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001cd0`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x140001dec`

## pseudocode

```c
__int64 load_OpenClusterResource()
{
  return _tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x140001dec  lea     rax, __imp_OpenClusterResource
0x140001df3  jmp     __tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll
```
