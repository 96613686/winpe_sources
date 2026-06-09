# __imp_load_PathCleanupSpec

- ea: `0x14002d75e`
- end: `0x14002d76a`
- name: `__imp_load_PathCleanupSpec`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14002d6df`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x14002d75e`

## pseudocode

```c
__int64 load_PathCleanupSpec()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x14002d75e  lea     rax, __imp_PathCleanupSpec
0x14002d765  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
