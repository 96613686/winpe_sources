# __imp_load_SetupDiOpenDeviceInterfaceW

- ea: `0x18000abea`
- end: `0x18000abf6`
- name: `__imp_load_SetupDiOpenDeviceInterfaceW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18000abea`

## pseudocode

```c
__int64 load_SetupDiOpenDeviceInterfaceW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000abea  lea     rax, __imp_SetupDiOpenDeviceInterfaceW
0x18000abf1  jmp     __tailMerge_setupapi_dll
```
