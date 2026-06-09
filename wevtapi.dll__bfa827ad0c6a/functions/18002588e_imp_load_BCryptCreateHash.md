# __imp_load_BCryptCreateHash

- ea: `0x18002588e`
- end: `0x18002589a`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800257c7`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002588e`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18002588e  lea     rax, __imp_BCryptCreateHash
0x180025895  jmp     __tailMerge_bcrypt_dll
```
