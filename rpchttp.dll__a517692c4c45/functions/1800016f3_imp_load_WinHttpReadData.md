# __imp_load_WinHttpReadData

- ea: `0x1800016f3`
- end: `0x1800016ff`
- name: `__imp_load_WinHttpReadData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000159c`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x1800016f3`

## pseudocode

```c
__int64 load_WinHttpReadData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800016f3  lea     rax, __imp_WinHttpReadData
0x1800016fa  jmp     __tailMerge_winhttp_dll
```
