# __imp_load_CertOpenStore

- ea: `0x18001f31d`
- end: `0x18001f329`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f244`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18001f31d`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x18001f31d  lea     rax, __imp_CertOpenStore
0x18001f324  jmp     __tailMerge_crypt32_dll
```
