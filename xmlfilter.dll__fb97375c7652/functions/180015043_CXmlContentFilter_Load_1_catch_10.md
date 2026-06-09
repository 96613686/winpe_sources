# _CXmlContentFilter::Load_::_1_::catch$10

- ea: `0x180015043`
- end: `0x18001507c`
- name: `_CXmlContentFilter::Load_::_1_::catch$10`
- size: `57`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180015054`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::Load_::_1_::catch_10()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180015043  mov     [rsp+arg_8], rdx
0x180015048  push    rbp
0x180015049  sub     rsp, 30h
0x18001504d  mov     rbp, rdx
0x180015050  mov     rcx, [rbp+78h]
0x180015054  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18001505b  mov     edx, 0F6h
0x180015060  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180015065  mov     [rbp+98h], eax
0x18001506b  mov     rax, 0
0x180015075  add     rsp, 30h
0x180015079  pop     rbp
0x18001507a  retn
```
