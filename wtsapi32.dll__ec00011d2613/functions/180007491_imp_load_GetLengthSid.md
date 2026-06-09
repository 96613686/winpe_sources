# __imp_load_GetLengthSid

- ea: `0x180007491`
- end: `0x18000749d`
- name: `__imp_load_GetLengthSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007375`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007491`

## pseudocode

```c
__int64 load_GetLengthSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180007491  lea     rax, __imp_GetLengthSid
0x180007498  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
