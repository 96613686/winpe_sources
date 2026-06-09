# __scrt_is_ucrt_dll_in_use

- ea: `0x180002a8c`
- end: `0x180002a98`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002254`
- `0x180002294`
- `0x18000232c`
- `0x18000237c`
- `0x180002410`
- `0x180002544`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002a8c  xor     eax, eax
0x180002a8e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002a94  setnz   al
0x180002a97  retn
```
