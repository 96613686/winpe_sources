# __imp_load_SetupDiOpenDeviceInfoW

- ea: `0x1800060ba`
- end: `0x1800060c6`
- name: `__imp_load_SetupDiOpenDeviceInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180006029`

## import_xrefs

- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800060ba`

## pseudocode

```c
__int64 load_SetupDiOpenDeviceInfoW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x1800060ba  lea     rax, __imp_SetupDiOpenDeviceInfoW
0x1800060c1  jmp     __tailMerge_setupapi_dll
```
