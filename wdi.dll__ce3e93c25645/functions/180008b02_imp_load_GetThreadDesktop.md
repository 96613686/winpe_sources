# __imp_load_GetThreadDesktop

- ea: `0x180008b02`
- end: `0x180008b0e`
- name: `__imp_load_GetThreadDesktop`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008a4d`

## import_xrefs

- `USER32!GetThreadDesktop` at `0x180008b02`

## pseudocode

```c
__int64 load_GetThreadDesktop()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180008b02  lea     rax, __imp_GetThreadDesktop
0x180008b09  jmp     __tailMerge_user32_dll
```
