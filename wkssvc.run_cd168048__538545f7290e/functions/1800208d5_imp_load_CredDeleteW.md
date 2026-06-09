# __imp_load_CredDeleteW

- ea: `0x1800208d5`
- end: `0x1800208e1`
- name: `__imp_load_CredDeleteW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020856`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800208d5`

## pseudocode

```c
__int64 load_CredDeleteW()
{
  return _tailMerge_api_ms_win_security_credentials_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800208d5  lea     rax, __imp_CredDeleteW
0x1800208dc  jmp     __tailMerge_api_ms_win_security_credentials_l1_1_0_dll
```
