# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e1c`
- end: `0x180001e28`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000171c`
- `0x18000175c`
- `0x1800017f4`
- `0x180001844`
- `0x1800018d8`
- `0x180001a0c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e1c  xor     eax, eax
0x180001e1e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e24  setnz   al
0x180001e27  retn
```
