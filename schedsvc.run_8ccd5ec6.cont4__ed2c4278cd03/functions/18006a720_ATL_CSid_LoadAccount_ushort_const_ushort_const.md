# ATL::CSid::LoadAccount(ushort const *,ushort const *)

- ea: `0x18006a720`
- end: `0x18006a8ee`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z`
- size: `462`
- prototype: `bool __fastcall(ATL::CSid *__hidden this, LPCWSTR lpAccountName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053b68`

## callees

- `0x180023b80`
- `0x1800529a0`
- `0x18006a124`
- `0x18006a184`
- `0x18006a1f8`
- `0x18006a720`
- `0x18006aa44`
- `0x18006ab3c`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a7bf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006a848`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006a848`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006a7af`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006a828`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006a7af`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006a828`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CSid::LoadAccount(enum _SID_NAME_USE *this, LPCWSTR lpAccountName, const unsigned __int16 *a3)
{
  __int64 v5; // rax
  WCHAR *v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // r8
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR ReferencedDomainName[18]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Sid[80]; // [rsp+E0h] [rbp-20h] BYREF

  ATL::CSid::Clear((ATL::CSid *)this);
  if ( !lpAccountName )
    return 0;
  ReferencedDomainName[0] = 0;
  v5 = ATL::AtlMultiplyThrow<unsigned __int64>();
  ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateBytes(ReferencedDomainName, v5);
  v6 = ReferencedDomainName[0];
  cbSid[0] = 68;
  cchReferencedDomainName = 128;
  if ( !LookupAccountNameW(0, lpAccountName, Sid, cbSid, ReferencedDomainName[0], &cchReferencedDomainName, this + 20) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_17;
    if ( cbSid[0] > 0x44 )
      ATL::PrivateAtlThrow(0x80004005);
    if ( cchReferencedDomainName > 0x80 )
    {
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::Reallocate(
        ReferencedDomainName,
        2LL * cchReferencedDomainName);
      v6 = ReferencedDomainName[0];
    }
    if ( !LookupAccountNameW(0, lpAccountName, Sid, cbSid, v6, &cchReferencedDomainName, this + 20) )
      goto LABEL_17;
  }
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(cbSid[0], this + 2, Sid) )
  {
LABEL_17:
    ATL::CSid::Clear((ATL::CSid *)this);
    ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,128,ATL::CCRTAllocator>(ReferencedDomainName);
    return 0;
  }
  v7 = -1;
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
  }
  else
  {
    v8 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(this + 24, v6, v8);
  do
    ++v7;
  while ( lpAccountName[v7] );
  ATL::CSimpleStringT<unsigned short,0>::SetString(this + 22, lpAccountName, (unsigned int)v7);
  ATL::CSimpleStringT<unsigned short,0>::SetString(this + 28, 0, 0);
  ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,128,ATL::CCRTAllocator>(ReferencedDomainName);
  return 1;
}

```

## disassembly

```asm
0x18006a720  mov     [rsp-8+arg_10], rbx
0x18006a725  push    rbp
0x18006a726  push    rsi
0x18006a727  push    rdi
0x18006a728  push    r14
0x18006a72a  push    r15
0x18006a72c  lea     rbp, [rsp-40h]
0x18006a731  sub     rsp, 140h
0x18006a738  mov     rax, cs:__security_cookie
0x18006a73f  xor     rax, rsp
0x18006a742  mov     [rbp+60h+var_30], rax
0x18006a746  mov     r14, rdx
0x18006a749  mov     rbx, rcx
0x18006a74c  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18006a751  xor     r15d, r15d
0x18006a754  test    r14, r14
0x18006a757  jz      loc_18006A8C8
0x18006a75d  mov     [rsp+160h+var_110], r15
0x18006a762  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18006a767  mov     rdx, rax
0x18006a76a  lea     rcx, [rsp+160h+var_110]
0x18006a76f  call    ?AllocateBytes@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18006a774  mov     rsi, [rsp+160h+var_110]
0x18006a779  mov     [rsp+160h+cbSid], 44h ; 'D'
0x18006a781  mov     [rsp+160h+var_120], 80h
0x18006a789  lea     rdi, [rbx+50h]
0x18006a78d  mov     [rsp+160h+peUse], rdi; peUse
0x18006a792  lea     rax, [rsp+160h+var_120]
0x18006a797  mov     [rsp+160h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18006a79c  mov     [rsp+160h+ReferencedDomainName], rsi; ReferencedDomainName
0x18006a7a1  lea     r9, [rsp+160h+cbSid]; cbSid
0x18006a7a6  lea     r8, [rbp+60h+Sid]; Sid
0x18006a7aa  mov     rdx, r14; lpAccountName
0x18006a7ad  xor     ecx, ecx; lpSystemName
0x18006a7af  call    cs:__imp_LookupAccountNameW
0x18006a7b6  nop     dword ptr [rax+rax+00h]
0x18006a7bb  test    eax, eax
0x18006a7bd  jnz     short loc_18006A838
0x18006a7bf  call    cs:__imp_GetLastError
0x18006a7c6  nop     dword ptr [rax+rax+00h]
0x18006a7cb  cmp     eax, 7Ah ; 'z'
0x18006a7ce  jnz     loc_18006A8B5
0x18006a7d4  cmp     [rsp+160h+cbSid], 44h ; 'D'
0x18006a7d9  jbe     short loc_18006A7E6
0x18006a7db  mov     ecx, 80004005h; unsigned int
0x18006a7e0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18006a7e6  cmp     [rsp+160h+var_120], 80h
0x18006a7ee  jbe     short loc_18006A806
0x18006a7f0  mov     edx, [rsp+160h+var_120]
0x18006a7f4  add     rdx, rdx
0x18006a7f7  lea     rcx, [rsp+160h+var_110]
0x18006a7fc  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x18006a801  mov     rsi, [rsp+160h+var_110]
0x18006a806  mov     [rsp+160h+peUse], rdi; peUse
0x18006a80b  lea     rax, [rsp+160h+var_120]
0x18006a810  mov     [rsp+160h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18006a815  mov     [rsp+160h+ReferencedDomainName], rsi; ReferencedDomainName
0x18006a81a  lea     r9, [rsp+160h+cbSid]; cbSid
0x18006a81f  lea     r8, [rbp+60h+Sid]; Sid
0x18006a823  mov     rdx, r14; lpAccountName
0x18006a826  xor     ecx, ecx; lpSystemName
0x18006a828  call    cs:__imp_LookupAccountNameW
0x18006a82f  nop     dword ptr [rax+rax+00h]
0x18006a834  test    eax, eax
0x18006a836  jz      short loc_18006A8B5
0x18006a838  mov     byte ptr [rbx+4Ch], 1
0x18006a83c  lea     rdx, [rbx+8]; pDestinationSid
0x18006a840  lea     r8, [rbp+60h+Sid]; pSourceSid
0x18006a844  mov     ecx, [rsp+160h+cbSid]; nDestinationSidLength
0x18006a848  call    cs:__imp_CopySid
0x18006a84f  nop     dword ptr [rax+rax+00h]
0x18006a854  test    eax, eax
0x18006a856  jz      short loc_18006A8B5
0x18006a858  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006a85c  test    rsi, rsi
0x18006a85f  jnz     short loc_18006A866
0x18006a861  mov     r8d, r15d
0x18006a864  jmp     short loc_18006A873
0x18006a866  mov     r8, rdi
0x18006a869  inc     r8
0x18006a86c  cmp     [rsi+r8*2], r15w
0x18006a871  jnz     short loc_18006A869
0x18006a873  lea     rcx, [rbx+60h]
0x18006a877  mov     rdx, rsi
0x18006a87a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18006a87f  inc     rdi
0x18006a882  cmp     [r14+rdi*2], r15w
0x18006a887  jnz     short loc_18006A87F
0x18006a889  lea     rcx, [rbx+58h]
0x18006a88d  mov     r8d, edi
0x18006a890  mov     rdx, r14
0x18006a893  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18006a898  lea     rcx, [rbx+70h]
0x18006a89c  xor     r8d, r8d
0x18006a89f  xor     edx, edx
0x18006a8a1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18006a8a6  nop
0x18006a8a7  lea     rcx, [rsp+160h+var_110]
0x18006a8ac  call    ??1?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::~CTempBuffer<ushort,128,ATL::CCRTAllocator>(void)
0x18006a8b1  mov     al, 1
0x18006a8b3  jmp     short loc_18006A8CA
0x18006a8b5  mov     rcx, rbx; this
0x18006a8b8  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18006a8bd  nop
0x18006a8be  lea     rcx, [rsp+160h+var_110]
0x18006a8c3  call    ??1?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::~CTempBuffer<ushort,128,ATL::CCRTAllocator>(void)
0x18006a8c8  xor     al, al
0x18006a8ca  mov     rcx, [rbp+60h+var_30]
0x18006a8ce  xor     rcx, rsp; StackCookie
0x18006a8d1  call    __security_check_cookie
0x18006a8d6  mov     rbx, [rsp+160h+arg_10]
0x18006a8de  add     rsp, 140h
0x18006a8e5  pop     r15
0x18006a8e7  pop     r14
0x18006a8e9  pop     rdi
0x18006a8ea  pop     rsi
0x18006a8eb  pop     rbp
0x18006a8ec  retn
```
