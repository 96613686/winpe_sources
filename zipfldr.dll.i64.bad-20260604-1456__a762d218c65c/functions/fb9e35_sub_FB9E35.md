# sub_FB9E35

- ea: `0xfb9e35`
- end: `0xfb9e3b`
- name: `sub_FB9E35`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_FB9E35(
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
  __int64 result; // rax

  *(_BYTE *)(2 * result) = BYTE1(result);
  return result;
}

```

## disassembly

```asm
0xfb9e35  mov     [rax+rax], ah
0xfb9e38  retn    20h ; ' '
```
