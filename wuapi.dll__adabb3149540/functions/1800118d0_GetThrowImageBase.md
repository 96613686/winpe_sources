# _GetThrowImageBase

- ea: `0x1800118d0`
- end: `0x1800118e2`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800123a0`
- `0x180012598`
- `0x180012794`
- `0x18001285c`
- `0x180012aec`
- `0x180012fec`
- `0x180013aa0`
- `0x180013bc8`
- `0x180013d10`
- `0x180013f44`
- `0x18001507c`

## callees

- `0x180011fe8`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x1800118d0  sub     rsp, 28h
0x1800118d4  call    __vcrt_getptd
0x1800118d9  mov     rax, [rax+68h]
0x1800118dd  add     rsp, 28h
0x1800118e1  retn
```
