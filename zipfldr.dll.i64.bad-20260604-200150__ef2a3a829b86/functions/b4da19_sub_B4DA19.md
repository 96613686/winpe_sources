# sub_B4DA19

- ea: `0xb4da19`
- end: `0xb4da1e`
- name: `sub_B4DA19`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_WORD *__fastcall sub_B4DA19(
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
  _WORD *result; // rax

  *result = __ES__;
  return result;
}

```

## disassembly

```asm
0xb4da19  mov     word ptr [rax], es
0xb4da1b  retn    20h ; ' '
```
