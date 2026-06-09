# __imp_load_FreeSid

- ea: `0x180002340`
- end: `0x18000234c`
- name: `__imp_load_FreeSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000221f`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x180002340`

## pseudocode

```c
__int64 load_FreeSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002340  lea     rax, __imp_FreeSid
0x180002347  jmp     __tailMerge_advapi32_dll
```
