# __imp_load_CLSIDFromProgID

- ea: `0x18001b4e6`
- end: `0x18001b4f2`
- name: `__imp_load_CLSIDFromProgID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001b100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18001b4e6`

## pseudocode

```c
__int64 load_CLSIDFromProgID()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001b4e6  lea     rax, __imp_CLSIDFromProgID
0x18001b4ed  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
