# __scrt_is_ucrt_dll_in_use

- ea: `0x180005f10`
- end: `0x180005f1c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005888`
- `0x1800058c8`
- `0x180005960`
- `0x1800059b0`
- `0x180005a44`
- `0x180005b78`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005f10  xor     eax, eax
0x180005f12  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005f18  setnz   al
0x180005f1b  retn
```
