# __scrt_is_ucrt_dll_in_use

- ea: `0x180002928`
- end: `0x180002934`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001de4`
- `0x180001e24`
- `0x180001ebc`
- `0x180001f0c`
- `0x180001fa0`
- `0x1800020d4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002928  xor     eax, eax
0x18000292a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002930  setnz   al
0x180002933  retn
```
