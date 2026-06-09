# __imp_load_CryptSIPRemoveProvider

- ea: `0x180004279`
- end: `0x180004285`
- name: `__imp_load_CryptSIPRemoveProvider`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004134`

## import_xrefs

- `CRYPT32!CryptSIPRemoveProvider` at `0x180004279`

## pseudocode

```c
__int64 load_CryptSIPRemoveProvider()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180004279  lea     rax, __imp_CryptSIPRemoveProvider
0x180004280  jmp     __tailMerge_crypt32_dll
```
