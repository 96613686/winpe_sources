# __scrt_is_ucrt_dll_in_use

- ea: `0x18000935c`
- end: `0x180009368`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008b10`
- `0x180008b50`
- `0x180008be8`
- `0x180008c38`
- `0x180008ccc`
- `0x180008e00`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000935c  xor     eax, eax
0x18000935e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180009364  setnz   al
0x180009367  retn
```
