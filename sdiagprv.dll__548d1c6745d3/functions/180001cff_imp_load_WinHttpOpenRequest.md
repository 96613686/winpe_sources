# __imp_load_WinHttpOpenRequest

- ea: `0x180001cff`
- end: `0x180001d0b`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c02`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x180001cff`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001cff  lea     rax, __imp_WinHttpOpenRequest
0x180001d06  jmp     __tailMerge_winhttp_dll
```
