# _SecurityLogicControl::ShowRecDlg_::_1_::dtor$1

- ea: `0x18000ad30`
- end: `0x18000ad3c`
- name: `_SecurityLogicControl::ShowRecDlg_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b70`

## pseudocode

```c
void __fastcall SecurityLogicControl::ShowRecDlg_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((void *)(a2 + 96));
}

```

## disassembly

```asm
0x18000ad30  lea     rcx, [rdx+60h]; void *
0x18000ad37  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
