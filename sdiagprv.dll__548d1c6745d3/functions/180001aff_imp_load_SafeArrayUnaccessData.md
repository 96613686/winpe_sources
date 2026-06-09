# __imp_load_SafeArrayUnaccessData

- ea: `0x180001aff`
- end: `0x180001b0b`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019f0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180001aff`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001aff  lea     rax, __imp_SafeArrayUnaccessData
0x180001b06  jmp     __tailMerge_oleaut32_dll
```
