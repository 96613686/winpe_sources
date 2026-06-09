# __imp_load_CLSIDFromString

- ea: `0x180047684`
- end: `0x180047690`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180047454`

## import_xrefs

- `OLE32!CLSIDFromString` at `0x180047684`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180047684  lea     rax, __imp_CLSIDFromString
0x18004768b  jmp     __tailMerge_ole32_dll
```
