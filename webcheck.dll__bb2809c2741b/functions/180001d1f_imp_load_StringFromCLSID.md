# __imp_load_StringFromCLSID

- ea: `0x180001d1f`
- end: `0x180001d2b`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001bec`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180001d1f`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180001d1f  lea     rax, __imp_StringFromCLSID
0x180001d26  jmp     __tailMerge_ole32_dll
```
