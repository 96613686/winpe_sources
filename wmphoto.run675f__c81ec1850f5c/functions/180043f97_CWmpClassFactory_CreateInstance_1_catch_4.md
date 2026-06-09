# _CWmpClassFactory::CreateInstance_::_1_::catch$4

- ea: `0x180043f97`
- end: `0x180043fbc`
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
0x180043f97  mov     [rsp+arg_8], rdx
0x180043f9c  push    rbp
0x180043f9d  sub     rsp, 20h
0x180043fa1  mov     rbp, rdx
0x180043fa4  mov     dword ptr [rbp+38h], 8007000Eh
0x180043fab  mov     rax, 0
0x180043fb5  add     rsp, 20h
0x180043fb9  pop     rbp
0x180043fba  retn
```
