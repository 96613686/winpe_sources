# __imp_load_CertOpenStore

- ea: `0x180020710`
- end: `0x18002071c`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020637`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180020710`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180020710  lea     rax, __imp_CertOpenStore
0x180020717  jmp     __tailMerge_crypt32_dll
```
