# __imp_load_WinHttpOpenRequest

- ea: `0x180027782`
- end: `0x18002778e`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002764f`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x180027782`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180027782  lea     rax, __imp_WinHttpOpenRequest
0x180027789  jmp     __tailMerge_winhttp_dll
```
