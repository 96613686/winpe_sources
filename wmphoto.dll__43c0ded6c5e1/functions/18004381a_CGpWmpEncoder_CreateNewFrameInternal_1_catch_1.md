# _CGpWmpEncoder::CreateNewFrameInternal_::_1_::catch$1

- ea: `0x18004381a`
- end: `0x18004383f`
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
0x18004381a  mov     [rsp+arg_8], rdx
0x18004381f  push    rbp
0x180043820  sub     rsp, 30h
0x180043824  mov     rbp, rdx
0x180043827  mov     dword ptr [rbp+70h], 8007000Eh
0x18004382e  mov     rax, 0
0x180043838  add     rsp, 30h
0x18004383c  pop     rbp
0x18004383d  retn
```
