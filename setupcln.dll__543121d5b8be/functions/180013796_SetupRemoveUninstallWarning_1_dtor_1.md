# _SetupRemoveUninstallWarning_::_1_::dtor$1

- ea: `0x180013796`
- end: `0x1800137a2`
- name: `_SetupRemoveUninstallWarning_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180003c40`

## pseudocode

```c
__int64 __fastcall SetupRemoveUninstallWarning_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 56);
}

```

## disassembly

```asm
0x180013796  lea     rcx, [rdx+38h]
0x18001379d  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
