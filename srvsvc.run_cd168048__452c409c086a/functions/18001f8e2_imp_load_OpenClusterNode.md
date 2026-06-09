# __imp_load_OpenClusterNode

- ea: `0x18001f8e2`
- end: `0x18001f8ee`
- name: `__imp_load_OpenClusterNode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f851`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18001f8e2`

## pseudocode

```c
__int64 load_OpenClusterNode()
{
  return _tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001f8e2  lea     rax, __imp_OpenClusterNode
0x18001f8e9  jmp     __tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll
```
