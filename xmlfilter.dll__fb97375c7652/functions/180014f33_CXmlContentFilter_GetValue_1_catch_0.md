# _CXmlContentFilter::GetValue_::_1_::catch$0

- ea: `0x180014f33`
- end: `0x180014f69`
- name: `_CXmlContentFilter::GetValue_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180014f44`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __noreturn CXmlContentFilter::GetValue_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180014f33  mov     [rsp+arg_8], rdx
0x180014f38  push    rbp
0x180014f39  sub     rsp, 20h
0x180014f3d  mov     rbp, rdx
0x180014f40  mov     rcx, [rbp+28h]
0x180014f44  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180014f4b  mov     edx, 214h
0x180014f50  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180014f55  mov     [rbp+30h], eax
0x180014f58  mov     rax, 0
0x180014f62  add     rsp, 20h
0x180014f66  pop     rbp
0x180014f67  retn
```
