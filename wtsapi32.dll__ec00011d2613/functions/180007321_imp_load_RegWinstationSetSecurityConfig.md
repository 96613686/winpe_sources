# __imp_load_RegWinstationSetSecurityConfig

- ea: `0x180007321`
- end: `0x18000732d`
- name: `__imp_load_RegWinstationSetSecurityConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegWinstationSetSecurityConfig` at `0x180007321`

## pseudocode

```c
__int64 load_RegWinstationSetSecurityConfig()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x180007321  lea     rax, __imp_RegWinstationSetSecurityConfig
0x180007328  jmp     __tailMerge_regapi_dll
```
