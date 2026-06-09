# __imp_load_HvciGetConfig

- ea: `0x18002b14f`
- end: `0x18002b15b`
- name: `__imp_load_HvciGetConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002b0ac`

## import_xrefs

- `VbsApi!HvciGetConfig` at `0x18002b14f`

## pseudocode

```c
__int64 load_HvciGetConfig()
{
  return _tailMerge_vbsapi_dll();
}

```

## disassembly

```asm
0x18002b14f  lea     rax, __imp_HvciGetConfig
0x18002b156  jmp     __tailMerge_vbsapi_dll
```
