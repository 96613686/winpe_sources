# __imp_load_HttpQueryServiceConfiguration

- ea: `0x180001973`
- end: `0x18000197f`
- name: `__imp_load_HttpQueryServiceConfiguration`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800018d0`

## import_xrefs

- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180001973`

## pseudocode

```c
__int64 load_HttpQueryServiceConfiguration()
{
  return _tailMerge_httpapi_dll();
}

```

## disassembly

```asm
0x180001973  lea     rax, __imp_HttpQueryServiceConfiguration
0x18000197a  jmp     __tailMerge_httpapi_dll
```
