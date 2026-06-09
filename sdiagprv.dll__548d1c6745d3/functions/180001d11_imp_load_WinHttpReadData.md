# __imp_load_WinHttpReadData

- ea: `0x180001d11`
- end: `0x180001d1d`
- name: `__imp_load_WinHttpReadData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c02`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x180001d11`

## pseudocode

```c
__int64 load_WinHttpReadData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001d11  lea     rax, __imp_WinHttpReadData
0x180001d18  jmp     __tailMerge_winhttp_dll
```
