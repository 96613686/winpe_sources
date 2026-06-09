# __imp_load_StringFromCLSID

- ea: `0x180009441`
- end: `0x18000944d`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008bcb`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180009441`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009441  lea     rax, __imp_StringFromCLSID
0x180009448  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
