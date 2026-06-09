# _ATL::CSid::CSid_::_1_::dtor$0

- ea: `0x14000ab20`
- end: `0x14000ab30`
- name: `_ATL::CSid::CSid_::_1_::dtor$0`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140006b10`

## pseudocode

```c
__int64 __fastcall ATL::CSid::CSid_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 32) + 88LL));
}

```

## disassembly

```asm
0x14000ab20  mov     rcx, [rdx+20h]
0x14000ab27  add     rcx, 58h ; 'X'
0x14000ab2b  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
