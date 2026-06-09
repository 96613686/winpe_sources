# __imp_load_EvtOpenLog

- ea: `0x14002294f`
- end: `0x14002295b`
- name: `__imp_load_EvtOpenLog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenLog` at `0x14002294f`

## pseudocode

```c
__int64 load_EvtOpenLog()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x14002294f  lea     rax, __imp_EvtOpenLog
0x140022956  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
