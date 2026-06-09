# _CXmlContentFilter::Load_::_1_::dtor$1

- ea: `0x18001501e`
- end: `0x18001503d`
- name: `_CXmlContentFilter::Load_::_1_::dtor$1`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18000213c`

## pseudocode

```c
void __fastcall CXmlContentFilter::Load_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x18001501e  push    rbp
0x180015020  sub     rsp, 20h
0x180015024  mov     rbp, rdx
0x180015027  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001502e  mov     rcx, [rbp+30h]; Block
0x180015032  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015037  add     rsp, 20h
0x18001503b  pop     rbp
0x18001503c  retn
```
