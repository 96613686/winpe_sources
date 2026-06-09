# _SecurityLogicControl::GetString_::_1_::catch$9

- ea: `0x18000accc`
- end: `0x18000acf4`
- name: `_SecurityLogicControl::GetString_::_1_::catch$9`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005178`

## pseudocode

```c
__int64 __fastcall SecurityLogicControl::GetString_::_1_::catch_9(__int64 a1, __int64 a2)
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(*(_QWORD *)(a2 + 64));
  return 0;
}

```

## disassembly

```asm
0x18000accc  mov     [rsp+arg_8], rdx
0x18000acd1  push    rbp
0x18000acd2  sub     rsp, 20h
0x18000acd6  mov     rbp, rdx
0x18000acd9  mov     rcx, [rbp+40h]
0x18000acdd  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x18000ace2  nop
0x18000ace3  mov     rax, 0
0x18000aced  add     rsp, 20h
0x18000acf1  pop     rbp
0x18000acf2  retn
```
