# __imp_load_LsaIEventWritePackageNotCacheLogonUser

- ea: `0x18000c6dd`
- end: `0x18000c6e9`
- name: `__imp_load_LsaIEventWritePackageNotCacheLogonUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c65e`

## import_xrefs

- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x18000c6dd`

## pseudocode

```c
__int64 load_LsaIEventWritePackageNotCacheLogonUser()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x18000c6dd  lea     rax, __imp_LsaIEventWritePackageNotCacheLogonUser
0x18000c6e4  jmp     __tailMerge_lsasrv_dll
```
