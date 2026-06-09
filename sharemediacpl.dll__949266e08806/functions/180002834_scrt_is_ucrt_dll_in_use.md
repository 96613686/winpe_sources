# __scrt_is_ucrt_dll_in_use

- ea: `0x180002834`
- end: `0x180002840`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001db0`
- `0x180001df0`
- `0x180001e88`
- `0x180001ed8`
- `0x180001f6c`
- `0x1800020a0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002834  xor     eax, eax
0x180002836  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000283c  setnz   al
0x18000283f  retn
```
