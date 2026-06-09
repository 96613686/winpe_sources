# __imp_load_HttpDeleteServiceConfiguration

- ea: `0x18000194f`
- end: `0x18000195b`
- name: `__imp_load_HttpDeleteServiceConfiguration`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800018d0`

## import_xrefs

- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x18000194f`

## pseudocode

```c
__int64 load_HttpDeleteServiceConfiguration()
{
  return _tailMerge_httpapi_dll();
}

```

## disassembly

```asm
0x18000194f  lea     rax, __imp_HttpDeleteServiceConfiguration
0x180001956  jmp     __tailMerge_httpapi_dll
```
