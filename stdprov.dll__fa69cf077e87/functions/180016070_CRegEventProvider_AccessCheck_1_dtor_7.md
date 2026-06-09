# _CRegEventProvider::AccessCheck_::_1_::dtor$7

- ea: `0x180016070`
- end: `0x18001607c`
- name: `_CRegEventProvider::AccessCheck_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180009c6c`

## pseudocode

```c
void __fastcall CRegEventProvider::AccessCheck_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  CRegCloseMe::~CRegCloseMe((CRegCloseMe *)(a2 + 104));
}

```

## disassembly

```asm
0x180016070  lea     rcx, [rdx+68h]; this
0x180016077  jmp     ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
```
