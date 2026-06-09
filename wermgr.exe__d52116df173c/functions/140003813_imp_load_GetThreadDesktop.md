# __imp_load_GetThreadDesktop

- ea: `0x140003813`
- end: `0x14000381f`
- name: `__imp_load_GetThreadDesktop`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003782`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x140003813`

## pseudocode

```c
__int64 load_GetThreadDesktop()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003813  lea     rax, __imp_GetThreadDesktop
0x14000381a  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll
```
