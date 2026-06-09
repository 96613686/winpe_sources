# __scrt_is_ucrt_dll_in_use

- ea: `0x1400053cc`
- end: `0x1400053d8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140004bf4`
- `0x140004c74`
- `0x140004da8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400053cc  xor     eax, eax
0x1400053ce  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400053d4  setnz   al
0x1400053d7  retn
```
