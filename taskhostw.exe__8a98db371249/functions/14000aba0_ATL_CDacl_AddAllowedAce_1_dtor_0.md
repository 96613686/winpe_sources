# _ATL::CDacl::AddAllowedAce_::_1_::dtor$0

- ea: `0x14000aba0`
- end: `0x14000abac`
- name: `_ATL::CDacl::AddAllowedAce_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140005f00`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::AddAllowedAce_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 104));
}

```

## disassembly

```asm
0x14000aba0  lea     rcx, [rdx+68h]
0x14000aba7  jmp     ??1?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAA@XZ; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(void)
```
