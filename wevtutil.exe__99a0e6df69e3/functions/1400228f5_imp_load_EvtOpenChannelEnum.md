# __imp_load_EvtOpenChannelEnum

- ea: `0x1400228f5`
- end: `0x140022901`
- name: `__imp_load_EvtOpenChannelEnum`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenChannelEnum` at `0x1400228f5`

## pseudocode

```c
__int64 load_EvtOpenChannelEnum()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x1400228f5  lea     rax, __imp_EvtOpenChannelEnum
0x1400228fc  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
