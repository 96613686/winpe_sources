# __imp_load_BCryptCreateHash

- ea: `0x18000647f`
- end: `0x18000648b`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006394`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000647f`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18000647f  lea     rax, __imp_BCryptCreateHash
0x180006486  jmp     __tailMerge_bcrypt_dll
```
