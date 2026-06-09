# __imp_load_SHCreateItemFromParsingName

- ea: `0x180002c7b`
- end: `0x180002c87`
- name: `__imp_load_SHCreateItemFromParsingName`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002bea`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180002c7b`

## pseudocode

```c
__int64 load_SHCreateItemFromParsingName()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c7b  lea     rax, __imp_SHCreateItemFromParsingName
0x180002c82  jmp     __tailMerge_shell32_dll
```
