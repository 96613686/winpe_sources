# __imp_load_FDICopy

- ea: `0x180036496`
- end: `0x1800364a2`
- name: `__imp_load_FDICopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800363f3`

## import_xrefs

- `Cabinet!__imp_FDICopy` at `0x180036496`

## pseudocode

```c
__int64 load_FDICopy()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x180036496  lea     rax, __imp_FDICopy
0x18003649d  jmp     __tailMerge_cabinet_dll
```
