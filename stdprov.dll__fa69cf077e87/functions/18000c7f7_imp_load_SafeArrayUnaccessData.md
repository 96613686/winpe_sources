# __imp_load_SafeArrayUnaccessData

- ea: `0x18000c7f7`
- end: `0x18000c803`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c530`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000c7f7`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000c7f7  lea     rax, __imp_SafeArrayUnaccessData
0x18000c7fe  jmp     __tailMerge_oleaut32_dll
```
