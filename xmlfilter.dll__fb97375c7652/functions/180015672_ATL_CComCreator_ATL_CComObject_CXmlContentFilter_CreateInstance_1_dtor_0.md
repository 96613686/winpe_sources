# _ATL::CComCreator_ATL::CComObject_CXmlContentFilter___::CreateInstance_::_1_::dtor$0

- ea: `0x180015672`
- end: `0x18001568f`
- name: `_ATL::CComCreator_ATL::CComObject_CXmlContentFilter___::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000213c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CXmlContentFilter___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x180015672  push    rbp
0x180015674  sub     rsp, 20h
0x180015678  mov     rbp, rdx
0x18001567b  mov     edx, 220h
0x180015680  mov     rcx, [rbp+20h]; Block
0x180015684  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015689  add     rsp, 20h
0x18001568d  pop     rbp
0x18001568e  retn
```
