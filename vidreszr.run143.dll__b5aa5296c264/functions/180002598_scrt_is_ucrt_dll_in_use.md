# __scrt_is_ucrt_dll_in_use

- ea: `0x180002598`
- end: `0x1800025a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001eec`
- `0x180001f2c`
- `0x180001fc4`
- `0x180002014`
- `0x1800020a8`
- `0x1800021dc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002598  xor     eax, eax
0x18000259a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800025a0  setnz   al
0x1800025a3  retn
```
