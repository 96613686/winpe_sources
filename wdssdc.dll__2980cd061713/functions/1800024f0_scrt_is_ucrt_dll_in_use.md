# __scrt_is_ucrt_dll_in_use

- ea: `0x1800024f0`
- end: `0x1800024fc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001958`
- `0x180001998`
- `0x180001a3c`
- `0x180001aa4`
- `0x180001b38`
- `0x180001c6c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800024f0  xor     eax, eax
0x1800024f2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800024f8  setnz   al
0x1800024fb  retn
```
