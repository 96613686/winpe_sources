# __scrt_is_ucrt_dll_in_use

- ea: `0x180002068`
- end: `0x180002074`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800017cc`
- `0x18000180c`
- `0x1800018a4`
- `0x1800018f4`
- `0x180001988`
- `0x180001abc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002068  xor     eax, eax
0x18000206a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002070  setnz   al
0x180002073  retn
```
