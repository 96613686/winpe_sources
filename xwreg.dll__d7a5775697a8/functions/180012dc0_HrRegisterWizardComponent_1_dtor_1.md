# _HrRegisterWizardComponent_::_1_::dtor$1

- ea: `0x180012dc0`
- end: `0x180012dce`
- name: `_HrRegisterWizardComponent_::_1_::dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012dc7`

## pseudocode

```c
void __fastcall HrRegisterWizardComponent_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 168));
}

```

## disassembly

```asm
0x180012dc0  mov     rcx, [rdx+0A8h]
0x180012dc7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
