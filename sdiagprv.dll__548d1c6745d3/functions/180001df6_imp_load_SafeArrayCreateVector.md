# __imp_load_SafeArrayCreateVector

- ea: `0x180001df6`
- end: `0x180001e02`
- name: `__imp_load_SafeArrayCreateVector`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019f0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180001df6`

## pseudocode

```c
__int64 load_SafeArrayCreateVector()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001df6  lea     rax, __imp_SafeArrayCreateVector
0x180001dfd  jmp     __tailMerge_oleaut32_dll
```
