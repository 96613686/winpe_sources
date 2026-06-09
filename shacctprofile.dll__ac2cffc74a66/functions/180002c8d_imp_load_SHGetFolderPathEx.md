# __imp_load_SHGetFolderPathEx

- ea: `0x180002c8d`
- end: `0x180002c99`
- name: `__imp_load_SHGetFolderPathEx`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002bea`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180002c8d`

## pseudocode

```c
__int64 load_SHGetFolderPathEx()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c8d  lea     rax, __imp_SHGetFolderPathEx
0x180002c94  jmp     __tailMerge_shell32_dll
```
