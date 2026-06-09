# __imp_load_LsaIEventWritePackageNoCredential

- ea: `0x180013747`
- end: `0x180013753`
- name: `__imp_load_LsaIEventWritePackageNoCredential`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013692`

## import_xrefs

- `LSASRV!LsaIEventWritePackageNoCredential` at `0x180013747`

## pseudocode

```c
__int64 load_LsaIEventWritePackageNoCredential()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x180013747  lea     rax, __imp_LsaIEventWritePackageNoCredential
0x18001374e  jmp     __tailMerge_lsasrv_dll
```
