# _CImpReg::MethodAsync_::_1_::dtor$12

- ea: `0x180015ce0`
- end: `0x180015cee`
- name: `_CImpReg::MethodAsync_::_1_::dtor$12`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180015ce7`

## pseudocode

```c
void __fastcall CImpReg::MethodAsync_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)(a2 + 216));
}

```

## disassembly

```asm
0x180015ce0  lea     rcx, [rdx+0D8h]
0x180015ce7  jmp     cs:__imp_??1CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::~CNtSecurityDescriptor(void)
```
