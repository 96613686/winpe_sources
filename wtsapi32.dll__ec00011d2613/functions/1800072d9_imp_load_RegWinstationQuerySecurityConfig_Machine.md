# __imp_load_RegWinstationQuerySecurityConfig_Machine

- ea: `0x1800072d9`
- end: `0x1800072e5`
- name: `__imp_load_RegWinstationQuerySecurityConfig_Machine`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegWinstationQuerySecurityConfig_Machine` at `0x1800072d9`

## pseudocode

```c
__int64 load_RegWinstationQuerySecurityConfig_Machine()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x1800072d9  lea     rax, __imp_RegWinstationQuerySecurityConfig_Machine
0x1800072e0  jmp     __tailMerge_regapi_dll
```
