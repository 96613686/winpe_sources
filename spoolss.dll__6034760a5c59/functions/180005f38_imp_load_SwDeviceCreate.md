# __imp_load_SwDeviceCreate

- ea: `0x180005f38`
- end: `0x180005f44`
- name: `__imp_load_SwDeviceCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005ea7`

## import_xrefs

- `CFGMGR32!SwDeviceCreate` at `0x180005f38`

## pseudocode

```c
__int64 load_SwDeviceCreate()
{
  return _tailMerge_cfgmgr32_dll();
}

```

## disassembly

```asm
0x180005f38  lea     rax, __imp_SwDeviceCreate
0x180005f3f  jmp     __tailMerge_cfgmgr32_dll
```
