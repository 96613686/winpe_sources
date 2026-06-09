# __imp_load_RegOpenKeyW

- ea: `0x18001f796`
- end: `0x18001f7a2`
- name: `__imp_load_RegOpenKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18001f717`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18001f796`

## pseudocode

```c
__int64 load_RegOpenKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x18001f796  lea     rax, __imp_RegOpenKeyW
0x18001f79d  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
