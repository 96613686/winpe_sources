# __scrt_is_ucrt_dll_in_use

- ea: `0x180015d20`
- end: `0x180015d2c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180015638`
- `0x180015678`
- `0x180015710`
- `0x180015760`
- `0x1800157f4`
- `0x180015928`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180015d20  xor     eax, eax
0x180015d22  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180015d28  setnz   al
0x180015d2b  retn
```
