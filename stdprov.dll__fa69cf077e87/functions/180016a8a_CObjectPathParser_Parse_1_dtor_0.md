# _CObjectPathParser::Parse_::_1_::dtor$0

- ea: `0x180016a8a`
- end: `0x180016a96`
- name: `_CObjectPathParser::Parse_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180008fa0`

## pseudocode

```c
void __fastcall CObjectPathParser::Parse_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 168));
}

```

## disassembly

```asm
0x180016a8a  mov     rcx, [rdx+0A8h]; void *
0x180016a91  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
