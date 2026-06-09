# __scrt_is_ucrt_dll_in_use

- ea: `0x180004390`
- end: `0x18000439c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003d08`
- `0x180003d48`
- `0x180003de0`
- `0x180003e30`
- `0x180003ec4`
- `0x180003ff8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004390  xor     eax, eax
0x180004392  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004398  setnz   al
0x18000439b  retn
```
