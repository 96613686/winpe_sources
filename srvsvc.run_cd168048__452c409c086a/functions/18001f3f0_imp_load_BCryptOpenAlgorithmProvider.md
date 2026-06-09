# __imp_load_BCryptOpenAlgorithmProvider

- ea: `0x18001f3f0`
- end: `0x18001f3fc`
- name: `__imp_load_BCryptOpenAlgorithmProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f35f`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001f3f0`

## pseudocode

```c
__int64 load_BCryptOpenAlgorithmProvider()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18001f3f0  lea     rax, __imp_BCryptOpenAlgorithmProvider
0x18001f3f7  jmp     __tailMerge_bcrypt_dll
```
