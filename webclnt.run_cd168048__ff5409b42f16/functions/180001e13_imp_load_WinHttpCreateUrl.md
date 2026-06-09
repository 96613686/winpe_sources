# __imp_load_WinHttpCreateUrl

- ea: `0x180001e13`
- end: `0x180001e1f`
- name: `__imp_load_WinHttpCreateUrl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c86`

## import_xrefs

- `WINHTTP!WinHttpCreateUrl` at `0x180001e13`

## pseudocode

```c
__int64 load_WinHttpCreateUrl()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001e13  lea     rax, __imp_WinHttpCreateUrl
0x180001e1a  jmp     __tailMerge_winhttp_dll
```
