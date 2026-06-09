# MakeWellKnownSid(ushort * const,ATL::CComBSTR &)

- ea: `0x180024ab0`
- end: `0x180024e11`
- name: `?MakeWellKnownSid@@YAXQEAGAEAVCComBSTR@ATL@@@Z`
- size: `865`
- prototype: `void __fastcall(LPCWSTR lpAccountName, struct ATL::CComBSTR *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024380`
- `0x180024930`

## callees

- `0x180024ab0`
- `0x180024e18`
- `0x180024e78`
- `0x1800250ac`
- `0x180025100`
- `0x1800251ac`
- `0x180026120`
- `0x18003c664`
- `0x18003cc38`
- `0x18004e614`
- `0x180052640`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180024d32`
- `msvcrt!_wcsnicmp` at `0x180024d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024cdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024cdb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024bfa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024bfa`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d68`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d68`
- `OLEAUT32!__imp_SysFreeString` at `0x180024d50`
- `OLEAUT32!__imp_SysFreeString` at `0x180024d50`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024c59`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024c59`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180024bd5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180024dbf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180024bd5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180024dbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MakeWellKnownSid(LPCWSTR lpAccountName, BSTR *a2)
{
  WCHAR *v4; // rdi
  int v5; // edi
  BSTR v6; // rax
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  void **v10; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pDestinationSid[68]; // [rsp+58h] [rbp-A8h] BYREF
  char v12; // [rsp+9Ch] [rbp-64h]
  enum _SID_NAME_USE peUse; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v14[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v15[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v16[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v17[16]; // [rsp+C0h] [rbp-40h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v19[136]; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t String2[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE Sid[80]; // [rsp+170h] [rbp+70h] BYREF

  wcscpy(String2, L"S-1-");
  if ( !lpAccountName || !*lpAccountName || _wcsnicmp(lpAccountName, String2, 4u) )
  {
    v10 = &ATL::CSid::`vftable';
    v12 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v14);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v15);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v17);
    StringSid = 0;
    *(_QWORD *)String2 = &StringSid;
    peUse = SidTypeInvalid;
    ATL::CSimpleStringT<unsigned short,0>::Empty(v14);
    ATL::CSimpleStringT<unsigned short,0>::Empty(v15);
    ATL::CSimpleStringT<unsigned short,0>::Empty(v16);
    ATL::CSimpleStringT<unsigned short,0>::Empty(v17);
    v12 = 0;
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
          v12 = 1;
          if ( CopySid(cbSid, pDestinationSid, Sid) )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(v15, v4);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v14, lpAccountName);
            ATL::CSimpleStringT<unsigned short,0>::Empty(v17);
            if ( ReferencedDomainName != (LPWSTR)v19 )
              ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
            v5 = 0;
            if ( (unsigned int)(peUse - 4) <= 1 && ConvertSidToStringSidW(pDestinationSid, &StringSid) )
            {
              ATL::CComBSTR::operator=(a2);
              v5 = 1;
            }
LABEL_14:
            LocalFree(StringSid);
            ATL::CSid::~CSid((ATL::CSid *)&v10);
            if ( v5 )
              return;
            goto LABEL_18;
          }
        }
      }
      peUse = SidTypeInvalid;
      ATL::CSimpleStringT<unsigned short,0>::Empty(v14);
      ATL::CSimpleStringT<unsigned short,0>::Empty(v15);
      ATL::CSimpleStringT<unsigned short,0>::Empty(v16);
      ATL::CSimpleStringT<unsigned short,0>::Empty(v17);
      v12 = 0;
      if ( ReferencedDomainName != (LPWSTR)v19 )
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
      v6 = SysAllocString(lpAccountName);
      *a2 = v6;
      if ( !v6 )
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
0x180024ab0  mov     [rsp-8+arg_10], rbx
0x180024ab5  mov     [rsp-8+arg_18], rsi
0x180024aba  push    rbp
0x180024abb  push    rdi
0x180024abc  push    r14
0x180024abe  lea     rbp, [rsp-0D0h]
0x180024ac6  sub     rsp, 1D0h
0x180024acd  mov     rax, cs:__security_cookie
0x180024ad4  xor     rax, rsp
0x180024ad7  mov     [rbp+0E0h+var_20], rax
0x180024ade  mov     r14, rdx
0x180024ae1  mov     rbx, rcx
0x180024ae4  movsd   xmm0, qword ptr cs:aS1; "S-1-"
0x180024aec  movsd   qword ptr [rbp+0E0h+String2], xmm0
0x180024af1  movzx   eax, word ptr cs:aS1+8; ""
0x180024af8  mov     [rbp+0E0h+var_78], ax
0x180024afc  test    rcx, rcx
0x180024aff  jnz     loc_180024D1E
0x180024b05  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180024b0c  mov     [rsp+1E0h+var_190], rax
0x180024b11  mov     [rbp+0E0h+var_144], 0
0x180024b15  mov     [rbp+0E0h+var_140], 7
0x180024b1c  lea     rcx, [rbp+0E0h+var_138]
0x180024b20  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180024b25  lea     rcx, [rbp+0E0h+var_130]
0x180024b29  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180024b2e  lea     rcx, [rbp+0E0h+var_128]
0x180024b32  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180024b37  lea     rcx, [rbp+0E0h+var_120]
0x180024b3b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180024b40  nop
0x180024b41  xor     esi, esi
0x180024b43  mov     [rsp+1E0h+StringSid], rsi
0x180024b48  lea     rax, [rsp+1E0h+StringSid]
0x180024b4d  mov     qword ptr [rbp+0E0h+String2], rax
0x180024b51  mov     [rbp+0E0h+var_140], 7
0x180024b58  lea     rcx, [rbp+0E0h+var_138]
0x180024b5c  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024b61  lea     rcx, [rbp+0E0h+var_130]
0x180024b65  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024b6a  lea     rcx, [rbp+0E0h+var_128]
0x180024b6e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024b73  lea     rcx, [rbp+0E0h+var_120]
0x180024b77  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024b7c  mov     [rbp+0E0h+var_144], sil
0x180024b80  test    rbx, rbx
0x180024b83  jz      loc_180024CD4
0x180024b89  mov     [rbp+0E0h+var_110], rsi
0x180024b8d  mov     edx, 100h
0x180024b92  lea     rcx, [rbp+0E0h+var_110]
0x180024b96  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180024b9b  mov     rdi, [rbp+0E0h+var_110]
0x180024b9f  mov     [rsp+1E0h+cbSid], 44h ; 'D'
0x180024ba7  mov     [rsp+1E0h+var_19C], 80h
0x180024baf  lea     rax, [rbp+0E0h+var_140]
0x180024bb3  mov     [rsp+1E0h+peUse], rax; peUse
0x180024bb8  lea     rax, [rsp+1E0h+var_19C]
0x180024bbd  mov     [rsp+1E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180024bc2  mov     [rsp+1E0h+ReferencedDomainName], rdi; ReferencedDomainName
0x180024bc7  lea     r9, [rsp+1E0h+cbSid]; cbSid
0x180024bcc  lea     r8, [rbp+0E0h+Sid]; Sid
0x180024bd0  mov     rdx, rbx; lpAccountName
0x180024bd3  xor     ecx, ecx; lpSystemName
0x180024bd5  call    cs:__imp_LookupAccountNameW
0x180024bdc  nop     dword ptr [rax+rax+00h]
0x180024be1  test    eax, eax
0x180024be3  jz      loc_180024C7D
0x180024be9  mov     [rbp+0E0h+var_144], 1
0x180024bed  lea     r8, [rbp+0E0h+Sid]; pSourceSid
0x180024bf1  lea     rdx, [rsp+1E0h+pDestinationSid]; pDestinationSid
0x180024bf6  mov     ecx, [rsp+1E0h+cbSid]; nDestinationSidLength
0x180024bfa  call    cs:__imp_CopySid
0x180024c01  nop     dword ptr [rax+rax+00h]
0x180024c06  test    eax, eax
0x180024c08  jz      loc_180024C92
0x180024c0e  mov     rdx, rdi
0x180024c11  lea     rcx, [rbp+0E0h+var_130]
0x180024c15  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180024c1a  mov     rdx, rbx
0x180024c1d  lea     rcx, [rbp+0E0h+var_138]
0x180024c21  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180024c26  lea     rcx, [rbp+0E0h+var_120]
0x180024c2a  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024c2f  nop
0x180024c30  lea     rax, [rbp+0E0h+var_108]
0x180024c34  cmp     [rbp+0E0h+var_110], rax
0x180024c38  jnz     loc_180024D8B
0x180024c3e  mov     edi, esi
0x180024c40  mov     eax, [rbp+0E0h+var_140]
0x180024c43  add     eax, 0FFFFFFFCh
0x180024c46  cmp     eax, 1
0x180024c49  ja      loc_180024CD6
0x180024c4f  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x180024c54  lea     rcx, [rsp+1E0h+pDestinationSid]; Sid
0x180024c59  call    cs:__imp_ConvertSidToStringSidW
0x180024c60  nop     dword ptr [rax+rax+00h]
0x180024c65  test    eax, eax
0x180024c67  jz      short loc_180024CD6
0x180024c69  mov     rdx, [rsp+1E0h+StringSid]
0x180024c6e  mov     rcx, r14
0x180024c71  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180024c76  mov     edi, 1
0x180024c7b  jmp     short loc_180024CD6
0x180024c7d  call    cs:__imp_GetLastError
0x180024c84  nop     dword ptr [rax+rax+00h]
0x180024c89  cmp     eax, 7Ah ; 'z'
0x180024c8c  jz      loc_180024DD8
0x180024c92  mov     [rbp+0E0h+var_140], 7
0x180024c99  lea     rcx, [rbp+0E0h+var_138]
0x180024c9d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024ca2  lea     rcx, [rbp+0E0h+var_130]
0x180024ca6  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024cab  lea     rcx, [rbp+0E0h+var_128]
0x180024caf  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024cb4  lea     rcx, [rbp+0E0h+var_120]
0x180024cb8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024cbd  mov     [rbp+0E0h+var_144], 0
0x180024cc1  lea     rax, [rbp+0E0h+var_108]
0x180024cc5  cmp     [rbp+0E0h+var_110], rax
0x180024cc9  jz      short loc_180024CD4
0x180024ccb  lea     rcx, [rbp+0E0h+var_110]
0x180024ccf  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180024cd4  mov     edi, esi
0x180024cd6  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x180024cdb  call    cs:__imp_LocalFree
0x180024ce2  nop     dword ptr [rax+rax+00h]
0x180024ce7  nop
0x180024ce8  lea     rcx, [rsp+1E0h+var_190]; this
0x180024ced  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180024cf2  test    edi, edi
0x180024cf4  jz      short loc_180024D48
0x180024cf6  mov     rcx, [rbp+0E0h+var_20]
0x180024cfd  xor     rcx, rsp; StackCookie
0x180024d00  call    __security_check_cookie
0x180024d05  lea     r11, [rsp+1E0h+var_10]
0x180024d0d  mov     rbx, [r11+30h]
0x180024d11  mov     rsi, [r11+38h]
0x180024d15  mov     rsp, r11
0x180024d18  pop     r14
0x180024d1a  pop     rdi
0x180024d1b  pop     rbp
0x180024d1c  retn
0x180024d1e  cmp     word ptr [rcx], 0
0x180024d22  jz      loc_180024B05
0x180024d28  mov     r8d, 4; MaxCount
0x180024d2e  lea     rdx, [rbp+0E0h+String2]; String2
0x180024d32  call    cs:__imp__wcsnicmp
0x180024d39  nop     dword ptr [rax+rax+00h]
0x180024d3e  test    eax, eax
0x180024d40  jnz     loc_180024B05
0x180024d46  xor     esi, esi
0x180024d48  mov     rcx, [r14]; bstrString
0x180024d4b  cmp     rbx, rcx
0x180024d4e  jz      short loc_180024CF6
0x180024d50  call    cs:__imp_SysFreeString
0x180024d57  nop     dword ptr [rax+rax+00h]
0x180024d5c  test    rbx, rbx
0x180024d5f  jz      loc_180024E09
0x180024d65  mov     rcx, rbx; psz
0x180024d68  call    cs:__imp_SysAllocString
0x180024d6f  nop     dword ptr [rax+rax+00h]
0x180024d74  mov     [r14], rax
0x180024d77  test    rax, rax
0x180024d7a  jnz     loc_180024CF6
0x180024d80  mov     ecx, 8007000Eh; int
0x180024d85  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180024d8b  lea     rcx, [rbp+0E0h+var_110]
0x180024d8f  call    ?FreeHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::FreeHeap(void)
0x180024d94  jmp     loc_180024C3E
0x180024d99  lea     rax, [rbp+0E0h+var_140]
0x180024d9d  mov     [rsp+1E0h+peUse], rax; peUse
0x180024da2  lea     rax, [rsp+1E0h+var_19C]
0x180024da7  mov     [rsp+1E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180024dac  mov     [rsp+1E0h+ReferencedDomainName], rdi; ReferencedDomainName
0x180024db1  lea     r9, [rsp+1E0h+cbSid]; cbSid
0x180024db6  lea     r8, [rbp+0E0h+Sid]; Sid
0x180024dba  mov     rdx, rbx; lpAccountName
0x180024dbd  xor     ecx, ecx; lpSystemName
0x180024dbf  call    cs:__imp_LookupAccountNameW
0x180024dc6  nop     dword ptr [rax+rax+00h]
0x180024dcb  test    eax, eax
0x180024dcd  jnz     loc_180024BE9
0x180024dd3  jmp     loc_180024C92
0x180024dd8  cmp     [rsp+1E0h+cbSid], 44h ; 'D'
0x180024ddd  jbe     short loc_180024DEA
0x180024ddf  mov     ecx, 80004005h; int
0x180024de4  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180024dea  mov     eax, [rsp+1E0h+var_19C]
0x180024dee  cmp     eax, 80h
0x180024df3  jbe     short loc_180024D99
0x180024df5  mov     edx, eax
0x180024df7  add     rdx, rdx
0x180024dfa  lea     rcx, [rbp+0E0h+var_110]
0x180024dfe  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x180024e03  mov     rdi, [rbp+0E0h+var_110]
0x180024e07  jmp     short loc_180024D99
0x180024e09  mov     [r14], rsi
0x180024e0c  jmp     loc_180024CF6
```
