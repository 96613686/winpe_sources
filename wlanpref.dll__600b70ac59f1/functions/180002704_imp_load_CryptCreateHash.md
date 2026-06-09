# __imp_load_CryptCreateHash

- ea: `0x180002704`
- end: `0x180002710`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000262b`

## import_xrefs

- `CRYPTSP!CryptCreateHash` at `0x180002704`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_cryptsp_dll();
}

```

## disassembly

```asm
0x180002704  lea     rax, __imp_CryptCreateHash
0x18000270b  jmp     __tailMerge_cryptsp_dll
```
