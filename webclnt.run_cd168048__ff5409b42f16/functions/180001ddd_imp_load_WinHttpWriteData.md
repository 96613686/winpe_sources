# __imp_load_WinHttpWriteData

- ea: `0x180001ddd`
- end: `0x180001de9`
- name: `__imp_load_WinHttpWriteData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c86`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x180001ddd`

## pseudocode

```c
__int64 load_WinHttpWriteData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001ddd  lea     rax, __imp_WinHttpWriteData
0x180001de4  jmp     __tailMerge_winhttp_dll
```
