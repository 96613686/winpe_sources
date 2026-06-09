# _CXmlContentFilter::Load_::_1_::catch$7

- ea: `0x180014fd0`
- end: `0x180015006`
- name: `_CXmlContentFilter::Load_::_1_::catch$7`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180014fe1`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::Load_::_1_::catch_7()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180014fd0  mov     [rsp+arg_8], rdx
0x180014fd5  push    rbp
0x180014fd6  sub     rsp, 20h
0x180014fda  mov     rbp, rdx
0x180014fdd  mov     rcx, [rbp+28h]
0x180014fe1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180014fe8  mov     edx, 124h
0x180014fed  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180014ff2  mov     [rbp+40h], eax
0x180014ff5  mov     rax, 0
0x180014fff  add     rsp, 20h
0x180015003  pop     rbp
0x180015004  retn
```
