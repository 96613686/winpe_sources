# __imp_load_CoCreateGuid

- ea: `0x18000246d`
- end: `0x180002479`
- name: `__imp_load_CoCreateGuid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002328`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000246d`

## pseudocode

```c
__int64 load_CoCreateGuid()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000246d  lea     rax, __imp_CoCreateGuid
0x180002474  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
