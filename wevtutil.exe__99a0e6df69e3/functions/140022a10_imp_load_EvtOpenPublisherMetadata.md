# __imp_load_EvtOpenPublisherMetadata

- ea: `0x140022a10`
- end: `0x140022a1c`
- name: `__imp_load_EvtOpenPublisherMetadata`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022991`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x140022a10`

## pseudocode

```c
__int64 load_EvtOpenPublisherMetadata()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll();
}

```

## disassembly

```asm
0x140022a10  lea     rax, __imp_EvtOpenPublisherMetadata
0x140022a17  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_2_dll
```
