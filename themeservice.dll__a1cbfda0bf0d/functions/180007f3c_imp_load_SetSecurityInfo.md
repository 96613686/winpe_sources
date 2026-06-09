# __imp_load_SetSecurityInfo

- ea: `0x180007f3c`
- end: `0x180007f48`
- name: `__imp_load_SetSecurityInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007eab`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180007f3c`

## pseudocode

```c
__int64 load_SetSecurityInfo()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x180007f3c  lea     rax, __imp_SetSecurityInfo
0x180007f43  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
