# __scrt_is_ucrt_dll_in_use

- ea: `0x180001da4`
- end: `0x180001db0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000156c`
- `0x1800015ac`
- `0x180001644`
- `0x180001694`
- `0x180001728`
- `0x18000185c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001da4  xor     eax, eax
0x180001da6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001dac  setnz   al
0x180001daf  retn
```
