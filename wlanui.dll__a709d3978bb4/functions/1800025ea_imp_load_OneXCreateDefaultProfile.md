# __imp_load_OneXCreateDefaultProfile

- ea: `0x1800025ea`
- end: `0x1800025f6`
- name: `__imp_load_OneXCreateDefaultProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002559`

## import_xrefs

- `OneX!OneXCreateDefaultProfile` at `0x1800025ea`

## pseudocode

```c
__int64 load_OneXCreateDefaultProfile()
{
  return _tailMerge_onex_dll();
}

```

## disassembly

```asm
0x1800025ea  lea     rax, __imp_OneXCreateDefaultProfile
0x1800025f1  jmp     __tailMerge_onex_dll
```
