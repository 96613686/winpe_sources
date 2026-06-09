# __imp_load_NCryptOpenStorageProvider

- ea: `0x1800021c6`
- end: `0x1800021d2`
- name: `__imp_load_NCryptOpenStorageProvider`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002147`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800021c6`

## pseudocode

```c
__int64 load_NCryptOpenStorageProvider()
{
  return _tailMerge_ncrypt_dll();
}

```

## disassembly

```asm
0x1800021c6  lea     rax, __imp_NCryptOpenStorageProvider
0x1800021cd  jmp     __tailMerge_ncrypt_dll
```
