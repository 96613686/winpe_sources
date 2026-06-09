# __imp_load_OpenColorProfileW

- ea: `0x180037395`
- end: `0x1800373a1`
- name: `__imp_load_OpenColorProfileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180037316`

## import_xrefs

- `mscms!OpenColorProfileW` at `0x180037395`

## pseudocode

```c
__int64 load_OpenColorProfileW()
{
  return _tailMerge_mscms_dll();
}

```

## disassembly

```asm
0x180037395  lea     rax, __imp_OpenColorProfileW
0x18003739c  jmp     __tailMerge_mscms_dll
```
