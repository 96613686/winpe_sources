# __imp_load_SamIFreeSidAndAttributesList

- ea: `0x18001396b`
- end: `0x180013977`
- name: `__imp_load_SamIFreeSidAndAttributesList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180013892`

## import_xrefs

- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18001396b`

## pseudocode

```c
__int64 load_SamIFreeSidAndAttributesList()
{
  return _tailMerge_samsrv_dll();
}

```

## disassembly

```asm
0x18001396b  lea     rax, __imp_SamIFreeSidAndAttributesList
0x180013972  jmp     __tailMerge_samsrv_dll
```
