# _SecurityLogicControl::GetString_::_1_::dtor$0

- ea: `0x18000ac2e`
- end: `0x18000ac54`
- name: `_SecurityLogicControl::GetString_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001b70`
- `0x18000ac2e`

## pseudocode

```c
void __fastcall SecurityLogicControl::GetString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 56) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 56) &= ~1u;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(*(void **)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18000ac2e  push    rbp
0x18000ac30  sub     rsp, 20h
0x18000ac34  mov     rbp, rdx
0x18000ac37  mov     eax, [rbp+38h]
0x18000ac3a  and     eax, 1
0x18000ac3d  test    eax, eax
0x18000ac3f  jz      short loc_18000AC4E
0x18000ac41  and     dword ptr [rbp+38h], 0FFFFFFFEh
0x18000ac45  mov     rcx, [rbp+40h]; void *
0x18000ac49  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000ac4e  add     rsp, 20h
0x18000ac52  pop     rbp
0x18000ac53  retn
```
