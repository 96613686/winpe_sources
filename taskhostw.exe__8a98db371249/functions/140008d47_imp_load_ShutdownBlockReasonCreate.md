# __imp_load_ShutdownBlockReasonCreate

- ea: `0x140008d47`
- end: `0x140008d53`
- name: `__imp_load_ShutdownBlockReasonCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140008cc8`

## import_xrefs

- `ext-ms-win-ntuser-misc-l1-1-0!ShutdownBlockReasonCreate` at `0x140008d47`

## pseudocode

```c
__int64 load_ShutdownBlockReasonCreate()
{
  return _tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x140008d47  lea     rax, __imp_ShutdownBlockReasonCreate
0x140008d4e  jmp     __tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll
```
