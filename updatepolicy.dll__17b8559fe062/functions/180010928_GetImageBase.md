# _GetImageBase

- ea: `0x180010928`
- end: `0x18001093a`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180011410`
- `0x180011608`
- `0x180011994`
- `0x180011a78`
- `0x180011b5c`
- `0x18001259c`
- `0x180012804`
- `0x180012b10`
- `0x180012c38`
- `0x180012d80`
- `0x180013ba0`
- `0x180013d30`
- `0x1800140ec`
- `0x1800141dc`

## callees

- `0x180011058`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x180010928  sub     rsp, 28h
0x18001092c  call    __vcrt_getptd
0x180010931  mov     rax, [rax+60h]
0x180010935  add     rsp, 28h
0x180010939  retn
```
