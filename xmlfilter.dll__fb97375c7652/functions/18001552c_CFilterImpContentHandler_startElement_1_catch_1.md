# _CFilterImpContentHandler::startElement_::_1_::catch$1

- ea: `0x18001552c`
- end: `0x180015565`
- name: `_CFilterImpContentHandler::startElement_::_1_::catch$1`
- size: `57`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ee4`

## string_xrefs

- `0x180015540`: `onecoreuap\base\appmodel\search\filters\xml\filterimpcontenthandler.cpp`

## pseudocode

```c
void __noreturn CFilterImpContentHandler::startElement_::_1_::catch_1()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x18001552c  mov     [rsp+arg_8], rdx
0x180015531  push    rbp
0x180015532  sub     rsp, 50h
0x180015536  mov     rbp, rdx
0x180015539  mov     rcx, [rbp+0E8h]
0x180015540  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180015547  mov     edx, 1A8h
0x18001554c  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180015551  mov     [rbp+54h], eax
0x180015554  mov     rax, 0
0x18001555e  add     rsp, 50h
0x180015562  pop     rbp
0x180015563  retn
```
