# __scrt_is_ucrt_dll_in_use

- ea: `0x1800030e0`
- end: `0x1800030ec`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000284c`
- `0x18000288c`
- `0x180002924`
- `0x180002974`
- `0x180002a08`
- `0x180002b3c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800030e0  xor     eax, eax
0x1800030e2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800030e8  setnz   al
0x1800030eb  retn
```
