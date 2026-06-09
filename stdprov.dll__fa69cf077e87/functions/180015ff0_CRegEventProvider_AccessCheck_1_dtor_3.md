# _CRegEventProvider::AccessCheck_::_1_::dtor$3

- ea: `0x180015ff0`
- end: `0x180015ffc`
- name: `_CRegEventProvider::AccessCheck_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000bbc8`

## pseudocode

```c
void __fastcall CRegEventProvider::AccessCheck_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CPropertyName::~CPropertyName((CPropertyName *)(a2 + 128));
}

```

## disassembly

```asm
0x180015ff0  lea     rcx, [rdx+80h]; this
0x180015ff7  jmp     ??1CPropertyName@@QEAA@XZ; CPropertyName::~CPropertyName(void)
```
