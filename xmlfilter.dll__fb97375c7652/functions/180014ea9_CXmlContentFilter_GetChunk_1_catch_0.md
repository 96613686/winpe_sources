# _CXmlContentFilter::GetChunk_::_1_::catch$0

- ea: `0x180014ea9`
- end: `0x180014edf`
- name: `_CXmlContentFilter::GetChunk_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180014eba`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::GetChunk_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180014ea9  mov     [rsp+arg_8], rdx
0x180014eae  push    rbp
0x180014eaf  sub     rsp, 30h
0x180014eb3  mov     rbp, rdx
0x180014eb6  mov     rcx, [rbp+38h]
0x180014eba  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180014ec1  mov     edx, 1C4h
0x180014ec6  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180014ecb  mov     [rbp+40h], eax
0x180014ece  mov     rax, 0
0x180014ed8  add     rsp, 30h
0x180014edc  pop     rbp
0x180014edd  retn
```
