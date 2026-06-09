# _DuiView::DisplayDuiFromEapConfig_::_1_::dtor$0

- ea: `0x18001c3f4`
- end: `0x18001c402`
- name: `_DuiView::DisplayDuiFromEapConfig_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001c3fb`

## pseudocode

```c
void __fastcall DuiView::DisplayDuiFromEapConfig_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 120));
}

```

## disassembly

```asm
0x18001c3f4  mov     rcx, [rdx+78h]
0x18001c3fb  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
