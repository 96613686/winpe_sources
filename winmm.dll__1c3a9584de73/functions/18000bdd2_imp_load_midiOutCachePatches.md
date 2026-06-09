# __imp_load_midiOutCachePatches

- ea: `0x18000bdd2`
- end: `0x18000bdde`
- name: `__imp_load_midiOutCachePatches`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiOutCachePatches` at `0x18000bdd2`

## pseudocode

```c
__int64 load_midiOutCachePatches()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000bdd2  lea     rax, __imp_midiOutCachePatches
0x18000bdd9  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
