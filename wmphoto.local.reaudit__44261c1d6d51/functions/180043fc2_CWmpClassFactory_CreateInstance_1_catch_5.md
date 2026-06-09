# _CWmpClassFactory::CreateInstance_::_1_::catch$5

- ea: `0x180043fc2`
- end: `0x180043fe7`
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
0x180043fc2  mov     [rsp+arg_8], rdx
0x180043fc7  push    rbp
0x180043fc8  sub     rsp, 20h
0x180043fcc  mov     rbp, rdx
0x180043fcf  mov     dword ptr [rbp+38h], 8007000Eh
0x180043fd6  mov     rax, 0
0x180043fe0  add     rsp, 20h
0x180043fe4  pop     rbp
0x180043fe5  retn
```
