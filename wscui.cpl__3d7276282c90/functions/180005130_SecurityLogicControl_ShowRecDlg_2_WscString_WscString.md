# _SecurityLogicControl::ShowRecDlg_::_2_::WscString::WscString

- ea: `0x180005130`
- end: `0x180005147`
- name: `_SecurityLogicControl::ShowRecDlg_::_2_::WscString::WscString`
- size: `23`
- prototype: `void(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004838`

## pseudocode

```c
void __fastcall SecurityLogicControl::ShowRecDlg_::_2_::WscString::WscString(void *a1)
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1);
}

```

## disassembly

```asm
0x180005130  push    rbx
0x180005132  sub     rsp, 20h
0x180005136  mov     rbx, rcx
0x180005139  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000513e  mov     rax, rbx
0x180005141  add     rsp, 20h
0x180005145  pop     rbx
0x180005146  retn
```
