# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180020133`
- end: `0x18002013f`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f562`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180020133`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180020133  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x18002013a  jmp     __tailMerge_bcrypt_dll
```
