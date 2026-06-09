# __uncaught_exception(void)

- ea: `0x180003488`
- end: `0x180003494`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `_BOOL8(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002904`
- `0x180002944`
- `0x1800029dc`
- `0x180002a2c`
- `0x180002ac0`
- `0x180002bf4`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_1800263E0 != 0;
}

```

## disassembly

```asm
0x180003488  xor     eax, eax
0x18000348a  cmp     cs:dword_1800263E0, eax
0x180003490  setnz   al
0x180003493  retn
```
