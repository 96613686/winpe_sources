# _GetImageBase

- ea: `0x180002bb8`
- end: `0x180002bca`
- name: `_GetImageBase`
- size: `18`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180003760`
- `0x180003930`
- `0x180003c80`
- `0x180003d64`
- `0x180003e48`
- `0x180004820`
- `0x180004a60`
- `0x180004d60`
- `0x180004e78`
- `0x180004f94`
- `0x180005d50`
- `0x180005ef4`
- `0x1800062a0`
- `0x180006388`

## callees

- `0x1800033d8`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x180002bb8  sub     rsp, 28h
0x180002bbc  call    __vcrt_getptd
0x180002bc1  mov     rax, [rax+60h]
0x180002bc5  add     rsp, 28h
0x180002bc9  retn
```
