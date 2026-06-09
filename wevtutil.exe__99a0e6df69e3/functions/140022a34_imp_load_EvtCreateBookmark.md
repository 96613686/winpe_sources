# __imp_load_EvtCreateBookmark

- ea: `0x140022a34`
- end: `0x140022a40`
- name: `__imp_load_EvtCreateBookmark`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtCreateBookmark` at `0x140022a34`

## pseudocode

```c
__int64 load_EvtCreateBookmark()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x140022a34  lea     rax, __imp_EvtCreateBookmark
0x140022a3b  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
