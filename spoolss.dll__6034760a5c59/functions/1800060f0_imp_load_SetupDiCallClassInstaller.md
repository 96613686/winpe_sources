# __imp_load_SetupDiCallClassInstaller

- ea: `0x1800060f0`
- end: `0x1800060fc`
- name: `__imp_load_SetupDiCallClassInstaller`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180006029`

## import_xrefs

- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800060f0`

## pseudocode

```c
__int64 load_SetupDiCallClassInstaller()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x1800060f0  lea     rax, __imp_SetupDiCallClassInstaller
0x1800060f7  jmp     __tailMerge_setupapi_dll
```
