# __scrt_is_ucrt_dll_in_use

- ea: `0x18001094c`
- end: `0x180010958`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000fd04`
- `0x18000fd44`
- `0x18000fde8`
- `0x18000fe50`
- `0x18000fee4`
- `0x180010018`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18001094c  xor     eax, eax
0x18001094e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180010954  setnz   al
0x180010957  retn
```
