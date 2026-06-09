# __scrt_is_ucrt_dll_in_use

- ea: `0x180005b78`
- end: `0x180005b84`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005344`
- `0x180005384`
- `0x18000541c`
- `0x18000546c`
- `0x180005500`
- `0x180005634`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005b78  xor     eax, eax
0x180005b7a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005b80  setnz   al
0x180005b83  retn
```
