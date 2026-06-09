# __scrt_is_ucrt_dll_in_use

- ea: `0x180005b20`
- end: `0x180005b2c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000524c`
- `0x18000528c`
- `0x180005324`
- `0x180005374`
- `0x180005408`
- `0x18000553c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005b20  xor     eax, eax
0x180005b22  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005b28  setnz   al
0x180005b2b  retn
```
