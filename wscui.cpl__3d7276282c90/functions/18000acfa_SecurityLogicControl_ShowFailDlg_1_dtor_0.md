# _SecurityLogicControl::ShowFailDlg_::_1_::dtor$0

- ea: `0x18000acfa`
- end: `0x18000ad06`
- name: `_SecurityLogicControl::ShowFailDlg_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b70`

## pseudocode

```c
void __fastcall SecurityLogicControl::ShowFailDlg_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((void *)(a2 + 272));
}

```

## disassembly

```asm
0x18000acfa  lea     rcx, [rdx+110h]; void *
0x18000ad01  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
