# ATL::CSid::LoadAccount(ushort const *,ushort const *)

- ea: `0x18006748c`
- end: `0x180067641`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z`
- size: `437`
- prototype: `bool __fastcall(ATL::CSid *__hidden this, LPCWSTR lpAccountName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800515c0`

## callees

- `0x180028b80`
- `0x1800504b4`
- `0x180066eec`
- `0x180066f44`
- `0x180066fb8`
- `0x18006748c`
- `0x18006778c`
- `0x180067878`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067525`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800675a2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800675a2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006751b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180067588`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006751b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180067588`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CSid::LoadAccount(enum _SID_NAME_USE *this, LPCWSTR lpAccountName, const unsigned __int16 *a3)
{
  unsigned __int64 v5; // rax
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
  ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateBytes((__int64)ReferencedDomainName, v5);
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
0x18006748c  mov     [rsp-8+arg_10], rbx
0x180067491  push    rbp
0x180067492  push    rsi
0x180067493  push    rdi
0x180067494  push    r14
0x180067496  push    r15
0x180067498  lea     rbp, [rsp-40h]
0x18006749d  sub     rsp, 140h
0x1800674a4  mov     rax, cs:__security_cookie
0x1800674ab  xor     rax, rsp
0x1800674ae  mov     [rbp+60h+var_30], rax
0x1800674b2  mov     r14, rdx
0x1800674b5  mov     rbx, rcx
0x1800674b8  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x1800674bd  xor     r15d, r15d
0x1800674c0  test    r14, r14
0x1800674c3  jz      loc_18006761C
0x1800674c9  mov     [rsp+160h+var_110], r15
0x1800674ce  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800674d3  mov     rdx, rax
0x1800674d6  lea     rcx, [rsp+160h+var_110]
0x1800674db  call    ?AllocateBytes@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x1800674e0  mov     rsi, [rsp+160h+var_110]
0x1800674e5  mov     [rsp+160h+cbSid], 44h ; 'D'
0x1800674ed  mov     [rsp+160h+var_120], 80h
0x1800674f5  lea     rdi, [rbx+50h]
0x1800674f9  mov     [rsp+160h+peUse], rdi; peUse
0x1800674fe  lea     rax, [rsp+160h+var_120]
0x180067503  mov     [rsp+160h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180067508  mov     [rsp+160h+ReferencedDomainName], rsi; ReferencedDomainName
0x18006750d  lea     r9, [rsp+160h+cbSid]; cbSid
0x180067512  lea     r8, [rbp+60h+Sid]; Sid
0x180067516  mov     rdx, r14; lpAccountName
0x180067519  xor     ecx, ecx; lpSystemName
0x18006751b  call    cs:__imp_LookupAccountNameW
0x180067521  test    eax, eax
0x180067523  jnz     short loc_180067592
0x180067525  call    cs:__imp_GetLastError
0x18006752b  cmp     eax, 7Ah ; 'z'
0x18006752e  jnz     loc_180067609
0x180067534  cmp     [rsp+160h+cbSid], 44h ; 'D'
0x180067539  jbe     short loc_180067546
0x18006753b  mov     ecx, 80004005h; unsigned int
0x180067540  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180067546  cmp     [rsp+160h+var_120], 80h
0x18006754e  jbe     short loc_180067566
0x180067550  mov     edx, [rsp+160h+var_120]
0x180067554  add     rdx, rdx
0x180067557  lea     rcx, [rsp+160h+var_110]
0x18006755c  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x180067561  mov     rsi, [rsp+160h+var_110]
0x180067566  mov     [rsp+160h+peUse], rdi; peUse
0x18006756b  lea     rax, [rsp+160h+var_120]
0x180067570  mov     [rsp+160h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180067575  mov     [rsp+160h+ReferencedDomainName], rsi; ReferencedDomainName
0x18006757a  lea     r9, [rsp+160h+cbSid]; cbSid
0x18006757f  lea     r8, [rbp+60h+Sid]; Sid
0x180067583  mov     rdx, r14; lpAccountName
0x180067586  xor     ecx, ecx; lpSystemName
0x180067588  call    cs:__imp_LookupAccountNameW
0x18006758e  test    eax, eax
0x180067590  jz      short loc_180067609
0x180067592  mov     byte ptr [rbx+4Ch], 1
0x180067596  lea     rdx, [rbx+8]; pDestinationSid
0x18006759a  lea     r8, [rbp+60h+Sid]; pSourceSid
0x18006759e  mov     ecx, [rsp+160h+cbSid]; nDestinationSidLength
0x1800675a2  call    cs:__imp_CopySid
0x1800675a8  test    eax, eax
0x1800675aa  jz      short loc_180067609
0x1800675ac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800675b0  test    rsi, rsi
0x1800675b3  jnz     short loc_1800675BA
0x1800675b5  mov     r8d, r15d
0x1800675b8  jmp     short loc_1800675C7
0x1800675ba  mov     r8, rdi
0x1800675bd  inc     r8
0x1800675c0  cmp     [rsi+r8*2], r15w
0x1800675c5  jnz     short loc_1800675BD
0x1800675c7  lea     rcx, [rbx+60h]
0x1800675cb  mov     rdx, rsi
0x1800675ce  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800675d3  inc     rdi
0x1800675d6  cmp     [r14+rdi*2], r15w
0x1800675db  jnz     short loc_1800675D3
0x1800675dd  lea     rcx, [rbx+58h]
0x1800675e1  mov     r8d, edi
0x1800675e4  mov     rdx, r14
0x1800675e7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800675ec  lea     rcx, [rbx+70h]
0x1800675f0  xor     r8d, r8d
0x1800675f3  xor     edx, edx
0x1800675f5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800675fa  nop
0x1800675fb  lea     rcx, [rsp+160h+var_110]
0x180067600  call    ??1?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::~CTempBuffer<ushort,128,ATL::CCRTAllocator>(void)
0x180067605  mov     al, 1
0x180067607  jmp     short loc_18006761E
0x180067609  mov     rcx, rbx; this
0x18006760c  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x180067611  nop
0x180067612  lea     rcx, [rsp+160h+var_110]
0x180067617  call    ??1?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::~CTempBuffer<ushort,128,ATL::CCRTAllocator>(void)
0x18006761c  xor     al, al
0x18006761e  mov     rcx, [rbp+60h+var_30]
0x180067622  xor     rcx, rsp; StackCookie
0x180067625  call    __security_check_cookie
0x18006762a  mov     rbx, [rsp+160h+arg_10]
0x180067632  add     rsp, 140h
0x180067639  pop     r15
0x18006763b  pop     r14
0x18006763d  pop     rdi
0x18006763e  pop     rsi
0x18006763f  pop     rbp
0x180067640  retn
```
