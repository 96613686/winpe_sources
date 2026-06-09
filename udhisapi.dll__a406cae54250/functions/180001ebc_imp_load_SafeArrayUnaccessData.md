# __imp_load_SafeArrayUnaccessData

- ea: `0x180001ebc`
- end: `0x180001ec8`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d46`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180001ebc`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001ebc  lea     rax, __imp_SafeArrayUnaccessData
0x180001ec3  jmp     __tailMerge_oleaut32_dll
```
