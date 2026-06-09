# __scrt_is_ucrt_dll_in_use

- ea: `0x180002d30`
- end: `0x180002d3c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800025b8`
- `0x1800025f8`
- `0x180002690`
- `0x1800026e0`
- `0x180002774`
- `0x1800028a8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002d30  xor     eax, eax
0x180002d32  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002d38  setnz   al
0x180002d3b  retn
```
