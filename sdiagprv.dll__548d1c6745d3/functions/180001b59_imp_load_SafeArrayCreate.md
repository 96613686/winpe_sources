# __imp_load_SafeArrayCreate

- ea: `0x180001b59`
- end: `0x180001b65`
- name: `__imp_load_SafeArrayCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019f0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180001b59`

## pseudocode

```c
__int64 load_SafeArrayCreate()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001b59  lea     rax, __imp_SafeArrayCreate
0x180001b60  jmp     __tailMerge_oleaut32_dll
```
