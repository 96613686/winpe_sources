# __imp_load_CoInitializeSecurity

- ea: `0x140005ca8`
- end: `0x140005cb4`
- name: `__imp_load_CoInitializeSecurity`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005b44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140005ca8`

## pseudocode

```c
__int64 load_CoInitializeSecurity()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x140005ca8  lea     rax, __imp_CoInitializeSecurity
0x140005caf  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
