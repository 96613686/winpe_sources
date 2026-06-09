# _CGpWmpEncoder::HrCommitFrame_::_1_::catch$0

- ea: `0x180044067`
- end: `0x18004408c`
- name: `_CGpWmpEncoder::HrCommitFrame_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::HrCommitFrame_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x180044067  mov     [rsp+arg_8], rdx
0x18004406c  push    rbp
0x18004406d  sub     rsp, 30h
0x180044071  mov     rbp, rdx
0x180044074  mov     dword ptr [rbp+40h], 8007000Eh
0x18004407b  mov     rax, 0
0x180044085  add     rsp, 30h
0x180044089  pop     rbp
0x18004408a  retn
```
