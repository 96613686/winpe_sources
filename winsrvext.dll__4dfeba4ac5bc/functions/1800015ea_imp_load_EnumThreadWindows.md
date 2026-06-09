# __imp_load_EnumThreadWindows

- ea: `0x1800015ea`
- end: `0x1800015f6`
- name: `__imp_load_EnumThreadWindows`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!EnumThreadWindows` at `0x1800015ea`

## pseudocode

```c
__int64 load_EnumThreadWindows()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x1800015ea  lea     rax, __imp_EnumThreadWindows
0x1800015f1  jmp     __tailMerge_user32_dll
```
