# _CXmlContentFilter::FinalConstruct_::_1_::catch$1

- ea: `0x180014e6d`
- end: `0x180014ea3`
- name: `_CXmlContentFilter::FinalConstruct_::_1_::catch$1`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180014e7e`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::FinalConstruct_::_1_::catch_1()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180014e6d  mov     [rsp+arg_8], rdx
0x180014e72  push    rbp
0x180014e73  sub     rsp, 30h
0x180014e77  mov     rbp, rdx
0x180014e7a  mov     rcx, [rbp+38h]
0x180014e7e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180014e85  mov     edx, 51h ; 'Q'
0x180014e8a  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180014e8f  mov     [rbp+40h], eax
0x180014e92  mov     rax, 0
0x180014e9c  add     rsp, 30h
0x180014ea0  pop     rbp
0x180014ea1  retn
```
