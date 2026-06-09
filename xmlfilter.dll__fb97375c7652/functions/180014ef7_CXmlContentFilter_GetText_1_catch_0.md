# _CXmlContentFilter::GetText_::_1_::catch$0

- ea: `0x180014ef7`
- end: `0x180014f2d`
- name: `_CXmlContentFilter::GetText_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180014f08`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::GetText_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180014ef7  mov     [rsp+arg_8], rdx
0x180014efc  push    rbp
0x180014efd  sub     rsp, 20h
0x180014f01  mov     rbp, rdx
0x180014f04  mov     rcx, [rbp+28h]
0x180014f08  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180014f0f  mov     edx, 1ECh
0x180014f14  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180014f19  mov     [rbp+30h], eax
0x180014f1c  mov     rax, 0
0x180014f26  add     rsp, 20h
0x180014f2a  pop     rbp
0x180014f2b  retn
```
