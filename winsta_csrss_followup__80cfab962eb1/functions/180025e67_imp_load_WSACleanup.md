# __imp_load_WSACleanup

- ea: `0x180025e67`
- end: `0x180025e73`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180025db2`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180025e67`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x180025e67  lea     rax, __imp_WSACleanup
0x180025e6e  jmp     __tailMerge_ws2_32_dll
```
