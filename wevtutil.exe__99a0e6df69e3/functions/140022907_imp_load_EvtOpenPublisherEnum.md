# __imp_load_EvtOpenPublisherEnum

- ea: `0x140022907`
- end: `0x140022913`
- name: `__imp_load_EvtOpenPublisherEnum`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenPublisherEnum` at `0x140022907`

## pseudocode

```c
__int64 load_EvtOpenPublisherEnum()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x140022907  lea     rax, __imp_EvtOpenPublisherEnum
0x14002290e  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
