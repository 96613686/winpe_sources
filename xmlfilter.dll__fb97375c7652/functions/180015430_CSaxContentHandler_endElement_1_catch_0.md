# _CSaxContentHandler::endElement_::_1_::catch$0

- ea: `0x180015430`
- end: `0x180015466`
- name: `_CSaxContentHandler::endElement_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180015441`: `onecoreuap\base\appmodel\search\filters\xml\saxcontenthandler.cpp`

## pseudocode

```c
void __noreturn CSaxContentHandler::endElement_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180015430  mov     [rsp+arg_8], rdx
0x180015435  push    rbp
0x180015436  sub     rsp, 50h
0x18001543a  mov     rbp, rdx
0x18001543d  mov     rcx, [rbp+68h]
0x180015441  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180015448  mov     edx, 11Dh
0x18001544d  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180015452  mov     [rbp+50h], eax
0x180015455  mov     rax, 0
0x18001545f  add     rsp, 50h
0x180015463  pop     rbp
0x180015464  retn
```
