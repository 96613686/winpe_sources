# _GetImageBase

- ea: `0x180011868`
- end: `0x18001187a`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180012350`
- `0x180012548`
- `0x1800128d4`
- `0x1800129b8`
- `0x180012a9c`
- `0x1800134dc`
- `0x180013744`
- `0x180013a50`
- `0x180013b78`
- `0x180013cc0`
- `0x180014ae0`
- `0x180014c70`
- `0x18001502c`
- `0x18001511c`

## callees

- `0x180011f98`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x180011868  sub     rsp, 28h
0x18001186c  call    __vcrt_getptd
0x180011871  mov     rax, [rax+60h]
0x180011875  add     rsp, 28h
0x180011879  retn
```
