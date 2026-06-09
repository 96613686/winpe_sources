# __imp_load_EvtOpenSession

- ea: `0x140022834`
- end: `0x140022840`
- name: `__imp_load_EvtOpenSession`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400227b5`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-1!EvtOpenSession` at `0x140022834`

## pseudocode

```c
__int64 load_EvtOpenSession()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_1_dll();
}

```

## disassembly

```asm
0x140022834  lea     rax, __imp_EvtOpenSession
0x14002283b  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_1_dll
```
