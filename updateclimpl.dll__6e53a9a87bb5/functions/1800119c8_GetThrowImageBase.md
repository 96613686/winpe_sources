# _GetThrowImageBase

- ea: `0x1800119c8`
- end: `0x1800119da`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180012260`
- `0x18001245c`
- `0x180012608`
- `0x180012e54`
- `0x180012f7c`
- `0x1800130c4`
- `0x180013dc4`

## callees

- `0x180011f98`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x1800119c8  sub     rsp, 28h
0x1800119cc  call    __vcrt_getptd
0x1800119d1  mov     rax, [rax+68h]
0x1800119d5  add     rsp, 28h
0x1800119d9  retn
```
