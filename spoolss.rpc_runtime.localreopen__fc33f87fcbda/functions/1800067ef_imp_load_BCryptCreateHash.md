# __imp_load_BCryptCreateHash

- ea: `0x1800067ef`
- end: `0x1800067fb`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006704`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800067ef`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800067ef  lea     rax, __imp_BCryptCreateHash
0x1800067f6  jmp     __tailMerge_bcrypt_dll
```
