# __imp_load_CryptMsgOpenToDecode

- ea: `0x1800236b2`
- end: `0x1800236be`
- name: `__imp_load_CryptMsgOpenToDecode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022aca`

## import_xrefs

- `CRYPT32!CryptMsgOpenToDecode` at `0x1800236b2`

## pseudocode

```c
__int64 load_CryptMsgOpenToDecode()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x1800236b2  lea     rax, __imp_CryptMsgOpenToDecode
0x1800236b9  jmp     __tailMerge_crypt32_dll
```
