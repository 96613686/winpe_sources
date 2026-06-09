# __imp_load_PathIsDirectoryW

- ea: `0x180002b0e`
- end: `0x180002b1a`
- name: `__imp_load_PathIsDirectoryW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002a8f`

## import_xrefs

- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180002b0e`

## pseudocode

```c
__int64 load_PathIsDirectoryW()
{
  return _tailMerge_api_ms_win_shlwapi_ie_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002b0e  lea     rax, __imp_PathIsDirectoryW
0x180002b15  jmp     __tailMerge_api_ms_win_shlwapi_ie_l1_1_0_dll
```
