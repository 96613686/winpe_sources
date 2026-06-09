# _ATL::CSid::CSid_::_1_::dtor$3

- ea: `0x14000ab80`
- end: `0x14000ab90`
- name: `_ATL::CSid::CSid_::_1_::dtor$3`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140006b10`

## pseudocode

```c
__int64 __fastcall ATL::CSid::CSid_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 32) + 112LL));
}

```

## disassembly

```asm
0x14000ab80  mov     rcx, [rdx+20h]
0x14000ab87  add     rcx, 70h ; 'p'
0x14000ab8b  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
