# _ATL::CSid::CSid_::_1_::dtor$2_0

- ea: `0x14000ac50`
- end: `0x14000ac60`
- name: `_ATL::CSid::CSid_::_1_::dtor$2_0`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140006b10`

## pseudocode

```c
__int64 __fastcall ATL::CSid::CSid_::_1_::dtor_2_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 48) + 104LL));
}

```

## disassembly

```asm
0x14000ac50  mov     rcx, [rdx+30h]
0x14000ac57  add     rcx, 68h ; 'h'
0x14000ac5b  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
