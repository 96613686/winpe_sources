# __scrt_is_ucrt_dll_in_use

- ea: `0x1800108fc`
- end: `0x180010908`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000fcb4`
- `0x18000fcf4`
- `0x18000fd98`
- `0x18000fe00`
- `0x18000fe94`
- `0x18000ffc8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800108fc  xor     eax, eax
0x1800108fe  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180010904  setnz   al
0x180010907  retn
```
