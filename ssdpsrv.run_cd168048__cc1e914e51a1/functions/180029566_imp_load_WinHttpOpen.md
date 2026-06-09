# __imp_load_WinHttpOpen

- ea: `0x180029566`
- end: `0x180029572`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002940f`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x180029566`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180029566  lea     rax, __imp_WinHttpOpen
0x18002956d  jmp     __tailMerge_winhttp_dll
```
