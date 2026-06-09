# _CheckForSaclPriv_::_1_::dtor$0

- ea: `0x180016c85`
- end: `0x180016c91`
- name: `_CheckForSaclPriv_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000bb30`

## pseudocode

```c
void __fastcall CheckForSaclPriv_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CCloseMe::~CCloseMe((void **)(a2 + 56));
}

```

## disassembly

```asm
0x180016c85  lea     rcx, [rdx+38h]; this
0x180016c8c  jmp     ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
```
