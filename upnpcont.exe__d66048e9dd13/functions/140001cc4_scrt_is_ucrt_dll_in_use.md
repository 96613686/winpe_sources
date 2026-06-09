# __scrt_is_ucrt_dll_in_use

- ea: `0x140001cc4`
- end: `0x140001cd0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400014e0`
- `0x140001560`
- `0x140001694`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001cc4  xor     eax, eax
0x140001cc6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001ccc  setnz   al
0x140001ccf  retn
```
