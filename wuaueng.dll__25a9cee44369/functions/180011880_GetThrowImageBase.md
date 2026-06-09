# _GetThrowImageBase

- ea: `0x180011880`
- end: `0x180011892`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180012350`
- `0x180012548`
- `0x180012744`
- `0x18001280c`
- `0x180012a9c`
- `0x180012f9c`
- `0x180013a50`
- `0x180013b78`
- `0x180013cc0`
- `0x180013ef4`
- `0x18001502c`

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
0x180011880  sub     rsp, 28h
0x180011884  call    __vcrt_getptd
0x180011889  mov     rax, [rax+68h]
0x18001188d  add     rsp, 28h
0x180011891  retn
```
