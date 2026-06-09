# __imp_load_OpenCluster

- ea: `0x140001ef5`
- end: `0x140001f01`
- name: `__imp_load_OpenCluster`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001cd0`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x140001ef5`

## pseudocode

```c
__int64 load_OpenCluster()
{
  return _tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x140001ef5  lea     rax, __imp_OpenCluster
0x140001efc  jmp     __tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll
```
