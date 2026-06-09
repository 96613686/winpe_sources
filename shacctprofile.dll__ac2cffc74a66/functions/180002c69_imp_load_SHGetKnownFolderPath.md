# __imp_load_SHGetKnownFolderPath

- ea: `0x180002c69`
- end: `0x180002c75`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002bea`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x180002c69`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c69  lea     rax, __imp_SHGetKnownFolderPath
0x180002c70  jmp     __tailMerge_shell32_dll
```
