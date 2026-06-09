# _CXmlContentFilter::Load_::_1_::dtor$0

- ea: `0x180014fab`
- end: `0x180014fca`
- name: `_CXmlContentFilter::Load_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18000213c`

## pseudocode

```c
void __fastcall CXmlContentFilter::Load_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180014fab  push    rbp
0x180014fad  sub     rsp, 20h
0x180014fb1  mov     rbp, rdx
0x180014fb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014fbb  mov     rcx, [rbp+40h]; Block
0x180014fbf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014fc4  add     rsp, 20h
0x180014fc8  pop     rbp
0x180014fc9  retn
```
