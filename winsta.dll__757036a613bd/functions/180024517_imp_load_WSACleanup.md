# __imp_load_WSACleanup

- ea: `0x180024517`
- end: `0x180024523`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180024462`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180024517`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x180024517  lea     rax, __imp_WSACleanup
0x18002451e  jmp     __tailMerge_ws2_32_dll
```
