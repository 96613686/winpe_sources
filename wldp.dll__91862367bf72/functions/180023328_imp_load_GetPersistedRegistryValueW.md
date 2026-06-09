# __imp_load_GetPersistedRegistryValueW

- ea: `0x180023328`
- end: `0x180023334`
- name: `__imp_load_GetPersistedRegistryValueW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800232a9`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x180023328`

## pseudocode

```c
__int64 load_GetPersistedRegistryValueW()
{
  return _tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll();
}

```

## disassembly

```asm
0x180023328  lea     rax, __imp_GetPersistedRegistryValueW
0x18002332f  jmp     __tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll
```
