# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c54`
- end: `0x180001c60`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015a8`
- `0x1800015e8`
- `0x180001680`
- `0x1800016d0`
- `0x180001764`
- `0x180001898`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c54  xor     eax, eax
0x180001c56  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c5c  setnz   al
0x180001c5f  retn
```
