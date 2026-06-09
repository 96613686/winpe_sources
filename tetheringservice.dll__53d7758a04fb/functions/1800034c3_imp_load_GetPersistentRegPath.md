# __imp_load_GetPersistentRegPath

- ea: `0x1800034c3`
- end: `0x1800034cf`
- name: `__imp_load_GetPersistentRegPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003420`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x1800034c3`

## pseudocode

```c
__int64 load_GetPersistentRegPath()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800034c3  lea     rax, __imp_GetPersistentRegPath
0x1800034ca  jmp     __tailMerge_mobilenetworking_dll
```
