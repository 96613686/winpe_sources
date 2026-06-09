# __imp_load_PathQuoteSpacesA

- ea: `0x1800040bc`
- end: `0x1800040c8`
- name: `__imp_load_PathQuoteSpacesA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000403d`

## import_xrefs

- `SHLWAPI!PathQuoteSpacesA` at `0x1800040bc`

## pseudocode

```c
__int64 load_PathQuoteSpacesA()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x1800040bc  lea     rax, __imp_PathQuoteSpacesA
0x1800040c3  jmp     __tailMerge_shlwapi_dll
```
