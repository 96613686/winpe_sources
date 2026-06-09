# __imp_load_SHGetKnownFolderPath

- ea: `0x18000302b`
- end: `0x180003037`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f9a`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18000302b`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x18000302b  lea     rax, __imp_SHGetKnownFolderPath
0x180003032  jmp     __tailMerge_shell32_dll
```
