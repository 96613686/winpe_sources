# ATL::CSid::LoadAccount(ushort const *,ushort const *)

- ea: `0x1800251e4`
- end: `0x1800253a0`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z`
- size: `444`
- prototype: `bool __fastcall(ATL::CSid *__hidden this, LPCWSTR lpAccountName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024eb0`

## callees

- `0x180024a60`
- `0x180025100`
- `0x1800251ac`
- `0x1800251e4`
- `0x18003c664`
- `0x18003cc38`
- `0x18004e614`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025283`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002530c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002530c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180025273`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800252ec`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180025273`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800252ec`

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
0x1800251e4  mov     [rsp-8+arg_10], rbx
0x1800251e9  mov     [rsp-8+arg_18], rsi
0x1800251ee  push    rbp
0x1800251ef  push    rdi
0x1800251f0  push    r14
0x1800251f2  lea     rbp, [rsp-40h]
0x1800251f7  sub     rsp, 140h
0x1800251fe  mov     rax, cs:__security_cookie
0x180025205  xor     rax, rsp
0x180025208  mov     [rbp+50h+var_20], rax
0x18002520c  mov     rdi, rdx
0x18002520f  mov     rbx, rcx
0x180025212  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x180025217  test    rdi, rdi
0x18002521a  jz      loc_180025379
0x180025220  mov     [rsp+150h+var_100], 0
0x180025229  mov     edx, 100h
0x18002522e  lea     rcx, [rsp+150h+var_100]
0x180025233  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180025238  mov     rsi, [rsp+150h+var_100]
0x18002523d  mov     [rsp+150h+cbSid], 44h ; 'D'
0x180025245  mov     [rsp+150h+var_110], 80h
0x18002524d  lea     r14, [rbx+50h]
0x180025251  mov     [rsp+150h+peUse], r14; peUse
0x180025256  lea     rax, [rsp+150h+var_110]
0x18002525b  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180025260  mov     [rsp+150h+ReferencedDomainName], rsi; ReferencedDomainName
0x180025265  lea     r9, [rsp+150h+cbSid]; cbSid
0x18002526a  lea     r8, [rbp+50h+Sid]; Sid
0x18002526e  mov     rdx, rdi; lpAccountName
0x180025271  xor     ecx, ecx; lpSystemName
0x180025273  call    cs:__imp_LookupAccountNameW
0x18002527a  nop     dword ptr [rax+rax+00h]
0x18002527f  test    eax, eax
0x180025281  jnz     short loc_1800252FC
0x180025283  call    cs:__imp_GetLastError
0x18002528a  nop     dword ptr [rax+rax+00h]
0x18002528f  cmp     eax, 7Ah ; 'z'
0x180025292  jnz     loc_18002535A
0x180025298  cmp     [rsp+150h+cbSid], 44h ; 'D'
0x18002529d  jbe     short loc_1800252AA
0x18002529f  mov     ecx, 80004005h; int
0x1800252a4  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800252aa  cmp     [rsp+150h+var_110], 80h
0x1800252b2  jbe     short loc_1800252CA
0x1800252b4  mov     edx, [rsp+150h+var_110]
0x1800252b8  add     rdx, rdx
0x1800252bb  lea     rcx, [rsp+150h+var_100]
0x1800252c0  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x1800252c5  mov     rsi, [rsp+150h+var_100]
0x1800252ca  mov     [rsp+150h+peUse], r14; peUse
0x1800252cf  lea     rax, [rsp+150h+var_110]
0x1800252d4  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800252d9  mov     [rsp+150h+ReferencedDomainName], rsi; ReferencedDomainName
0x1800252de  lea     r9, [rsp+150h+cbSid]; cbSid
0x1800252e3  lea     r8, [rbp+50h+Sid]; Sid
0x1800252e7  mov     rdx, rdi; lpAccountName
0x1800252ea  xor     ecx, ecx; lpSystemName
0x1800252ec  call    cs:__imp_LookupAccountNameW
0x1800252f3  nop     dword ptr [rax+rax+00h]
0x1800252f8  test    eax, eax
0x1800252fa  jz      short loc_18002535A
0x1800252fc  mov     byte ptr [rbx+4Ch], 1
0x180025300  lea     rdx, [rbx+8]; pDestinationSid
0x180025304  lea     r8, [rbp+50h+Sid]; pSourceSid
0x180025308  mov     ecx, [rsp+150h+cbSid]; nDestinationSidLength
0x18002530c  call    cs:__imp_CopySid
0x180025313  nop     dword ptr [rax+rax+00h]
0x180025318  test    eax, eax
0x18002531a  jz      short loc_18002535A
0x18002531c  lea     rcx, [rbx+60h]
0x180025320  mov     rdx, rsi
0x180025323  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180025328  lea     rcx, [rbx+58h]
0x18002532c  mov     rdx, rdi
0x18002532f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180025334  lea     rcx, [rbx+70h]
0x180025338  xor     edx, edx
0x18002533a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002533f  nop
0x180025340  lea     rcx, [rsp+150h+var_F8]
0x180025345  cmp     [rsp+150h+var_100], rcx
0x18002534a  jz      short loc_180025356
0x18002534c  lea     rcx, [rsp+150h+var_100]
0x180025351  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180025356  mov     al, 1
0x180025358  jmp     short loc_18002537B
0x18002535a  mov     rcx, rbx; this
0x18002535d  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x180025362  nop
0x180025363  lea     rax, [rsp+150h+var_F8]
0x180025368  cmp     [rsp+150h+var_100], rax
0x18002536d  jz      short loc_180025379
0x18002536f  lea     rcx, [rsp+150h+var_100]
0x180025374  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180025379  xor     al, al
0x18002537b  mov     rcx, [rbp+50h+var_20]
0x18002537f  xor     rcx, rsp; StackCookie
0x180025382  call    __security_check_cookie
0x180025387  lea     r11, [rsp+150h+var_10]
0x18002538f  mov     rbx, [r11+30h]
0x180025393  mov     rsi, [r11+38h]
0x180025397  mov     rsp, r11
0x18002539a  pop     r14
0x18002539c  pop     rdi
0x18002539d  pop     rbp
0x18002539e  retn
```
