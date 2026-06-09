# _CPXWizardRegistryLockedTransaction_3_::CPXWizardRegistryLockedTransaction_3__::_1_::dtor$0

- ea: `0x180012d88`
- end: `0x180012d96`
- name: `_CPXWizardRegistryLockedTransaction_3_::CPXWizardRegistryLockedTransaction_3__::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012d8f`

## pseudocode

```c
void __fastcall CPXWizardRegistryLockedTransaction_3_::CPXWizardRegistryLockedTransaction_3__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 112));
}

```

## disassembly

```asm
0x180012d88  mov     rcx, [rdx+70h]
0x180012d8f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
