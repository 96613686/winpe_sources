# __imp_load_SafeArrayCreateVector

- ea: `0x180001e98`
- end: `0x180001ea4`
- name: `__imp_load_SafeArrayCreateVector`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d46`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180001e98`

## pseudocode

```c
__int64 load_SafeArrayCreateVector()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001e98  lea     rax, __imp_SafeArrayCreateVector
0x180001e9f  jmp     __tailMerge_oleaut32_dll
```
