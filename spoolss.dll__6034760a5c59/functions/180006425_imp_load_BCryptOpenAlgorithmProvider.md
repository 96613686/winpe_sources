# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x180006425`
- end: `0x180006431`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006394`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180006425`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180006425  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x18000642c  jmp     __tailMerge_bcrypt_dll
```
