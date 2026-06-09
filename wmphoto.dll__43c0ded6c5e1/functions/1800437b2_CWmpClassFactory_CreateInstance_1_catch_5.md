# _CWmpClassFactory::CreateInstance_::_1_::catch$5

- ea: `0x1800437b2`
- end: `0x1800437d7`
- name: `_CWmpClassFactory::CreateInstance_::_1_::catch$5`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CWmpClassFactory::CreateInstance_::_1_::catch_5(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x1800437b2  mov     [rsp+arg_8], rdx
0x1800437b7  push    rbp
0x1800437b8  sub     rsp, 20h
0x1800437bc  mov     rbp, rdx
0x1800437bf  mov     dword ptr [rbp+38h], 8007000Eh
0x1800437c6  mov     rax, 0
0x1800437d0  add     rsp, 20h
0x1800437d4  pop     rbp
0x1800437d5  retn
```
