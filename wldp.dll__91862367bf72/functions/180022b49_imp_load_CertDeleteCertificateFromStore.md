# __imp_load_CertDeleteCertificateFromStore

- ea: `0x180022b49`
- end: `0x180022b55`
- name: `__imp_load_CertDeleteCertificateFromStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022aca`

## import_xrefs

- `CRYPT32!CertDeleteCertificateFromStore` at `0x180022b49`

## pseudocode

```c
__int64 load_CertDeleteCertificateFromStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180022b49  lea     rax, __imp_CertDeleteCertificateFromStore
0x180022b50  jmp     __tailMerge_crypt32_dll
```
