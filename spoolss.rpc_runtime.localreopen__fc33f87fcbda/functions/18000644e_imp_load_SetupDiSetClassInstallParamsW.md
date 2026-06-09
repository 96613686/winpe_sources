# __imp_load_SetupDiSetClassInstallParamsW

- ea: `0x18000644e`
- end: `0x18000645a`
- name: `__imp_load_SetupDiSetClassInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180006399`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18000644e`

## pseudocode

```c
__int64 load_SetupDiSetClassInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000644e  lea     rax, __imp_SetupDiSetClassInstallParamsW
0x180006455  jmp     __tailMerge_setupapi_dll
```
