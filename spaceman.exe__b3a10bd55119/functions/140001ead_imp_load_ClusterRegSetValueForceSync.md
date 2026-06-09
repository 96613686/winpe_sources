# __imp_load_ClusterRegSetValueForceSync

- ea: `0x140001ead`
- end: `0x140001eb9`
- name: `__imp_load_ClusterRegSetValueForceSync`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140001d6d`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegSetValueForceSync` at `0x140001ead`

## pseudocode

```c
__int64 load_ClusterRegSetValueForceSync()
{
  return _tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll();
}

```

## disassembly

```asm
0x140001ead  lea     rax, __imp_ClusterRegSetValueForceSync
0x140001eb4  jmp     __tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll
```
