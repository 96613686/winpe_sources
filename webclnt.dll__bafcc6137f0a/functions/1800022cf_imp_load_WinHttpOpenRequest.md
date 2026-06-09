# __imp_load_WinHttpOpenRequest

- ea: `0x1800022cf`
- end: `0x1800022db`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c86`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x1800022cf`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800022cf  lea     rax, __imp_WinHttpOpenRequest
0x1800022d6  jmp     __tailMerge_winhttp_dll
```
