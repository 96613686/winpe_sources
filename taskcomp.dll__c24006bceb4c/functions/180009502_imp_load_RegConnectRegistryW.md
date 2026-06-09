# __imp_load_RegConnectRegistryW

- ea: `0x180009502`
- end: `0x18000950e`
- name: `__imp_load_RegConnectRegistryW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180009483`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180009502`

## pseudocode

```c
__int64 load_RegConnectRegistryW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x180009502  lea     rax, __imp_RegConnectRegistryW
0x180009509  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
