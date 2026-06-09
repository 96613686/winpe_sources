# __scrt_is_ucrt_dll_in_use

- ea: `0x180037010`
- end: `0x18003701c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180036488`
- `0x1800364c8`
- `0x180036560`
- `0x1800365b0`
- `0x180036644`
- `0x180036778`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180037010  xor     eax, eax
0x180037012  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180037018  setnz   al
0x18003701b  retn
```
