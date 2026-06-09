# _CFilterImpContentHandler::endElement_::_1_::catch$0

- ea: `0x1800154de`
- end: `0x180015514`
- name: `_CFilterImpContentHandler::endElement_::_1_::catch$0`
- size: `54`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ee4`

## string_xrefs

- `0x1800154ef`: `onecoreuap\base\appmodel\search\filters\xml\filterimpcontenthandler.cpp`

## pseudocode

```c
void __noreturn CFilterImpContentHandler::endElement_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x1800154de  mov     [rsp+arg_8], rdx
0x1800154e3  push    rbp
0x1800154e4  sub     rsp, 50h
0x1800154e8  mov     rbp, rdx
0x1800154eb  mov     rcx, [rbp+58h]
0x1800154ef  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800154f6  mov     edx, 1F1h
0x1800154fb  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180015500  mov     [rbp+60h], eax
0x180015503  mov     rax, 0
0x18001550d  add     rsp, 50h
0x180015511  pop     rbp
0x180015512  retn
```
