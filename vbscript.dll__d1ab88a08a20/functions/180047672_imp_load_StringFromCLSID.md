# __imp_load_StringFromCLSID

- ea: `0x180047672`
- end: `0x18004767e`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180047454`

## import_xrefs

- `OLE32!StringFromCLSID` at `0x180047672`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180047672  lea     rax, __imp_StringFromCLSID
0x180047679  jmp     __tailMerge_ole32_dll
```
