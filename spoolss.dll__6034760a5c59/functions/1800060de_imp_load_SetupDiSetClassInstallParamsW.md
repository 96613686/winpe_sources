# __imp_load_SetupDiSetClassInstallParamsW

- ea: `0x1800060de`
- end: `0x1800060ea`
- name: `__imp_load_SetupDiSetClassInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180006029`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800060de`

## pseudocode

```c
__int64 load_SetupDiSetClassInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x1800060de  lea     rax, __imp_SetupDiSetClassInstallParamsW
0x1800060e5  jmp     __tailMerge_setupapi_dll
```
