# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x14000770a`
- end: `0x14000772a`
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
0x14000770a  push    rbp
0x14000770c  sub     rsp, 20h
0x140007710  mov     rbp, rdx
0x140007713  mov     rax, [rcx]
0x140007716  xor     ecx, ecx
0x140007718  cmp     dword ptr [rax], 0C0000017h
0x14000771e  setz    cl
0x140007721  mov     eax, ecx
0x140007723  add     rsp, 20h
0x140007727  pop     rbp
0x140007728  retn
```
