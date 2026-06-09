# __scrt_is_ucrt_dll_in_use

- ea: `0x1800029fc`
- end: `0x180002a08`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000218c`
- `0x1800021cc`
- `0x180002264`
- `0x1800022b4`
- `0x180002348`
- `0x18000247c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800029fc  xor     eax, eax
0x1800029fe  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002a04  setnz   al
0x180002a07  retn
```
