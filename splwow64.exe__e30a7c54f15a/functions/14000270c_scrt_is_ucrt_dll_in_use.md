# __scrt_is_ucrt_dll_in_use

- ea: `0x14000270c`
- end: `0x140002718`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001f04`
- `0x140001f84`
- `0x1400020b8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14000270c  xor     eax, eax
0x14000270e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002714  setnz   al
0x140002717  retn
```
