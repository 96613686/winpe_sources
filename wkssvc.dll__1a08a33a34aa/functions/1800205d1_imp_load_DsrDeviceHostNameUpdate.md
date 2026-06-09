# __imp_load_DsrDeviceHostNameUpdate

- ea: `0x1800205d1`
- end: `0x1800205dd`
- name: `__imp_load_DsrDeviceHostNameUpdate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180020552`

## import_xrefs

- `dsreg!DsrDeviceHostNameUpdate` at `0x1800205d1`

## pseudocode

```c
__int64 load_DsrDeviceHostNameUpdate()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x1800205d1  lea     rax, __imp_DsrDeviceHostNameUpdate
0x1800205d8  jmp     __tailMerge_dsreg_dll
```
