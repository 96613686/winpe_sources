# __scrt_is_ucrt_dll_in_use

- ea: `0x14001b48c`
- end: `0x14001b498`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14001aa84`
- `0x14001ab04`
- `0x14001ac38`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14001b48c  xor     eax, eax
0x14001b48e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14001b494  setnz   al
0x14001b497  retn
```
