# sub_E51AFE

- ea: `0xe51afe`
- end: `0xe51b03`
- name: `sub_E51AFE`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_BYTE *__fastcall sub_E51AFE(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  _BYTE *result; // rax

  *result = (_BYTE)result;
  return result;
}

```

## disassembly

```asm
0xe51afe  mov     [rax], al
0xe51b00  retn    20h ; ' '
```
