# __imp_load_PathCleanupSpec

- ea: `0x14002e92e`
- end: `0x14002e93a`
- name: `__imp_load_PathCleanupSpec`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14002e8af`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x14002e92e`

## pseudocode

```c
__int64 load_PathCleanupSpec()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x14002e92e  lea     rax, __imp_PathCleanupSpec
0x14002e935  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
