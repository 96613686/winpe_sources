# __imp_load_WinHttpOpen

- ea: `0x180001d35`
- end: `0x180001d41`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c02`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x180001d35`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001d35  lea     rax, __imp_WinHttpOpen
0x180001d3c  jmp     __tailMerge_winhttp_dll
```
