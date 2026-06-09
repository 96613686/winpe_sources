# __scrt_is_ucrt_dll_in_use

- ea: `0x18000276c`
- end: `0x180002778`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ef8`
- `0x180001f38`
- `0x180001fd0`
- `0x180002020`
- `0x1800020b4`
- `0x1800021e8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000276c  xor     eax, eax
0x18000276e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002774  setnz   al
0x180002777  retn
```
