# __imp_load_WinHttpOpenRequest

- ea: `0x180001663`
- end: `0x18000166f`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000159c`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x180001663`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001663  lea     rax, __imp_WinHttpOpenRequest
0x18000166a  jmp     __tailMerge_winhttp_dll
```
