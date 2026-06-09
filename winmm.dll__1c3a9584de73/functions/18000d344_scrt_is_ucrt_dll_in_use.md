# __scrt_is_ucrt_dll_in_use

- ea: `0x18000d344`
- end: `0x18000d350`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000caa0`
- `0x18000cae0`
- `0x18000cb78`
- `0x18000cbc8`
- `0x18000cc5c`
- `0x18000cd90`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000d344  xor     eax, eax
0x18000d346  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000d34c  setnz   al
0x18000d34f  retn
```
