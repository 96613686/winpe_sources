# __imp_load_NgcCreateTicketForSmartCardVpn

- ea: `0x1800020df`
- end: `0x1800020eb`
- name: `__imp_load_NgcCreateTicketForSmartCardVpn`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002060`

## import_xrefs

- `cryptngc!NgcCreateTicketForSmartCardVpn` at `0x1800020df`

## pseudocode

```c
__int64 load_NgcCreateTicketForSmartCardVpn()
{
  return _tailMerge_cryptngc_dll();
}

```

## disassembly

```asm
0x1800020df  lea     rax, __imp_NgcCreateTicketForSmartCardVpn
0x1800020e6  jmp     __tailMerge_cryptngc_dll
```
