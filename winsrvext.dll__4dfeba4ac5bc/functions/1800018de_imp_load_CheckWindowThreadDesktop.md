# __imp_load_CheckWindowThreadDesktop

- ea: `0x1800018de`
- end: `0x1800018ea`
- name: `__imp_load_CheckWindowThreadDesktop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!CheckWindowThreadDesktop` at `0x1800018de`

## pseudocode

```c
__int64 load_CheckWindowThreadDesktop()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x1800018de  lea     rax, __imp_CheckWindowThreadDesktop
0x1800018e5  jmp     __tailMerge_user32_dll
```
