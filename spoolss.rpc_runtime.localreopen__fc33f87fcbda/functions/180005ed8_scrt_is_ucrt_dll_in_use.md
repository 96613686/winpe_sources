# __scrt_is_ucrt_dll_in_use

- ea: `0x180005ed8`
- end: `0x180005ee4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800056a4`
- `0x1800056e4`
- `0x18000577c`
- `0x1800057cc`
- `0x180005860`
- `0x180005994`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180005ed8  xor     eax, eax
0x180005eda  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005ee0  setnz   al
0x180005ee3  retn
```
