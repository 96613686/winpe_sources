# __scrt_is_ucrt_dll_in_use

- ea: `0x140001e70`
- end: `0x140001e7c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400015e8`
- `0x140001668`
- `0x14000179c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001e70  xor     eax, eax
0x140001e72  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001e78  setnz   al
0x140001e7b  retn
```
