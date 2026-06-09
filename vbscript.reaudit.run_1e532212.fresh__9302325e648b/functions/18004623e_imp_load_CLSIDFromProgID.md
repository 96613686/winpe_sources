# __imp_load_CLSIDFromProgID

- ea: `0x18004623e`
- end: `0x18004624a`
- name: `__imp_load_CLSIDFromProgID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180046044`

## import_xrefs

- `OLE32!CLSIDFromProgID` at `0x18004623e`

## pseudocode

```c
__int64 load_CLSIDFromProgID()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18004623e  lea     rax, __imp_CLSIDFromProgID
0x180046245  jmp     __tailMerge_ole32_dll
```
