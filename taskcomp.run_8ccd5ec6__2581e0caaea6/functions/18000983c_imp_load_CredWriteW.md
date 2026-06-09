# __imp_load_CredWriteW

- ea: `0x18000983c`
- end: `0x180009848`
- name: `__imp_load_CredWriteW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800096f6`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18000983c`

## pseudocode

```c
__int64 load_CredWriteW()
{
  return _tailMerge_api_ms_win_security_credentials_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000983c  lea     rax, __imp_CredWriteW
0x180009843  jmp     __tailMerge_api_ms_win_security_credentials_l1_1_0_dll
```
