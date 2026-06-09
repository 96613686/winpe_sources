# _CWmpClassFactory::CreateInstance_::_1_::catch$4

- ea: `0x180043787`
- end: `0x1800437ac`
- name: `_CWmpClassFactory::CreateInstance_::_1_::catch$4`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CWmpClassFactory::CreateInstance_::_1_::catch_4(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x180043787  mov     [rsp+arg_8], rdx
0x18004378c  push    rbp
0x18004378d  sub     rsp, 20h
0x180043791  mov     rbp, rdx
0x180043794  mov     dword ptr [rbp+38h], 8007000Eh
0x18004379b  mov     rax, 0
0x1800437a5  add     rsp, 20h
0x1800437a9  pop     rbp
0x1800437aa  retn
```
