# __imp_load_PathFindExtensionA

- ea: `0x180004128`
- end: `0x180004134`
- name: `__imp_load_PathFindExtensionA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000403d`

## import_xrefs

- `SHLWAPI!PathFindExtensionA` at `0x180004128`

## pseudocode

```c
__int64 load_PathFindExtensionA()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x180004128  lea     rax, __imp_PathFindExtensionA
0x18000412f  jmp     __tailMerge_shlwapi_dll
```
