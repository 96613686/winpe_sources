# _GetThrowImageBase

- ea: `0x180002bd0`
- end: `0x180002be2`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003760`
- `0x180003930`
- `0x180003b00`
- `0x180003bc0`
- `0x180003e48`
- `0x180004304`
- `0x180004d60`
- `0x180004e78`
- `0x180004f94`
- `0x1800051a8`
- `0x1800062a0`

## callees

- `0x1800033d8`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x180002bd0  sub     rsp, 28h
0x180002bd4  call    __vcrt_getptd
0x180002bd9  mov     rax, [rax+68h]
0x180002bdd  add     rsp, 28h
0x180002be1  retn
```
