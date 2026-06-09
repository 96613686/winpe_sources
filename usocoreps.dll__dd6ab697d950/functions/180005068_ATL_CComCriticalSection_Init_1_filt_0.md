# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180005068`
- end: `0x180005088`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: `_BOOL8 __fastcall(_DWORD **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall ATL::CComCriticalSection::Init_::_1_::filt_0(_DWORD **a1)
{
  return **a1 == -1073741801;
}

```

## disassembly

```asm
0x180005068  push    rbp
0x18000506a  sub     rsp, 20h
0x18000506e  mov     rbp, rdx
0x180005071  mov     rax, [rcx]
0x180005074  xor     ecx, ecx
0x180005076  cmp     dword ptr [rax], 0C0000017h
0x18000507c  setz    cl
0x18000507f  mov     eax, ecx
0x180005081  add     rsp, 20h
0x180005085  pop     rbp
0x180005086  retn
```
