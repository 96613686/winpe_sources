# __imp_load_GetThreadDesktop

- ea: `0x180001f59`
- end: `0x180001f65`
- name: `__imp_load_GetThreadDesktop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!GetThreadDesktop` at `0x180001f59`

## pseudocode

```c
__int64 load_GetThreadDesktop()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180001f59  lea     rax, __imp_GetThreadDesktop
0x180001f60  jmp     __tailMerge_user32_dll
```
