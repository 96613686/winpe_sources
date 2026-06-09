# __imp_load_CertOpenStore

- ea: `0x18001ef60`
- end: `0x18001ef6c`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001ee87`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18001ef60`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x18001ef60  lea     rax, __imp_CertOpenStore
0x18001ef67  jmp     __tailMerge_crypt32_dll
```
