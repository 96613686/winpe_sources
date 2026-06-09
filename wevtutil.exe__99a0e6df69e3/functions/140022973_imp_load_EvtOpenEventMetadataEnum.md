# __imp_load_EvtOpenEventMetadataEnum

- ea: `0x140022973`
- end: `0x14002297f`
- name: `__imp_load_EvtOpenEventMetadataEnum`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenEventMetadataEnum` at `0x140022973`

## pseudocode

```c
__int64 load_EvtOpenEventMetadataEnum()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x140022973  lea     rax, __imp_EvtOpenEventMetadataEnum
0x14002297a  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
