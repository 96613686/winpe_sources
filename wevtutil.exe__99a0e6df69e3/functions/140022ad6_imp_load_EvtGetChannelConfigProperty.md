# __imp_load_EvtGetChannelConfigProperty

- ea: `0x140022ad6`
- end: `0x140022ae2`
- name: `__imp_load_EvtGetChannelConfigProperty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x14002272a`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x140022ad6`

## pseudocode

```c
__int64 load_EvtGetChannelConfigProperty()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll();
}

```

## disassembly

```asm
0x140022ad6  lea     rax, __imp_EvtGetChannelConfigProperty
0x140022add  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll
```
