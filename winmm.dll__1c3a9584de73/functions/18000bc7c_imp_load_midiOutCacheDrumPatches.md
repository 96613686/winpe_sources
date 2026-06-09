# __imp_load_midiOutCacheDrumPatches

- ea: `0x18000bc7c`
- end: `0x18000bc88`
- name: `__imp_load_midiOutCacheDrumPatches`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiOutCacheDrumPatches` at `0x18000bc7c`

## pseudocode

```c
__int64 load_midiOutCacheDrumPatches()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000bc7c  lea     rax, __imp_midiOutCacheDrumPatches
0x18000bc83  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
