# __scrt_is_ucrt_dll_in_use

- ea: `0x18000544c`
- end: `0x180005458`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004dac`
- `0x180004dec`
- `0x180004e84`
- `0x180004ed4`
- `0x180004f68`
- `0x18000509c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000544c  xor     eax, eax
0x18000544e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005454  setnz   al
0x180005457  retn
```
