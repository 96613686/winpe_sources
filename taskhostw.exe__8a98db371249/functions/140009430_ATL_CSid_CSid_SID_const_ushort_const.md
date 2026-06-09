# ATL::CSid::CSid(_SID const *,ushort const *)

- ea: `0x140009430`
- end: `0x1400094a5`
- name: `??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z`
- size: `117`
- prototype: `ATL::CSid *__fastcall(ATL::CSid *this, const struct _SID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400022d0`

## callees

- `0x140002ff0`
- `0x140007298`
- `0x140009430`
- `0x1400097f8`

## pseudocode

```c
ATL::CSid *__fastcall ATL::CSid::CSid(ATL::CSid *this, const struct _SID *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // r8

  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 96);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 104);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 112);
  if ( !ATL::CSid::LoadAccount(this, a2, v5) )
    ATL::AtlThrowLastWin32();
  return this;
}

```

## disassembly

```asm
0x140009430  mov     [rsp+arg_8], rbx
0x140009435  mov     [rsp+arg_0], rcx
0x14000943a  push    rdi
0x14000943b  sub     rsp, 20h
0x14000943f  mov     rbx, rdx
0x140009442  mov     rdi, rcx
0x140009445  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x14000944c  mov     [rcx], rax
0x14000944f  mov     byte ptr [rcx+4Ch], 0
0x140009453  mov     dword ptr [rcx+50h], 7
0x14000945a  add     rcx, 58h ; 'X'
0x14000945e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140009463  nop
0x140009464  lea     rcx, [rdi+60h]
0x140009468  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14000946d  nop
0x14000946e  lea     rcx, [rdi+68h]
0x140009472  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140009477  nop
0x140009478  lea     rcx, [rdi+70h]
0x14000947c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140009481  nop
0x140009482  mov     rdx, rbx; struct _SID *
0x140009485  mov     rcx, rdi; this
0x140009488  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x14000948d  test    al, al
0x14000948f  jnz     short loc_140009497
0x140009491  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140009497  mov     rax, rdi
0x14000949a  mov     rbx, [rsp+28h+arg_8]
0x14000949f  add     rsp, 20h
0x1400094a3  pop     rdi
0x1400094a4  retn
```
