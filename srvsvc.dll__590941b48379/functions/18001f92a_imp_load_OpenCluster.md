# __imp_load_OpenCluster

- ea: `0x18001f92a`
- end: `0x18001f936`
- name: `__imp_load_OpenCluster`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f851`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18001f92a`

## pseudocode

```c
__int64 load_OpenCluster()
{
  return _tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001f92a  lea     rax, __imp_OpenCluster
0x18001f931  jmp     __tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll
```
