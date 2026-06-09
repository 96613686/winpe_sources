# __imp_load_BCryptCreateHash

- ea: `0x18000221e`
- end: `0x18000222a`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800020eb`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000221e`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18000221e  lea     rax, __imp_BCryptCreateHash
0x180002225  jmp     __tailMerge_bcrypt_dll
```
