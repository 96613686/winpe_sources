# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180041b98`
- end: `0x180041ccd`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `309`
- prototype: `__int64(ATL::CSid *__hidden this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, unsigned __int8, ...)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180042404`
- `0x180045824`

## callees

- `0x180007598`
- `0x180010290`
- `0x180041b64`
- `0x180041b98`
- `0x18004266c`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!GetSidLengthRequired` at `0x180041c1f`
- `ADVAPI32!GetSidLengthRequired` at `0x180041c1f`
- `ADVAPI32!InitializeSid` at `0x180041c3e`
- `ADVAPI32!InitializeSid` at `0x180041c3e`
- `ADVAPI32!GetSidSubAuthority` at `0x180041c79`
- `ADVAPI32!GetSidSubAuthority` at `0x180041c79`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, UCHAR a3, ...)
{
  va_list v5; // rbp
  DWORD i; // esi
  DWORD v7; // ebx
  struct _SID Sid[6]; // [rsp+40h] [rbp-88h] BYREF
  va_list va; // [rsp+E8h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 96);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 104);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 112);
  if ( !a3 || GetSidLengthRequired(a3) > 0x44 )
    ATL::AtlThrowImpl(-2147024809);
  if ( !InitializeSid(Sid, pIdentifierAuthority, a3) )
    ATL::AtlThrowLastWin32();
  va_copy(v5, va);
  for ( i = 0; i < a3; *GetSidSubAuthority(Sid, i++) = v7 )
  {
    v5 += 8;
    v7 = *((_DWORD *)v5 - 2);
  }
  ATL::CSid::Copy(this, Sid);
  *((_DWORD *)this + 20) = 8;
  return this;
}

```

## disassembly

```asm
0x180041b98  mov     [rsp+nSubAuthorityCount], r8b
0x180041b9d  mov     [rsp+arg_18], r9
0x180041ba2  push    rbx
0x180041ba3  push    rbp
0x180041ba4  push    rsi
0x180041ba5  push    rdi
0x180041ba6  sub     rsp, 0A8h
0x180041bad  mov     [rsp+0C8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x180041bb6  mov     rax, cs:__security_cookie
0x180041bbd  xor     rax, rsp
0x180041bc0  mov     [rsp+0C8h+var_38], rax
0x180041bc8  mov     rbx, rdx
0x180041bcb  mov     rdi, rcx
0x180041bce  mov     [rsp+0C8h+var_A0], rcx
0x180041bd3  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180041bda  mov     [rcx], rax
0x180041bdd  mov     byte ptr [rcx+4Ch], 0
0x180041be1  mov     dword ptr [rcx+50h], 7
0x180041be8  add     rcx, 58h ; 'X'
0x180041bec  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041bf1  nop
0x180041bf2  lea     rcx, [rdi+60h]
0x180041bf6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041bfb  nop
0x180041bfc  lea     rcx, [rdi+68h]
0x180041c00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041c05  nop
0x180041c06  lea     rcx, [rdi+70h]
0x180041c0a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041c0f  nop
0x180041c10  mov     cl, [rsp+0C8h+nSubAuthorityCount]; nSubAuthorityCount
0x180041c17  test    cl, cl
0x180041c19  jz      loc_180041CC2
0x180041c1f  call    cs:__imp_GetSidLengthRequired
0x180041c25  cmp     eax, 44h ; 'D'
0x180041c28  ja      loc_180041CC2
0x180041c2e  mov     r8b, [rsp+0C8h+nSubAuthorityCount]; nSubAuthorityCount
0x180041c36  mov     rdx, rbx; pIdentifierAuthority
0x180041c39  lea     rcx, [rsp+0C8h+Sid]; Sid
0x180041c3e  call    cs:__imp_InitializeSid
0x180041c44  test    eax, eax
0x180041c46  jnz     short loc_180041C4E
0x180041c48  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180041c4e  mov     [rsp+0C8h+var_98], 0
0x180041c57  lea     rbp, [rsp+0C8h+arg_18]
0x180041c5f  xor     esi, esi
0x180041c61  cmp     [rsp+0C8h+nSubAuthorityCount], sil
0x180041c69  jbe     short loc_180041C8F
0x180041c6b  lea     rbp, [rbp+8]
0x180041c6f  mov     ebx, [rbp-8]
0x180041c72  mov     edx, esi; nSubAuthority
0x180041c74  lea     rcx, [rsp+0C8h+Sid]; pSid
0x180041c79  call    cs:__imp_GetSidSubAuthority
0x180041c7f  mov     [rax], ebx
0x180041c81  inc     esi
0x180041c83  movzx   ecx, [rsp+0C8h+nSubAuthorityCount]
0x180041c8b  cmp     esi, ecx
0x180041c8d  jb      short loc_180041C6B
0x180041c8f  lea     rdx, [rsp+0C8h+Sid]; struct _SID *
0x180041c94  mov     rcx, rdi; this
0x180041c97  call    ?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z; ATL::CSid::Copy(_SID const &)
0x180041c9c  mov     dword ptr [rdi+50h], 8
0x180041ca3  mov     rax, rdi
0x180041ca6  mov     rcx, [rsp+0C8h+var_38]
0x180041cae  xor     rcx, rsp; StackCookie
0x180041cb1  call    __security_check_cookie
0x180041cb6  add     rsp, 0A8h
0x180041cbd  pop     rdi
0x180041cbe  pop     rsi
0x180041cbf  pop     rbp
0x180041cc0  pop     rbx
0x180041cc1  retn
0x180041cc2  mov     ecx, 80070057h; int
0x180041cc7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
