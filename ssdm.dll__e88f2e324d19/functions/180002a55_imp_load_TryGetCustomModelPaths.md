# __imp_load_TryGetCustomModelPaths

- ea: `0x180002a55`
- end: `0x180002a61`
- name: `__imp_load_TryGetCustomModelPaths`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800029d6`

## import_xrefs

- `ext-ms-win-audiocore-spatial-l1-1-0!TryGetCustomModelPaths` at `0x180002a55`

## pseudocode

```c
__int64 load_TryGetCustomModelPaths()
{
  return _tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002a55  lea     rax, __imp_TryGetCustomModelPaths
0x180002a5c  jmp     __tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll
```
