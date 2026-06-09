# __imp_load_NCryptOpenKey

- ea: `0x1800021d8`
- end: `0x1800021e4`
- name: `__imp_load_NCryptOpenKey`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002147`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800021d8`

## pseudocode

```c
__int64 load_NCryptOpenKey()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x1800021d8  lea     rax, __imp_NCryptOpenKey
0x1800021df  jmp     __tailMerge_ncrypt_dll
```
