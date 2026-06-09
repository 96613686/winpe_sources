# _GetImageBase

- ea: `0x1800119b0`
- end: `0x1800119c2`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180012260`
- `0x180012524`
- `0x180012b48`
- `0x180012e54`
- `0x180012f7c`
- `0x180013ab0`
- `0x180013dc4`
- `0x180013eb4`

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
0x1800119b0  sub     rsp, 28h
0x1800119b4  call    __vcrt_getptd
0x1800119b9  mov     rax, [rax+60h]
0x1800119bd  add     rsp, 28h
0x1800119c1  retn
```
