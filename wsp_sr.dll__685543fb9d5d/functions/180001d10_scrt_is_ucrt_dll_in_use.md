# __scrt_is_ucrt_dll_in_use

- ea: `0x180001d10`
- end: `0x180001d1c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001628`
- `0x180001668`
- `0x180001700`
- `0x180001750`
- `0x1800017e4`
- `0x180001918`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001d10  xor     eax, eax
0x180001d12  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001d18  setnz   al
0x180001d1b  retn
```
