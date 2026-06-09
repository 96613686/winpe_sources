# __imp_load_EvtCreateRenderContext

- ea: `0x140022a58`
- end: `0x140022a64`
- name: `__imp_load_EvtCreateRenderContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14002272a`

## import_xrefs

- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x140022a58`

## pseudocode

```c
__int64 load_EvtCreateRenderContext()
{
  return _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll();
}

```

## disassembly

```asm
0x140022a58  lea     rax, __imp_EvtCreateRenderContext
0x140022a5f  jmp     __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll
```
