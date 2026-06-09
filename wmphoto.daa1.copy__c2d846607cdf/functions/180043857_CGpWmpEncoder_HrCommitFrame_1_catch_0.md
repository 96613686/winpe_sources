# _CGpWmpEncoder::HrCommitFrame_::_1_::catch$0

- ea: `0x180043857`
- end: `0x18004387c`
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
0x180043857  mov     [rsp+arg_8], rdx
0x18004385c  push    rbp
0x18004385d  sub     rsp, 30h
0x180043861  mov     rbp, rdx
0x180043864  mov     dword ptr [rbp+40h], 8007000Eh
0x18004386b  mov     rax, 0
0x180043875  add     rsp, 30h
0x180043879  pop     rbp
0x18004387a  retn
```
