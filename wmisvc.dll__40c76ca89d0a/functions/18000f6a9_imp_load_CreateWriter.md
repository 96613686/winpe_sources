# __imp_load_CreateWriter

- ea: `0x18000f6a9`
- end: `0x18000f6b5`
- name: `__imp_load_CreateWriter`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f62a`

## import_xrefs

- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriter` at `0x18000f6a9`

## pseudocode

```c
__int64 load_CreateWriter()
{
  return _tailMerge_ext_ms_win_fs_vssapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f6a9  lea     rax, __imp_CreateWriter
0x18000f6b0  jmp     __tailMerge_ext_ms_win_fs_vssapi_l1_1_0_dll
```
