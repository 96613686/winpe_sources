# __imp_load_SetupDiGetDeviceRegistryPropertyW

- ea: `0x18000ac0e`
- end: `0x18000ac1a`
- name: `__imp_load_SetupDiGetDeviceRegistryPropertyW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000ac0e`

## pseudocode

```c
__int64 load_SetupDiGetDeviceRegistryPropertyW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000ac0e  lea     rax, __imp_SetupDiGetDeviceRegistryPropertyW
0x18000ac15  jmp     __tailMerge_setupapi_dll
```
