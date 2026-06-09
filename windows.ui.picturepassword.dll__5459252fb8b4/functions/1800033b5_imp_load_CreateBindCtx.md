# __imp_load_CreateBindCtx

- ea: `0x1800033b5`
- end: `0x1800033c1`
- name: `__imp_load_CreateBindCtx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003336`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800033b5`

## pseudocode

```c
__int64 load_CreateBindCtx()
{
  return _tailMerge_ext_ms_win_ole32_bindctx_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800033b5  lea     rax, __imp_CreateBindCtx
0x1800033bc  jmp     __tailMerge_ext_ms_win_ole32_bindctx_l1_1_0_dll
```
