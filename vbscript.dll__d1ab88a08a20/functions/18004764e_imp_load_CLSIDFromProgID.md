# __imp_load_CLSIDFromProgID

- ea: `0x18004764e`
- end: `0x18004765a`
- name: `__imp_load_CLSIDFromProgID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180047454`

## import_xrefs

- `OLE32!CLSIDFromProgID` at `0x18004764e`

## pseudocode

```c
__int64 load_CLSIDFromProgID()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18004764e  lea     rax, __imp_CLSIDFromProgID
0x180047655  jmp     __tailMerge_ole32_dll
```
