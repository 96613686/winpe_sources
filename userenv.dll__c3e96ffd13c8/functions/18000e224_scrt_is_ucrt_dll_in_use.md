# __scrt_is_ucrt_dll_in_use

- ea: `0x18000e224`
- end: `0x18000e230`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000da0c`
- `0x18000da4c`
- `0x18000dae4`
- `0x18000db34`
- `0x18000dbc8`
- `0x18000dcfc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000e224  xor     eax, eax
0x18000e226  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000e22c  setnz   al
0x18000e22f  retn
```
