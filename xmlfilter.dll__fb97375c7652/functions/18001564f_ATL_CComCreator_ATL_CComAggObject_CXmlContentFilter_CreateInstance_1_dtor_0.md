# _ATL::CComCreator_ATL::CComAggObject_CXmlContentFilter___::CreateInstance_::_1_::dtor$0

- ea: `0x18001564f`
- end: `0x18001566c`
- name: `_ATL::CComCreator_ATL::CComAggObject_CXmlContentFilter___::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000213c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CXmlContentFilter___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18001564f  push    rbp
0x180015651  sub     rsp, 20h
0x180015655  mov     rbp, rdx
0x180015658  mov     edx, 238h
0x18001565d  mov     rcx, [rbp+28h]; Block
0x180015661  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015666  add     rsp, 20h
0x18001566a  pop     rbp
0x18001566b  retn
```
