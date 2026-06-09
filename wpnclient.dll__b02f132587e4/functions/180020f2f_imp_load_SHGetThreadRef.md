# __imp_load_SHGetThreadRef

- ea: `0x180020f2f`
- end: `0x180020f3b`
- name: `__imp_load_SHGetThreadRef`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020eb0`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x180020f2f`

## pseudocode

```c
__int64 load_SHGetThreadRef()
{
  return _tailMerge_api_ms_win_shcore_thread_l1_1_0_dll();
}

```

## disassembly

```asm
0x180020f2f  lea     rax, __imp_SHGetThreadRef
0x180020f36  jmp     __tailMerge_api_ms_win_shcore_thread_l1_1_0_dll
```
