# _CSaxContentHandler::startElement_::_1_::catch$0

- ea: `0x18001546c`
- end: `0x1800154a2`
- name: `_CSaxContentHandler::startElement_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ee4`

## string_xrefs

- `0x18001547d`: `onecoreuap\base\appmodel\search\filters\xml\saxcontenthandler.cpp`

## pseudocode

```c
void __noreturn CSaxContentHandler::startElement_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x18001546c  mov     [rsp+arg_8], rdx
0x180015471  push    rbp
0x180015472  sub     rsp, 50h
0x180015476  mov     rbp, rdx
0x180015479  mov     rcx, [rbp+68h]
0x18001547d  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180015484  mov     edx, 0E8h
0x180015489  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18001548e  mov     [rbp+50h], eax
0x180015491  mov     rax, 0
0x18001549b  add     rsp, 50h
0x18001549f  pop     rbp
0x1800154a0  retn
```
