# __imp_load_SHCreateItemFromParsingName

- ea: `0x18000303d`
- end: `0x180003049`
- name: `__imp_load_SHCreateItemFromParsingName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f9a`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18000303d`

## pseudocode

```c
__int64 load_SHCreateItemFromParsingName()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x18000303d  lea     rax, __imp_SHCreateItemFromParsingName
0x180003044  jmp     __tailMerge_shell32_dll
```
