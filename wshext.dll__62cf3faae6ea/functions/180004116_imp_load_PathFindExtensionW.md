# __imp_load_PathFindExtensionW

- ea: `0x180004116`
- end: `0x180004122`
- name: `__imp_load_PathFindExtensionW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000403d`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180004116`

## pseudocode

```c
__int64 load_PathFindExtensionW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x180004116  lea     rax, __imp_PathFindExtensionW
0x18000411d  jmp     __tailMerge_shlwapi_dll
```
