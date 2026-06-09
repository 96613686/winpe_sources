# _ATL::CSid::CSid_::_1_::dtor$0_0

- ea: `0x14000ac10`
- end: `0x14000ac20`
- name: `_ATL::CSid::CSid_::_1_::dtor$0_0`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140006b10`

## pseudocode

```c
__int64 __fastcall ATL::CSid::CSid_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 48) + 88LL));
}

```

## disassembly

```asm
0x14000ac10  mov     rcx, [rdx+30h]
0x14000ac17  add     rcx, 58h ; 'X'
0x14000ac1b  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
