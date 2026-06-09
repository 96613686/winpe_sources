# _CXmlContentFilter::Init_::_1_::catch$0

- ea: `0x180014f6f`
- end: `0x180014fa5`
- name: `_CXmlContentFilter::Init_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180014f80`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::Init_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180014f6f  mov     [rsp+arg_8], rdx
0x180014f74  push    rbp
0x180014f75  sub     rsp, 20h
0x180014f79  mov     rbp, rdx
0x180014f7c  mov     rcx, [rbp+28h]
0x180014f80  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180014f87  mov     edx, 17Fh
0x180014f8c  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180014f91  mov     [rbp+40h], eax
0x180014f94  mov     rax, 0
0x180014f9e  add     rsp, 20h
0x180014fa2  pop     rbp
0x180014fa3  retn
```
