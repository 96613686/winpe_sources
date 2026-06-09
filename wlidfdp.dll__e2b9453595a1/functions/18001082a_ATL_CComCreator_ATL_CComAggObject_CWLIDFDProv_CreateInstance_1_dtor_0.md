# _ATL::CComCreator_ATL::CComAggObject_CWLIDFDProv___::CreateInstance_::_1_::dtor$0

- ea: `0x18001082a`
- end: `0x180010847`
- name: `_ATL::CComCreator_ATL::CComAggObject_CWLIDFDProv___::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002814`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CWLIDFDProv___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18001082a  push    rbp
0x18001082c  sub     rsp, 20h
0x180010830  mov     rbp, rdx
0x180010833  mov     edx, 0A8h
0x180010838  mov     rcx, [rbp+28h]; Block
0x18001083c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010841  add     rsp, 20h
0x180010845  pop     rbp
0x180010846  retn
```
