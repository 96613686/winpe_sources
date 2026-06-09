# __scrt_is_ucrt_dll_in_use

- ea: `0x1800028c0`
- end: `0x1800028cc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001fb4`
- `0x180001ff4`
- `0x18000208c`
- `0x1800020dc`
- `0x180002170`
- `0x1800022a4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800028c0  xor     eax, eax
0x1800028c2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800028c8  setnz   al
0x1800028cb  retn
```
