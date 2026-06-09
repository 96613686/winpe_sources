# __imp_load_GetBasicProfileFolderPath

- ea: `0x18000e8bd`
- end: `0x18000e8c9`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000e7f6`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000e8bd`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000e8bd  lea     rax, __imp_GetBasicProfileFolderPath
0x18000e8c4  jmp     __tailMerge_profapi_dll
```
