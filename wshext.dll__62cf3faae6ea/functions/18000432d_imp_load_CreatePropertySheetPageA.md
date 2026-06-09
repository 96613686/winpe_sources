# __imp_load_CreatePropertySheetPageA

- ea: `0x18000432d`
- end: `0x180004339`
- name: `__imp_load_CreatePropertySheetPageA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003fa0`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageA` at `0x18000432d`

## pseudocode

```c
__int64 load_CreatePropertySheetPageA()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000432d  lea     rax, __imp_CreatePropertySheetPageA
0x180004334  jmp     __tailMerge_comctl32_dll
```
