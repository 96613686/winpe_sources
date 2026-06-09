# __scrt_is_ucrt_dll_in_use

- ea: `0x180002de8`
- end: `0x180002df4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002534`
- `0x180002574`
- `0x18000260c`
- `0x18000265c`
- `0x1800026f0`
- `0x180002824`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002de8  xor     eax, eax
0x180002dea  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002df0  setnz   al
0x180002df3  retn
```
