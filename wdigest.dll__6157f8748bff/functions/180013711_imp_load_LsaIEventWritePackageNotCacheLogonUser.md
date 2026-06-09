# __imp_load_LsaIEventWritePackageNotCacheLogonUser

- ea: `0x180013711`
- end: `0x18001371d`
- name: `__imp_load_LsaIEventWritePackageNotCacheLogonUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013692`

## import_xrefs

- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x180013711`

## pseudocode

```c
__int64 load_LsaIEventWritePackageNotCacheLogonUser()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x180013711  lea     rax, __imp_LsaIEventWritePackageNotCacheLogonUser
0x180013718  jmp     __tailMerge_lsasrv_dll
```
