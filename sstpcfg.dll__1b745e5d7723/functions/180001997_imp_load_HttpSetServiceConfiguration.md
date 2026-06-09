# __imp_load_HttpSetServiceConfiguration

- ea: `0x180001997`
- end: `0x1800019a3`
- name: `__imp_load_HttpSetServiceConfiguration`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800018d0`

## import_xrefs

- `HTTPAPI!HttpSetServiceConfiguration` at `0x180001997`

## pseudocode

```c
__int64 load_HttpSetServiceConfiguration()
{
  return _tailMerge_httpapi_dll();
}

```

## disassembly

```asm
0x180001997  lea     rax, __imp_HttpSetServiceConfiguration
0x18000199e  jmp     __tailMerge_httpapi_dll
```
