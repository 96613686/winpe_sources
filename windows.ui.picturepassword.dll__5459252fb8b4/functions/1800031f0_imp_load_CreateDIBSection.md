# __imp_load_CreateDIBSection

- ea: `0x1800031f0`
- end: `0x1800031fc`
- name: `__imp_load_CreateDIBSection`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003171`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1800031f0`

## pseudocode

```c
__int64 load_CreateDIBSection()
{
  return _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800031f0  lea     rax, __imp_CreateDIBSection
0x1800031f7  jmp     __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll
```
