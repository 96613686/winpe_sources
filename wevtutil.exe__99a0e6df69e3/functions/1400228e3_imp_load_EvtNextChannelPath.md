# __imp_load_EvtNextChannelPath

- ea: `0x1400228e3`
- end: `0x1400228ef`
- name: `__imp_load_EvtNextChannelPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextChannelPath` at `0x1400228e3`

## pseudocode

```c
__int64 load_EvtNextChannelPath()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x1400228e3  lea     rax, __imp_EvtNextChannelPath
0x1400228ea  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
