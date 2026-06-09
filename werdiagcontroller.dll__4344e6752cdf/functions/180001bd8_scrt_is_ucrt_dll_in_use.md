# __scrt_is_ucrt_dll_in_use

- ea: `0x180001bd8`
- end: `0x180001be4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000152c`
- `0x18000156c`
- `0x180001604`
- `0x180001654`
- `0x1800016e8`
- `0x18000181c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001bd8  xor     eax, eax
0x180001bda  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001be0  setnz   al
0x180001be3  retn
```
