# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e78`
- end: `0x180001e84`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015b4`
- `0x1800015f4`
- `0x18000168c`
- `0x1800016dc`
- `0x180001770`
- `0x1800018a4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e78  xor     eax, eax
0x180001e7a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e80  setnz   al
0x180001e83  retn
```
