# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180012cf6`
- end: `0x180012d16`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: ``
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
0x180012cf6  push    rbp
0x180012cf8  sub     rsp, 20h
0x180012cfc  mov     rbp, rdx
0x180012cff  mov     rax, [rcx]
0x180012d02  xor     ecx, ecx
0x180012d04  cmp     dword ptr [rax], 0C0000017h
0x180012d0a  setz    cl
0x180012d0d  mov     eax, ecx
0x180012d0f  add     rsp, 20h
0x180012d13  pop     rbp
0x180012d14  retn
```
