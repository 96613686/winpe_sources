# __imp_load_RegCreateKeyW

- ea: `0x180015fe4`
- end: `0x180015ff0`
- name: `__imp_load_RegCreateKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180015f65`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180015fe4`

## pseudocode

```c
__int64 load_RegCreateKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x180015fe4  lea     rax, __imp_RegCreateKeyW
0x180015feb  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
