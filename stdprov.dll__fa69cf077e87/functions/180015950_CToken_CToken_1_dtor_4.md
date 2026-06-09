# _CToken::CToken_::_1_::dtor$4

- ea: `0x180015950`
- end: `0x18001595c`
- name: `_CToken::CToken_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180008fa0`

## pseudocode

```c
void __fastcall CToken::CToken_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 88));
}

```

## disassembly

```asm
0x180015950  mov     rcx, [rdx+58h]; void *
0x180015957  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
