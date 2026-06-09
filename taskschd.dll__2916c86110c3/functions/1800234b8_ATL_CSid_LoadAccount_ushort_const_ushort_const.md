# ATL::CSid::LoadAccount(ushort const *,ushort const *)

- ea: `0x1800234b8`
- end: `0x18002365b`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z`
- size: `419`
- prototype: `bool __fastcall(ATL::CSid *__hidden this, LPCWSTR lpAccountName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800231d0`

## callees

- `0x180022dc0`
- `0x1800233e4`
- `0x180023484`
- `0x1800234b8`
- `0x180039524`
- `0x180039aa0`
- `0x18004aa50`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023551`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800235ce`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800235ce`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180023547`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800235b4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180023547`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800235b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CSid::LoadAccount(enum _SID_NAME_USE *this, LPCWSTR lpAccountName, const unsigned __int16 *a3)
{
  WCHAR *v5; // rsi
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR ReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[136]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Sid[80]; // [rsp+E0h] [rbp-20h] BYREF

  ATL::CSid::Clear((ATL::CSid *)this);
  if ( !lpAccountName )
    return 0;
  ReferencedDomainName = 0;
  ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(&ReferencedDomainName, 256);
  v5 = ReferencedDomainName;
  cbSid[0] = 68;
  cchReferencedDomainName = 128;
  if ( !LookupAccountNameW(0, lpAccountName, Sid, cbSid, ReferencedDomainName, &cchReferencedDomainName, this + 20) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_13;
    if ( cbSid[0] > 0x44 )
      ATL::PrivateAtlThrow(-2147467259);
    if ( cchReferencedDomainName > 0x80 )
    {
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::Reallocate(
        &ReferencedDomainName,
        2LL * cchReferencedDomainName);
      v5 = ReferencedDomainName;
    }
    if ( !LookupAccountNameW(0, lpAccountName, Sid, cbSid, v5, &cchReferencedDomainName, this + 20) )
      goto LABEL_13;
  }
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(cbSid[0], this + 2, Sid) )
  {
LABEL_13:
    ATL::CSid::Clear((ATL::CSid *)this);
    if ( ReferencedDomainName != (LPWSTR)v10 )
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
    return 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(this + 24, v5);
  ATL::CSimpleStringT<unsigned short,0>::SetString(this + 22, lpAccountName);
  ATL::CSimpleStringT<unsigned short,0>::SetString(this + 28, 0);
  if ( ReferencedDomainName != (LPWSTR)v10 )
    ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
  return 1;
}

```

## disassembly

```asm
0x1800234b8  mov     [rsp-8+arg_10], rbx
0x1800234bd  mov     [rsp-8+arg_18], rsi
0x1800234c2  push    rbp
0x1800234c3  push    rdi
0x1800234c4  push    r14
0x1800234c6  lea     rbp, [rsp-40h]
0x1800234cb  sub     rsp, 140h
0x1800234d2  mov     rax, cs:__security_cookie
0x1800234d9  xor     rax, rsp
0x1800234dc  mov     [rbp+50h+var_20], rax
0x1800234e0  mov     rdi, rdx
0x1800234e3  mov     rbx, rcx
0x1800234e6  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x1800234eb  test    rdi, rdi
0x1800234ee  jz      loc_180023635
0x1800234f4  mov     [rsp+150h+var_100], 0
0x1800234fd  mov     edx, 100h
0x180023502  lea     rcx, [rsp+150h+var_100]
0x180023507  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002350c  mov     rsi, [rsp+150h+var_100]
0x180023511  mov     [rsp+150h+cbSid], 44h ; 'D'
0x180023519  mov     [rsp+150h+var_110], 80h
0x180023521  lea     r14, [rbx+50h]
0x180023525  mov     [rsp+150h+peUse], r14; peUse
0x18002352a  lea     rax, [rsp+150h+var_110]
0x18002352f  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023534  mov     [rsp+150h+ReferencedDomainName], rsi; ReferencedDomainName
0x180023539  lea     r9, [rsp+150h+cbSid]; cbSid
0x18002353e  lea     r8, [rbp+50h+Sid]; Sid
0x180023542  mov     rdx, rdi; lpAccountName
0x180023545  xor     ecx, ecx; lpSystemName
0x180023547  call    cs:__imp_LookupAccountNameW
0x18002354d  test    eax, eax
0x18002354f  jnz     short loc_1800235BE
0x180023551  call    cs:__imp_GetLastError
0x180023557  cmp     eax, 7Ah ; 'z'
0x18002355a  jnz     loc_180023616
0x180023560  cmp     [rsp+150h+cbSid], 44h ; 'D'
0x180023565  jbe     short loc_180023572
0x180023567  mov     ecx, 80004005h; int
0x18002356c  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180023572  cmp     [rsp+150h+var_110], 80h
0x18002357a  jbe     short loc_180023592
0x18002357c  mov     edx, [rsp+150h+var_110]
0x180023580  add     rdx, rdx
0x180023583  lea     rcx, [rsp+150h+var_100]
0x180023588  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x18002358d  mov     rsi, [rsp+150h+var_100]
0x180023592  mov     [rsp+150h+peUse], r14; peUse
0x180023597  lea     rax, [rsp+150h+var_110]
0x18002359c  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800235a1  mov     [rsp+150h+ReferencedDomainName], rsi; ReferencedDomainName
0x1800235a6  lea     r9, [rsp+150h+cbSid]; cbSid
0x1800235ab  lea     r8, [rbp+50h+Sid]; Sid
0x1800235af  mov     rdx, rdi; lpAccountName
0x1800235b2  xor     ecx, ecx; lpSystemName
0x1800235b4  call    cs:__imp_LookupAccountNameW
0x1800235ba  test    eax, eax
0x1800235bc  jz      short loc_180023616
0x1800235be  mov     byte ptr [rbx+4Ch], 1
0x1800235c2  lea     rdx, [rbx+8]; pDestinationSid
0x1800235c6  lea     r8, [rbp+50h+Sid]; pSourceSid
0x1800235ca  mov     ecx, [rsp+150h+cbSid]; nDestinationSidLength
0x1800235ce  call    cs:__imp_CopySid
0x1800235d4  test    eax, eax
0x1800235d6  jz      short loc_180023616
0x1800235d8  lea     rcx, [rbx+60h]
0x1800235dc  mov     rdx, rsi
0x1800235df  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800235e4  lea     rcx, [rbx+58h]
0x1800235e8  mov     rdx, rdi
0x1800235eb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800235f0  lea     rcx, [rbx+70h]
0x1800235f4  xor     edx, edx
0x1800235f6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800235fb  nop
0x1800235fc  lea     rcx, [rsp+150h+var_F8]
0x180023601  cmp     [rsp+150h+var_100], rcx
0x180023606  jz      short loc_180023612
0x180023608  lea     rcx, [rsp+150h+var_100]
0x18002360d  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180023612  mov     al, 1
0x180023614  jmp     short loc_180023637
0x180023616  mov     rcx, rbx; this
0x180023619  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18002361e  nop
0x18002361f  lea     rax, [rsp+150h+var_F8]
0x180023624  cmp     [rsp+150h+var_100], rax
0x180023629  jz      short loc_180023635
0x18002362b  lea     rcx, [rsp+150h+var_100]
0x180023630  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180023635  xor     al, al
0x180023637  mov     rcx, [rbp+50h+var_20]
0x18002363b  xor     rcx, rsp; StackCookie
0x18002363e  call    __security_check_cookie
0x180023643  lea     r11, [rsp+150h+var_10]
0x18002364b  mov     rbx, [r11+30h]
0x18002364f  mov     rsi, [r11+38h]
0x180023653  mov     rsp, r11
0x180023656  pop     r14
0x180023658  pop     rdi
0x180023659  pop     rbp
0x18002365a  retn
```
