# __imp_load_mmioInstallIOProcA

- ea: `0x18000c3b5`
- end: `0x18000c3c1`
- name: `__imp_load_mmioInstallIOProcA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioInstallIOProcA` at `0x18000c3b5`

## pseudocode

```c
__int64 load_mmioInstallIOProcA()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c3b5  lea     rax, __imp_mmioInstallIOProcA
0x18000c3bc  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
