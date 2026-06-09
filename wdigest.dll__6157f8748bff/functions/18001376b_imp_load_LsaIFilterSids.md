# __imp_load_LsaIFilterSids

- ea: `0x18001376b`
- end: `0x180013777`
- name: `__imp_load_LsaIFilterSids`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180013692`

## import_xrefs

- `LSASRV!LsaIFilterSids` at `0x18001376b`

## pseudocode

```c
__int64 load_LsaIFilterSids()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x18001376b  lea     rax, __imp_LsaIFilterSids
0x180013772  jmp     __tailMerge_lsasrv_dll
```
