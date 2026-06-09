# ATL::CSid::CSid(ATL::CSid const &)

- ea: `0x14004ab5c`
- end: `0x14004ac08`
- name: `??0CSid@ATL@@QEAA@AEBV01@@Z`
- size: `172`
- prototype: `ATL::CSid *__fastcall(ATL::CSid *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14004aab0`

## callees

- `0x140003690`
- `0x14000b3b0`
- `0x1400396dc`
- `0x14004ab5c`
- `0x14004bb5c`
- `0x14004f06c`

## import_xrefs

- `ADVAPI32!CopySid` at `0x14004abe3`
- `ADVAPI32!CopySid` at `0x14004abe3`
- `ADVAPI32!GetLengthSid` at `0x14004abd3`
- `ADVAPI32!GetLengthSid` at `0x14004abd3`

## pseudocode

```c
ATL::CSid *__fastcall ATL::CSid::CSid(ATL::CSid *this, const struct ATL::CSid *a2)
{
  DWORD LengthSid; // eax
  int Error; // eax

  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (_QWORD *)this + 11,
    (const void **)a2 + 11);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (_QWORD *)this + 12,
    (const void **)a2 + 12);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (_QWORD *)this + 13,
    (const void **)a2 + 13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>((_QWORD *)this + 14);
  if ( *((_BYTE *)a2 + 76) )
  {
    if ( !ATL::CSid::IsValid(a2) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid((char *)a2 + 8);
    if ( !CopySid(LengthSid, (char *)this + 8, (char *)a2 + 8) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  return this;
}

```

## disassembly

```asm
0x14004ab5c  mov     [rsp+arg_0], rbx
0x14004ab61  push    rdi
0x14004ab62  sub     rsp, 20h
0x14004ab66  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x14004ab6d  mov     rbx, rdx
0x14004ab70  mov     [rcx], rax
0x14004ab73  mov     rdi, rcx
0x14004ab76  mov     al, [rdx+4Ch]
0x14004ab79  mov     [rcx+4Ch], al
0x14004ab7c  mov     eax, [rdx+50h]
0x14004ab7f  add     rdx, 58h ; 'X'
0x14004ab83  mov     [rcx+50h], eax
0x14004ab86  add     rcx, 58h ; 'X'
0x14004ab8a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14004ab8f  lea     rdx, [rbx+60h]
0x14004ab93  lea     rcx, [rdi+60h]
0x14004ab97  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14004ab9c  lea     rdx, [rbx+68h]
0x14004aba0  lea     rcx, [rdi+68h]
0x14004aba4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14004aba9  lea     rcx, [rdi+70h]
0x14004abad  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14004abb2  cmp     byte ptr [rbx+4Ch], 0
0x14004abb6  jz      short loc_14004ABFA
0x14004abb8  mov     rcx, rbx; this
0x14004abbb  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x14004abc0  test    al, al
0x14004abc2  jnz     short loc_14004ABCF
0x14004abc4  mov     ecx, 80070057h; int
0x14004abc9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004abcf  lea     rcx, [rbx+8]; pSid
0x14004abd3  call    cs:__imp_GetLengthSid
0x14004abd9  mov     ecx, eax; nDestinationSidLength
0x14004abdb  lea     rdx, [rdi+8]; pDestinationSid
0x14004abdf  lea     r8, [rbx+8]; pSourceSid
0x14004abe3  call    cs:__imp_CopySid
0x14004abe9  test    eax, eax
0x14004abeb  jnz     short loc_14004ABFA
0x14004abed  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14004abf2  mov     ecx, eax; int
0x14004abf4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004abfa  mov     rbx, [rsp+28h+arg_0]
0x14004abff  mov     rax, rdi
0x14004ac02  add     rsp, 20h
0x14004ac06  pop     rdi
0x14004ac07  retn
```
