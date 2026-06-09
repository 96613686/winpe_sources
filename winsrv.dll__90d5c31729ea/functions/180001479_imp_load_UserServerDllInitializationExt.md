# __imp_load_UserServerDllInitializationExt

- ea: `0x180001479`
- end: `0x180001485`
- name: `__imp_load_UserServerDllInitializationExt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800013fa`

## import_xrefs

- `ext-ms-win-core-winsrv-l1-1-0!UserServerDllInitializationExt` at `0x180001479`

## pseudocode

```c
__int64 load_UserServerDllInitializationExt()
{
  return _tailMerge_ext_ms_win_core_winsrv_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001479  lea     rax, __imp_UserServerDllInitializationExt
0x180001480  jmp     __tailMerge_ext_ms_win_core_winsrv_l1_1_0_dll
```
