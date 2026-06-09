# __imp_load_BCryptCreateHash

- ea: `0x18001f9cf`
- end: `0x18001f9db`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f562`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001f9cf`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18001f9cf  lea     rax, __imp_BCryptCreateHash
0x18001f9d6  jmp     __tailMerge_bcrypt_dll
```
