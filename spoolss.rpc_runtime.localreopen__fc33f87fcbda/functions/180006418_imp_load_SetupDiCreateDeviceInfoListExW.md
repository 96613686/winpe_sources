# __imp_load_SetupDiCreateDeviceInfoListExW

- ea: `0x180006418`
- end: `0x180006424`
- name: `__imp_load_SetupDiCreateDeviceInfoListExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180006399`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x180006418`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoListExW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180006418  lea     rax, __imp_SetupDiCreateDeviceInfoListExW
0x18000641f  jmp     __tailMerge_setupapi_dll
```
