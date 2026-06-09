# __scrt_is_ucrt_dll_in_use

- ea: `0x140002e24`
- end: `0x140002e30`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002628`
- `0x1400026a8`
- `0x1400027dc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002e24  xor     eax, eax
0x140002e26  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002e2c  setnz   al
0x140002e2f  retn
```
