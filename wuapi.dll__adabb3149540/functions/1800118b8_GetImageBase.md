# _GetImageBase

- ea: `0x1800118b8`
- end: `0x1800118ca`
- name: `_GetImageBase`
- size: `18`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1800123a0`
- `0x180012598`
- `0x180012924`
- `0x180012a08`
- `0x180012aec`
- `0x18001352c`
- `0x180013794`
- `0x180013aa0`
- `0x180013bc8`
- `0x180013d10`
- `0x180014b30`
- `0x180014cc0`
- `0x18001507c`
- `0x18001516c`

## callees

- `0x180011fe8`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x1800118b8  sub     rsp, 28h
0x1800118bc  call    __vcrt_getptd
0x1800118c1  mov     rax, [rax+60h]
0x1800118c5  add     rsp, 28h
0x1800118c9  retn
```
