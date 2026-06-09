# __imp_load_SwDeviceCreate

- ea: `0x1800062a8`
- end: `0x1800062b4`
- name: `__imp_load_SwDeviceCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006217`

## import_xrefs

- `CFGMGR32!SwDeviceCreate` at `0x1800062a8`

## pseudocode

```c
__int64 load_SwDeviceCreate()
{
  return _tailMerge_cfgmgr32_dll();
}

```

## disassembly

```asm
0x1800062a8  lea     rax, __imp_SwDeviceCreate
0x1800062af  jmp     __tailMerge_cfgmgr32_dll
```
