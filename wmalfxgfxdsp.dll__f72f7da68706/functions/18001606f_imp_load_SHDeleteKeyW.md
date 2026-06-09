# __imp_load_SHDeleteKeyW

- ea: `0x18001606f`
- end: `0x18001607b`
- name: `__imp_load_SHDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180015ff0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18001606f`

## pseudocode

```c
__int64 load_SHDeleteKeyW()
{
  return _tailMerge_api_ms_win_shcore_registry_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001606f  lea     rax, __imp_SHDeleteKeyW
0x180016076  jmp     __tailMerge_api_ms_win_shcore_registry_l1_1_0_dll
```
