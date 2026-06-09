# __imp_load_EvtSaveChannelConfig

- ea: `0x140022aa0`
- end: `0x140022aac`
- name: `__imp_load_EvtSaveChannelConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140022991`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x140022aa0`

## pseudocode

```c
__int64 load_EvtSaveChannelConfig()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll();
}

```

## disassembly

```asm
0x140022aa0  lea     rax, __imp_EvtSaveChannelConfig
0x140022aa7  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll
```
