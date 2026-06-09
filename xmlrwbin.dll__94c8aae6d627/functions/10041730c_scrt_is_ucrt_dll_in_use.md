# __scrt_is_ucrt_dll_in_use

- ea: `0x10041730c`
- end: `0x100417318`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x100416d24`
- `0x100416d64`
- `0x100416e08`
- `0x100416e70`
- `0x100416f14`
- `0x100417048`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x10041730c  xor     eax, eax
0x10041730e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x100417314  setnz   al
0x100417317  retn
```
