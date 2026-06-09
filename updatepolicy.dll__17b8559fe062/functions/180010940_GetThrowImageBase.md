# _GetThrowImageBase

- ea: `0x180010940`
- end: `0x180010952`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180011410`
- `0x180011608`
- `0x180011804`
- `0x1800118cc`
- `0x180011b5c`
- `0x18001205c`
- `0x180012b10`
- `0x180012c38`
- `0x180012d80`
- `0x180012fb4`
- `0x1800140ec`

## callees

- `0x180011058`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x180010940  sub     rsp, 28h
0x180010944  call    __vcrt_getptd
0x180010949  mov     rax, [rax+68h]
0x18001094d  add     rsp, 28h
0x180010951  retn
```
