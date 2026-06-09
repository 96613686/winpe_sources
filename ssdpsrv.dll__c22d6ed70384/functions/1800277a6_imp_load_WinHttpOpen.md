# __imp_load_WinHttpOpen

- ea: `0x1800277a6`
- end: `0x1800277b2`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002764f`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x1800277a6`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800277a6  lea     rax, __imp_WinHttpOpen
0x1800277ad  jmp     __tailMerge_winhttp_dll
```
