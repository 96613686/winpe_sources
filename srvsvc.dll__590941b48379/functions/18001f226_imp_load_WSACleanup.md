# __imp_load_WSACleanup

- ea: `0x18001f226`
- end: `0x18001f232`
- name: `__imp_load_WSACleanup`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001f171`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18001f226`

## pseudocode

```c
__int64 load_WSACleanup()
{
  return _tailMerge_ws2_32_dll();
}

```

## disassembly

```asm
0x18001f226  lea     rax, __imp_WSACleanup
0x18001f22d  jmp     __tailMerge_ws2_32_dll
```
