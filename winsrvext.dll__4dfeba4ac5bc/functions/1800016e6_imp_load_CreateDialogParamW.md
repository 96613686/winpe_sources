# __imp_load_CreateDialogParamW

- ea: `0x1800016e6`
- end: `0x1800016f2`
- name: `__imp_load_CreateDialogParamW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!CreateDialogParamW` at `0x1800016e6`

## pseudocode

```c
__int64 load_CreateDialogParamW()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x1800016e6  lea     rax, __imp_CreateDialogParamW
0x1800016ed  jmp     __tailMerge_user32_dll
```
