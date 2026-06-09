# __imp_load_BCryptCreateHash

- ea: `0x18002117f`
- end: `0x18002118b`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020d12`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002117f`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18002117f  lea     rax, __imp_BCryptCreateHash
0x180021186  jmp     __tailMerge_bcrypt_dll
```
