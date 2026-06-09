# __imp_load_ClusterRegOpenKey

- ea: `0x140001ee3`
- end: `0x140001eef`
- name: `__imp_load_ClusterRegOpenKey`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140001d6d`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegOpenKey` at `0x140001ee3`

## pseudocode

```c
__int64 load_ClusterRegOpenKey()
{
  return _tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll();
}

```

## disassembly

```asm
0x140001ee3  lea     rax, __imp_ClusterRegOpenKey
0x140001eea  jmp     __tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll
```
