# __imp_load_CLSIDFromProgIDEx

- ea: `0x180047660`
- end: `0x18004766c`
- name: `__imp_load_CLSIDFromProgIDEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180047454`

## import_xrefs

- `OLE32!CLSIDFromProgIDEx` at `0x180047660`

## pseudocode

```c
__int64 load_CLSIDFromProgIDEx()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180047660  lea     rax, __imp_CLSIDFromProgIDEx
0x180047667  jmp     __tailMerge_ole32_dll
```
