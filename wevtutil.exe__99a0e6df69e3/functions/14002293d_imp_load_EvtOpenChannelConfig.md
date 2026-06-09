# __imp_load_EvtOpenChannelConfig

- ea: `0x14002293d`
- end: `0x140022949`
- name: `__imp_load_EvtOpenChannelConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x14002272a`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x14002293d`

## pseudocode

```c
__int64 load_EvtOpenChannelConfig()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll();
}

```

## disassembly

```asm
0x14002293d  lea     rax, __imp_EvtOpenChannelConfig
0x140022944  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll
```
