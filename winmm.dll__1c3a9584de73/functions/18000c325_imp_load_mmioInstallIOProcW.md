# __imp_load_mmioInstallIOProcW

- ea: `0x18000c325`
- end: `0x18000c331`
- name: `__imp_load_mmioInstallIOProcW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioInstallIOProcW` at `0x18000c325`

## pseudocode

```c
__int64 load_mmioInstallIOProcW()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c325  lea     rax, __imp_mmioInstallIOProcW
0x18000c32c  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
