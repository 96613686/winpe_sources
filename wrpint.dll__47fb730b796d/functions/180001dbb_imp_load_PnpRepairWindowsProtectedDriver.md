# __imp_load_PnpRepairWindowsProtectedDriver

- ea: `0x180001dbb`
- end: `0x180001dc7`
- name: `__imp_load_PnpRepairWindowsProtectedDriver`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180001d18`

## import_xrefs

- `setupapi!PnpRepairWindowsProtectedDriver` at `0x180001dbb`

## pseudocode

```c
__int64 load_PnpRepairWindowsProtectedDriver()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180001dbb  lea     rax, __imp_PnpRepairWindowsProtectedDriver
0x180001dc2  jmp     __tailMerge_setupapi_dll
```
