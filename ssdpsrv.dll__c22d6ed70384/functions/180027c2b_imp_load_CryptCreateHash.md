# __imp_load_CryptCreateHash

- ea: `0x180027c2b`
- end: `0x180027c37`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800278f6`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180027c2b`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x180027c2b  lea     rax, __imp_CryptCreateHash
0x180027c32  jmp     __tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll
```
