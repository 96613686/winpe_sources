# __imp_load_BCryptCreateHash

- ea: `0x18001f480`
- end: `0x18001f48c`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f35f`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001f480`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18001f480  lea     rax, __imp_BCryptCreateHash
0x18001f487  jmp     __tailMerge_bcrypt_dll
```
