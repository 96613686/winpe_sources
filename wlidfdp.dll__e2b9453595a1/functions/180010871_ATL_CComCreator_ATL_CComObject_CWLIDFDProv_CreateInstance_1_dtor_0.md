# _ATL::CComCreator_ATL::CComObject_CWLIDFDProv___::CreateInstance_::_1_::dtor$0

- ea: `0x180010871`
- end: `0x18001088e`
- name: `_ATL::CComCreator_ATL::CComObject_CWLIDFDProv___::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002814`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CWLIDFDProv___::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x180010871  push    rbp
0x180010873  sub     rsp, 20h
0x180010877  mov     rbp, rdx
0x18001087a  mov     edx, 90h
0x18001087f  mov     rcx, [rbp+20h]; Block
0x180010883  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010888  add     rsp, 20h
0x18001088c  pop     rbp
0x18001088d  retn
```
