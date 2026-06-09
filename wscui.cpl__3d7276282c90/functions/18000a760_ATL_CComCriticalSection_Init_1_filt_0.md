# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000a760`
- end: `0x18000a780`
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
0x18000a760  push    rbp
0x18000a762  sub     rsp, 20h
0x18000a766  mov     rbp, rdx
0x18000a769  mov     rax, [rcx]
0x18000a76c  xor     ecx, ecx
0x18000a76e  cmp     dword ptr [rax], 0C0000017h
0x18000a774  setz    cl
0x18000a777  mov     eax, ecx
0x18000a779  add     rsp, 20h
0x18000a77d  pop     rbp
0x18000a77e  retn
```
