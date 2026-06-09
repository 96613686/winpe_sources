# _CWmpClassFactory::CreateInstance_::_1_::catch$3

- ea: `0x180043f6c`
- end: `0x180043f91`
- name: `_CWmpClassFactory::CreateInstance_::_1_::catch$3`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CWmpClassFactory::CreateInstance_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x180043f6c  mov     [rsp+arg_8], rdx
0x180043f71  push    rbp
0x180043f72  sub     rsp, 20h
0x180043f76  mov     rbp, rdx
0x180043f79  mov     dword ptr [rbp+38h], 8007000Eh
0x180043f80  mov     rax, 0
0x180043f8a  add     rsp, 20h
0x180043f8e  pop     rbp
0x180043f8f  retn
```
