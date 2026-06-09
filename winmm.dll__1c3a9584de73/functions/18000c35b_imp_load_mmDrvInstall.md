# __imp_load_mmDrvInstall

- ea: `0x18000c35b`
- end: `0x18000c367`
- name: `__imp_load_mmDrvInstall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmDrvInstall` at `0x18000c35b`

## pseudocode

```c
__int64 load_mmDrvInstall()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c35b  lea     rax, __imp_mmDrvInstall
0x18000c362  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
