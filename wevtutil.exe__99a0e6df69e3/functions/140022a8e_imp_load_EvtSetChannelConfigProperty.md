# __imp_load_EvtSetChannelConfigProperty

- ea: `0x140022a8e`
- end: `0x140022a9a`
- name: `__imp_load_EvtSetChannelConfigProperty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140022991`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x140022a8e`

## pseudocode

```c
__int64 load_EvtSetChannelConfigProperty()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll();
}

```

## disassembly

```asm
0x140022a8e  lea     rax, __imp_EvtSetChannelConfigProperty
0x140022a95  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll
```
