# __scrt_is_ucrt_dll_in_use

- ea: `0x18000ca78`
- end: `0x18000ca84`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000c378`
- `0x18000c3b8`
- `0x18000c450`
- `0x18000c4a0`
- `0x18000c534`
- `0x18000c668`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000ca78  xor     eax, eax
0x18000ca7a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000ca80  setnz   al
0x18000ca83  retn
```
