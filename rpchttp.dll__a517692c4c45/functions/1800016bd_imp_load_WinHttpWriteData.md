# __imp_load_WinHttpWriteData

- ea: `0x1800016bd`
- end: `0x1800016c9`
- name: `__imp_load_WinHttpWriteData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000159c`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800016bd`

## pseudocode

```c
__int64 load_WinHttpWriteData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800016bd  lea     rax, __imp_WinHttpWriteData
0x1800016c4  jmp     __tailMerge_winhttp_dll
```
