# _HrUnregisterWizardComponent_::_1_::dtor$1

- ea: `0x180012e0a`
- end: `0x180012e18`
- name: `_HrUnregisterWizardComponent_::_1_::dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012e11`

## pseudocode

```c
void __fastcall HrUnregisterWizardComponent_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180012e0a  mov     rcx, [rdx+40h]
0x180012e11  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
