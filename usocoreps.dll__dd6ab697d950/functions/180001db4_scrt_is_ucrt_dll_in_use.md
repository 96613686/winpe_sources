# __scrt_is_ucrt_dll_in_use

- ea: `0x180001db4`
- end: `0x180001dc0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001560`
- `0x1800015a0`
- `0x180001638`
- `0x180001688`
- `0x18000171c`
- `0x180001850`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001db4  xor     eax, eax
0x180001db6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001dbc  setnz   al
0x180001dbf  retn
```
