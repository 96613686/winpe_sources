# __imp_load_FDICreate

- ea: `0x180036484`
- end: `0x180036490`
- name: `__imp_load_FDICreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800363f3`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x180036484`

## pseudocode

```c
__int64 load_FDICreate()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x180036484  lea     rax, __imp_FDICreate
0x18003648b  jmp     __tailMerge_cabinet_dll
```
