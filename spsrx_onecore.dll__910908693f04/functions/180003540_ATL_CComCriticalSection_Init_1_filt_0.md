# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180003540`
- end: `0x180003560`
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
0x180003540  push    rbp
0x180003542  sub     rsp, 20h
0x180003546  mov     rbp, rdx
0x180003549  mov     rax, [rcx]
0x18000354c  xor     ecx, ecx
0x18000354e  cmp     dword ptr [rax], 0C0000017h
0x180003554  setz    cl
0x180003557  mov     eax, ecx
0x180003559  add     rsp, 20h
0x18000355d  pop     rbp
0x18000355e  retn
```
