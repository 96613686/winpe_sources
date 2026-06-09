# __imp_load_DsGetDcOpenW

- ea: `0x180035191`
- end: `0x18003519d`
- name: `__imp_load_DsGetDcOpenW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180035100`

## import_xrefs

- `logoncli!DsGetDcOpenW` at `0x180035191`

## pseudocode

```c
__int64 load_DsGetDcOpenW()
{
  return _tailMerge_logoncli_dll();
}

```

## disassembly

```asm
0x180035191  lea     rax, __imp_DsGetDcOpenW
0x180035198  jmp     __tailMerge_logoncli_dll
```
