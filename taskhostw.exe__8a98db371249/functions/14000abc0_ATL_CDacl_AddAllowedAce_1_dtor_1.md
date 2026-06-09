# _ATL::CDacl::AddAllowedAce_::_1_::dtor$1

- ea: `0x14000abc0`
- end: `0x14000abce`
- name: `_ATL::CDacl::AddAllowedAce_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, authz_impersonation`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000abc7`

## pseudocode

```c
void __fastcall ATL::CDacl::AddAllowedAce_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x14000abc0  mov     rcx, [rdx+30h]
0x14000abc7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
