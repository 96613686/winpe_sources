# __imp_load_EvtUpdateBookmark

- ea: `0x140022a7c`
- end: `0x140022a88`
- name: `__imp_load_EvtUpdateBookmark`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140022840`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtUpdateBookmark` at `0x140022a7c`

## pseudocode

```c
__int64 load_EvtUpdateBookmark()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll();
}

```

## disassembly

```asm
0x140022a7c  lea     rax, __imp_EvtUpdateBookmark
0x140022a83  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_3_dll
```
