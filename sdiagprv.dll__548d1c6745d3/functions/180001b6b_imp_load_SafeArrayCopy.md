# __imp_load_SafeArrayCopy

- ea: `0x180001b6b`
- end: `0x180001b77`
- name: `__imp_load_SafeArrayCopy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019f0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x180001b6b`

## pseudocode

```c
__int64 load_SafeArrayCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001b6b  lea     rax, __imp_SafeArrayCopy
0x180001b72  jmp     __tailMerge_oleaut32_dll
```
