# __imp_load_GetPersistentRegPath

- ea: `0x180009706`
- end: `0x180009712`
- name: `__imp_load_GetPersistentRegPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000962d`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x180009706`

## pseudocode

```c
__int64 load_GetPersistentRegPath()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180009706  lea     rax, __imp_GetPersistentRegPath
0x18000970d  jmp     __tailMerge_mobilenetworking_dll
```
