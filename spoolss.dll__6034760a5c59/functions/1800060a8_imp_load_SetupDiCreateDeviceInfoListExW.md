# __imp_load_SetupDiCreateDeviceInfoListExW

- ea: `0x1800060a8`
- end: `0x1800060b4`
- name: `__imp_load_SetupDiCreateDeviceInfoListExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180006029`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1800060a8`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoListExW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x1800060a8  lea     rax, __imp_SetupDiCreateDeviceInfoListExW
0x1800060af  jmp     __tailMerge_setupapi_dll
```
