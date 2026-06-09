# __imp_load_DsrDeviceHostNameUpdate

- ea: `0x18001ee21`
- end: `0x18001ee2d`
- name: `__imp_load_DsrDeviceHostNameUpdate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18001eda2`

## import_xrefs

- `dsreg!DsrDeviceHostNameUpdate` at `0x18001ee21`

## pseudocode

```c
__int64 load_DsrDeviceHostNameUpdate()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x18001ee21  lea     rax, __imp_DsrDeviceHostNameUpdate
0x18001ee28  jmp     __tailMerge_dsreg_dll
```
