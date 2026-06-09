# _CGpWmpEncoder::CreateNewFrameInternal_::_1_::catch$1

- ea: `0x18004402a`
- end: `0x18004404f`
- name: `_CGpWmpEncoder::CreateNewFrameInternal_::_1_::catch$1`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::CreateNewFrameInternal_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18004402a  mov     [rsp+arg_8], rdx
0x18004402f  push    rbp
0x180044030  sub     rsp, 30h
0x180044034  mov     rbp, rdx
0x180044037  mov     dword ptr [rbp+70h], 8007000Eh
0x18004403e  mov     rax, 0
0x180044048  add     rsp, 30h
0x18004404c  pop     rbp
0x18004404d  retn
```
