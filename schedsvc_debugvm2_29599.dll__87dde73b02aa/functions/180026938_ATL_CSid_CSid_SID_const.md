# ATL::CSid::CSid(_SID const &)

- ea: `0x180026938`
- end: `0x1800269e6`
- name: `??0CSid@ATL@@QEAA@AEBU_SID@@@Z`
- size: `174`
- prototype: `_QWORD(ATL::CSid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800269f0`

## callees

- `0x180026938`
- `0x180027bf0`
- `0x1800504b4`
- `0x1800528ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002699a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002699a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002698d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002698d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800269b2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800269b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ATL::CSid *__fastcall ATL::CSid::CSid(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  unsigned int Error; // eax

  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 96);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 104);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 112);
  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::PrivateAtlThrow(0x80070057);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, a2) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::PrivateAtlThrow(Error);
  }
  return this;
}

```

## disassembly

```asm
0x180026938  mov     [rsp+arg_8], rbx
0x18002693d  mov     [rsp+arg_0], rcx
0x180026942  push    rdi
0x180026943  sub     rsp, 20h
0x180026947  mov     rdi, rdx
0x18002694a  mov     rbx, rcx
0x18002694d  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180026954  mov     [rcx], rax
0x180026957  mov     byte ptr [rcx+4Ch], 0
0x18002695b  mov     dword ptr [rcx+50h], 7
0x180026962  add     rcx, 58h ; 'X'
0x180026966  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002696b  nop
0x18002696c  lea     rcx, [rbx+60h]
0x180026970  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180026975  nop
0x180026976  lea     rcx, [rbx+68h]
0x18002697a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002697f  nop
0x180026980  lea     rcx, [rbx+70h]
0x180026984  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180026989  nop
0x18002698a  mov     rcx, rdi; pSid
0x18002698d  call    cs:__imp_IsValidSid
0x180026993  test    eax, eax
0x180026995  jz      short loc_1800269DB
0x180026997  mov     rcx, rdi; pSid
0x18002699a  call    cs:__imp_GetLengthSid
0x1800269a0  cmp     eax, 44h ; 'D'
0x1800269a3  ja      short loc_1800269DB
0x1800269a5  mov     byte ptr [rbx+4Ch], 1
0x1800269a9  lea     rdx, [rbx+8]; pDestinationSid
0x1800269ad  mov     r8, rdi; pSourceSid
0x1800269b0  mov     ecx, eax; nDestinationSidLength
0x1800269b2  call    cs:__imp_CopySid
0x1800269b8  test    eax, eax
0x1800269ba  jnz     short loc_1800269CD
0x1800269bc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800269c1  mov     byte ptr [rbx+4Ch], 0
0x1800269c5  mov     ecx, eax; unsigned int
0x1800269c7  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800269cd  mov     rax, rbx
0x1800269d0  mov     rbx, [rsp+28h+arg_8]
0x1800269d5  add     rsp, 20h
0x1800269d9  pop     rdi
0x1800269da  retn
0x1800269db  mov     ecx, 80070057h; unsigned int
0x1800269e0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
