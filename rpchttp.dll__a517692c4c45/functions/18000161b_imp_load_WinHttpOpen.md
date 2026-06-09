# __imp_load_WinHttpOpen

- ea: `0x18000161b`
- end: `0x180001627`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000159c`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x18000161b`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18000161b  lea     rax, __imp_WinHttpOpen
0x180001622  jmp     __tailMerge_winhttp_dll
```
