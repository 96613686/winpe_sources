# __imp_load_GetBasicProfileFolderPath

- ea: `0x18000f56d`
- end: `0x18000f579`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f4a6`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000f56d`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000f56d  lea     rax, __imp_GetBasicProfileFolderPath
0x18000f574  jmp     __tailMerge_profapi_dll
```
