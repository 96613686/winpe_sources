# __imp_load_OpenColorProfileW

- ea: `0x180036dc5`
- end: `0x180036dd1`
- name: `__imp_load_OpenColorProfileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180036d46`

## import_xrefs

- `mscms!OpenColorProfileW` at `0x180036dc5`

## pseudocode

```c
__int64 load_OpenColorProfileW()
{
  return _tailMerge_mscms_dll();
}

```

## disassembly

```asm
0x180036dc5  lea     rax, __imp_OpenColorProfileW
0x180036dcc  jmp     __tailMerge_mscms_dll
```
