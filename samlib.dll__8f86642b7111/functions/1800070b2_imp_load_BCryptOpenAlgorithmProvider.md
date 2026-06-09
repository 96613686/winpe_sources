# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x1800070b2`
- end: `0x1800070be`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006ffd`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800070b2`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800070b2  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x1800070b9  jmp     __tailMerge_bcrypt_dll
```
