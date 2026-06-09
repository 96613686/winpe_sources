# __imp_load_StringFromCLSID

- ea: `0x180009921`
- end: `0x18000992d`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800090ab`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180009921`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009921  lea     rax, __imp_StringFromCLSID
0x180009928  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
