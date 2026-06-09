# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x18000abd8`
- end: `0x18000abe4`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000abd8`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000abd8  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x18000abdf  jmp     __tailMerge_setupapi_dll
```
