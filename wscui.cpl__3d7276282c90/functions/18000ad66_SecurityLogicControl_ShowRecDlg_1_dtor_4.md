# _SecurityLogicControl::ShowRecDlg_::_1_::dtor$4

- ea: `0x18000ad66`
- end: `0x18000ad72`
- name: `_SecurityLogicControl::ShowRecDlg_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b70`

## pseudocode

```c
void __fastcall SecurityLogicControl::ShowRecDlg_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((void *)(a2 + 120));
}

```

## disassembly

```asm
0x18000ad66  lea     rcx, [rdx+78h]; void *
0x18000ad6d  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
