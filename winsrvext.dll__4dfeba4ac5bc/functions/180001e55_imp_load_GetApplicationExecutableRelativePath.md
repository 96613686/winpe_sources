# __imp_load_GetApplicationExecutableRelativePath

- ea: `0x180001e55`
- end: `0x180001e61`
- name: `__imp_load_GetApplicationExecutableRelativePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001dd6`

## import_xrefs

- `ext-ms-win-desktopappx-l1-1-3!GetApplicationExecutableRelativePath` at `0x180001e55`

## pseudocode

```c
__int64 load_GetApplicationExecutableRelativePath()
{
  return _tailMerge_ext_ms_win_desktopappx_l1_1_3_dll();
}

```

## disassembly

```asm
0x180001e55  lea     rax, __imp_GetApplicationExecutableRelativePath
0x180001e5c  jmp     __tailMerge_ext_ms_win_desktopappx_l1_1_3_dll
```
