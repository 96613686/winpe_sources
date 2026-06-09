# MakeWellKnownSid(ushort * const,ATL::CComBSTR &)

- ea: `0x180022e10`
- end: `0x18002312e`
- name: `?MakeWellKnownSid@@YAXQEAGAEAVCComBSTR@ATL@@@Z`
- size: `798`
- prototype: `void __fastcall(LPCWSTR lpAccountName, struct ATL::CComBSTR *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022750`
- `0x180022ca0`

## callees

- `0x180022e10`
- `0x180023134`
- `0x180023194`
- `0x180023390`
- `0x1800233e4`
- `0x180023484`
- `0x180024460`
- `0x180039524`
- `0x180039aa0`
- `0x18004aa50`
- `0x18004e950`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002306b`
- `msvcrt!_wcsnicmp` at `0x18002306b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002301b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002301b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022f54`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022f54`
- `OLEAUT32!__imp_SysAllocString` at `0x180023095`
- `OLEAUT32!__imp_SysAllocString` at `0x180023095`
- `OLEAUT32!__imp_SysFreeString` at `0x180023083`
- `OLEAUT32!__imp_SysFreeString` at `0x180023083`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022fa5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022fa5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180022f35`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800230e2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180022f35`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800230e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MakeWellKnownSid(LPCWSTR lpAccountName, BSTR *a2)
{
  WCHAR *v4; // rdi
  int v5; // edi
  __int64 v6; // r8
  BSTR v7; // rax
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  void **v11; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pDestinationSid[68]; // [rsp+58h] [rbp-A8h] BYREF
  char v13; // [rsp+9Ch] [rbp-64h]
  enum _SID_NAME_USE peUse; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v15[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v16[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v17[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v18[16]; // [rsp+C0h] [rbp-40h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v20[136]; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t String2[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE Sid[80]; // [rsp+170h] [rbp+70h] BYREF

  wcscpy(String2, L"S-1-");
  if ( !lpAccountName || !*lpAccountName || _wcsnicmp(lpAccountName, String2, 4u) )
  {
    v11 = &ATL::CSid::`vftable';
    v13 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v15);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v17);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v18);
    StringSid = 0;
    *(_QWORD *)String2 = &StringSid;
    peUse = SidTypeInvalid;
    ATL::CSimpleStringT<unsigned short,0>::Empty(v15);
    ATL::CSimpleStringT<unsigned short,0>::Empty(v16);
    ATL::CSimpleStringT<unsigned short,0>::Empty(v17);
    ATL::CSimpleStringT<unsigned short,0>::Empty(v18);
    v13 = 0;
    if ( lpAccountName )
    {
      ReferencedDomainName = 0;
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(&ReferencedDomainName, 256);
      v4 = ReferencedDomainName;
      cbSid = 68;
      cchReferencedDomainName = 128;
      if ( LookupAccountNameW(0, lpAccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        goto LABEL_31;
      if ( GetLastError() == 122 )
      {
        if ( cbSid > 0x44 )
          ATL::PrivateAtlThrow(-2147467259);
        if ( cchReferencedDomainName > 0x80 )
        {
          ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::Reallocate(
            &ReferencedDomainName,
            2LL * cchReferencedDomainName);
          v4 = ReferencedDomainName;
        }
        if ( LookupAccountNameW(0, lpAccountName, Sid, &cbSid, v4, &cchReferencedDomainName, &peUse) )
        {
LABEL_31:
          v13 = 1;
          if ( CopySid(cbSid, pDestinationSid, Sid) )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(v16, v4);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v15, lpAccountName);
            ATL::CSimpleStringT<unsigned short,0>::Empty(v18);
            if ( ReferencedDomainName != (LPWSTR)v20 )
              ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
            v5 = 0;
            if ( (unsigned int)(peUse - 4) <= 1 && ConvertSidToStringSidW(pDestinationSid, &StringSid) )
            {
              ATL::CComBSTR::operator=(a2, StringSid, v6);
              v5 = 1;
            }
LABEL_14:
            LocalFree(StringSid);
            ATL::CSid::~CSid((ATL::CSid *)&v11);
            if ( v5 )
              return;
            goto LABEL_18;
          }
        }
      }
      peUse = SidTypeInvalid;
      ATL::CSimpleStringT<unsigned short,0>::Empty(v15);
      ATL::CSimpleStringT<unsigned short,0>::Empty(v16);
      ATL::CSimpleStringT<unsigned short,0>::Empty(v17);
      ATL::CSimpleStringT<unsigned short,0>::Empty(v18);
      v13 = 0;
      if ( ReferencedDomainName != (LPWSTR)v20 )
        ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
    }
    v5 = 0;
    goto LABEL_14;
  }
LABEL_18:
  if ( lpAccountName != *a2 )
  {
    SysFreeString(*a2);
    if ( lpAccountName )
    {
      v7 = SysAllocString(lpAccountName);
      *a2 = v7;
      if ( !v7 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      *a2 = 0;
    }
  }
}

```

## disassembly

```asm
0x180022e10  mov     [rsp-8+arg_10], rbx
0x180022e15  mov     [rsp-8+arg_18], rsi
0x180022e1a  push    rbp
0x180022e1b  push    rdi
0x180022e1c  push    r14
0x180022e1e  lea     rbp, [rsp-0D0h]
0x180022e26  sub     rsp, 1D0h
0x180022e2d  mov     rax, cs:__security_cookie
0x180022e34  xor     rax, rsp
0x180022e37  mov     [rbp+0E0h+var_20], rax
0x180022e3e  mov     r14, rdx
0x180022e41  mov     rbx, rcx
0x180022e44  movsd   xmm0, qword ptr cs:aS1; "S-1-"
0x180022e4c  movsd   qword ptr [rbp+0E0h+String2], xmm0
0x180022e51  movzx   eax, word ptr cs:aS1+8; ""
0x180022e58  mov     [rbp+0E0h+var_78], ax
0x180022e5c  test    rcx, rcx
0x180022e5f  jnz     loc_180023057
0x180022e65  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180022e6c  mov     [rsp+1E0h+var_190], rax
0x180022e71  mov     [rbp+0E0h+var_144], 0
0x180022e75  mov     [rbp+0E0h+var_140], 7
0x180022e7c  lea     rcx, [rbp+0E0h+var_138]
0x180022e80  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022e85  lea     rcx, [rbp+0E0h+var_130]
0x180022e89  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022e8e  lea     rcx, [rbp+0E0h+var_128]
0x180022e92  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022e97  lea     rcx, [rbp+0E0h+var_120]
0x180022e9b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022ea0  nop
0x180022ea1  xor     esi, esi
0x180022ea3  mov     [rsp+1E0h+StringSid], rsi
0x180022ea8  lea     rax, [rsp+1E0h+StringSid]
0x180022ead  mov     qword ptr [rbp+0E0h+String2], rax
0x180022eb1  mov     [rbp+0E0h+var_140], 7
0x180022eb8  lea     rcx, [rbp+0E0h+var_138]
0x180022ebc  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022ec1  lea     rcx, [rbp+0E0h+var_130]
0x180022ec5  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022eca  lea     rcx, [rbp+0E0h+var_128]
0x180022ece  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022ed3  lea     rcx, [rbp+0E0h+var_120]
0x180022ed7  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022edc  mov     [rbp+0E0h+var_144], sil
0x180022ee0  test    rbx, rbx
0x180022ee3  jz      loc_180023014
0x180022ee9  mov     [rbp+0E0h+var_110], rsi
0x180022eed  mov     edx, 100h
0x180022ef2  lea     rcx, [rbp+0E0h+var_110]
0x180022ef6  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180022efb  mov     rdi, [rbp+0E0h+var_110]
0x180022eff  mov     [rsp+1E0h+cbSid], 44h ; 'D'
0x180022f07  mov     [rsp+1E0h+var_19C], 80h
0x180022f0f  lea     rax, [rbp+0E0h+var_140]
0x180022f13  mov     [rsp+1E0h+peUse], rax; peUse
0x180022f18  lea     rax, [rsp+1E0h+var_19C]
0x180022f1d  mov     [rsp+1E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180022f22  mov     [rsp+1E0h+ReferencedDomainName], rdi; ReferencedDomainName
0x180022f27  lea     r9, [rsp+1E0h+cbSid]; cbSid
0x180022f2c  lea     r8, [rbp+0E0h+Sid]; Sid
0x180022f30  mov     rdx, rbx; lpAccountName
0x180022f33  xor     ecx, ecx; lpSystemName
0x180022f35  call    cs:__imp_LookupAccountNameW
0x180022f3b  test    eax, eax
0x180022f3d  jz      loc_180022FC3
0x180022f43  mov     [rbp+0E0h+var_144], 1
0x180022f47  lea     r8, [rbp+0E0h+Sid]; pSourceSid
0x180022f4b  lea     rdx, [rsp+1E0h+pDestinationSid]; pDestinationSid
0x180022f50  mov     ecx, [rsp+1E0h+cbSid]; nDestinationSidLength
0x180022f54  call    cs:__imp_CopySid
0x180022f5a  test    eax, eax
0x180022f5c  jz      short loc_180022FD2
0x180022f5e  mov     rdx, rdi
0x180022f61  lea     rcx, [rbp+0E0h+var_130]
0x180022f65  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180022f6a  mov     rdx, rbx
0x180022f6d  lea     rcx, [rbp+0E0h+var_138]
0x180022f71  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180022f76  lea     rcx, [rbp+0E0h+var_120]
0x180022f7a  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022f7f  nop
0x180022f80  lea     rax, [rbp+0E0h+var_108]
0x180022f84  cmp     [rbp+0E0h+var_110], rax
0x180022f88  jnz     loc_1800230AE
0x180022f8e  mov     edi, esi
0x180022f90  mov     eax, [rbp+0E0h+var_140]
0x180022f93  add     eax, 0FFFFFFFCh
0x180022f96  cmp     eax, 1
0x180022f99  ja      short loc_180023016
0x180022f9b  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x180022fa0  lea     rcx, [rsp+1E0h+pDestinationSid]; Sid
0x180022fa5  call    cs:__imp_ConvertSidToStringSidW
0x180022fab  test    eax, eax
0x180022fad  jz      short loc_180023016
0x180022faf  mov     rdx, [rsp+1E0h+StringSid]
0x180022fb4  mov     rcx, r14
0x180022fb7  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180022fbc  mov     edi, 1
0x180022fc1  jmp     short loc_180023016
0x180022fc3  call    cs:__imp_GetLastError
0x180022fc9  cmp     eax, 7Ah ; 'z'
0x180022fcc  jz      loc_1800230F5
0x180022fd2  mov     [rbp+0E0h+var_140], 7
0x180022fd9  lea     rcx, [rbp+0E0h+var_138]
0x180022fdd  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022fe2  lea     rcx, [rbp+0E0h+var_130]
0x180022fe6  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022feb  lea     rcx, [rbp+0E0h+var_128]
0x180022fef  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022ff4  lea     rcx, [rbp+0E0h+var_120]
0x180022ff8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022ffd  mov     [rbp+0E0h+var_144], 0
0x180023001  lea     rax, [rbp+0E0h+var_108]
0x180023005  cmp     [rbp+0E0h+var_110], rax
0x180023009  jz      short loc_180023014
0x18002300b  lea     rcx, [rbp+0E0h+var_110]
0x18002300f  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180023014  mov     edi, esi
0x180023016  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x18002301b  call    cs:__imp_LocalFree
0x180023021  nop
0x180023022  lea     rcx, [rsp+1E0h+var_190]; this
0x180023027  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002302c  test    edi, edi
0x18002302e  jz      short loc_18002307B
0x180023030  mov     rcx, [rbp+0E0h+var_20]
0x180023037  xor     rcx, rsp; StackCookie
0x18002303a  call    __security_check_cookie
0x18002303f  lea     r11, [rsp+1E0h+var_10]
0x180023047  mov     rbx, [r11+30h]
0x18002304b  mov     rsi, [r11+38h]
0x18002304f  mov     rsp, r11
0x180023052  pop     r14
0x180023054  pop     rdi
0x180023055  pop     rbp
0x180023056  retn
0x180023057  cmp     word ptr [rcx], 0
0x18002305b  jz      loc_180022E65
0x180023061  mov     r8d, 4; MaxCount
0x180023067  lea     rdx, [rbp+0E0h+String2]; String2
0x18002306b  call    cs:__imp__wcsnicmp
0x180023071  test    eax, eax
0x180023073  jnz     loc_180022E65
0x180023079  xor     esi, esi
0x18002307b  mov     rcx, [r14]; bstrString
0x18002307e  cmp     rbx, rcx
0x180023081  jz      short loc_180023030
0x180023083  call    cs:__imp_SysFreeString
0x180023089  test    rbx, rbx
0x18002308c  jz      loc_180023126
0x180023092  mov     rcx, rbx; psz
0x180023095  call    cs:__imp_SysAllocString
0x18002309b  mov     [r14], rax
0x18002309e  test    rax, rax
0x1800230a1  jnz     short loc_180023030
0x1800230a3  mov     ecx, 8007000Eh; int
0x1800230a8  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800230ae  lea     rcx, [rbp+0E0h+var_110]
0x1800230b2  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x1800230b7  jmp     loc_180022F8E
0x1800230bc  lea     rax, [rbp+0E0h+var_140]
0x1800230c0  mov     [rsp+1E0h+peUse], rax; peUse
0x1800230c5  lea     rax, [rsp+1E0h+var_19C]
0x1800230ca  mov     [rsp+1E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800230cf  mov     [rsp+1E0h+ReferencedDomainName], rdi; ReferencedDomainName
0x1800230d4  lea     r9, [rsp+1E0h+cbSid]; cbSid
0x1800230d9  lea     r8, [rbp+0E0h+Sid]; Sid
0x1800230dd  mov     rdx, rbx; lpAccountName
0x1800230e0  xor     ecx, ecx; lpSystemName
0x1800230e2  call    cs:__imp_LookupAccountNameW
0x1800230e8  test    eax, eax
0x1800230ea  jnz     loc_180022F43
0x1800230f0  jmp     loc_180022FD2
0x1800230f5  cmp     [rsp+1E0h+cbSid], 44h ; 'D'
0x1800230fa  jbe     short loc_180023107
0x1800230fc  mov     ecx, 80004005h; int
0x180023101  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180023107  mov     eax, [rsp+1E0h+var_19C]
0x18002310b  cmp     eax, 80h
0x180023110  jbe     short loc_1800230BC
0x180023112  mov     edx, eax
0x180023114  add     rdx, rdx
0x180023117  lea     rcx, [rbp+0E0h+var_110]
0x18002311b  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x180023120  mov     rdi, [rbp+0E0h+var_110]
0x180023124  jmp     short loc_1800230BC
0x180023126  mov     [r14], rsi
0x180023129  jmp     loc_180023030
```
