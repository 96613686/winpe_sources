# __scrt_is_ucrt_dll_in_use

- ea: `0x180003158`
- end: `0x180003164`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002aac`
- `0x180002aec`
- `0x180002b84`
- `0x180002bd4`
- `0x180002c68`
- `0x180002d9c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003158  xor     eax, eax
0x18000315a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003160  setnz   al
0x180003163  retn
```
