# ConvertPrinterSDToRestrictedDeviceSD(void *,void * *)

- ea: `0x180015c64`
- end: `0x1800161e1`
- name: `?ConvertPrinterSDToRestrictedDeviceSD@@YAJPEAXPEAPEAX@Z`
- size: `1405`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012bd0`

## callees

- `0x180001b60`
- `0x180001bb0`
- `0x18000526c`
- `0x180005680`
- `0x18000601c`
- `0x18000c4c0`
- `0x18001389c`
- `0x180014944`
- `0x180015398`
- `0x180015c64`
- `0x180016a3c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180015fbe`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180015fea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180015fbe`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180015fea`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180015f8a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180015f8a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180015f29`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180015f29`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180015ee2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180015ee2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015e36`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015e65`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015e7d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015e36`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015e65`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015e7d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180015e22`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180015e22`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180015dd9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180015dd9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015cf3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015d57`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015cf3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015d57`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015d6a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180016123`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015d6a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180016123`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180016059`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180016059`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180016092`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180016092`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800160ae`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800160ae`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001602c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001602c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016184`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016199`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016184`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016199`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180016153`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180016153`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800160ff`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800160ff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800160e3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800160e3`

## pseudocode

```c
__int64 __fastcall ConvertPrinterSDToRestrictedDeviceSD(void *Src, void **a2)
{
  struct _ACL *v2; // r14
  void **v3; // r15
  char IsEnabled; // r13
  NCoreLibrary *v6; // rcx
  unsigned __int64 SecurityDescriptorLength; // rsi
  void *v9; // rax
  void *v10; // rdi
  int LastErrorAsFailHR; // ebx
  struct _ACL *v12; // rcx
  NCoreLibrary *v13; // rcx
  DWORD v14; // edi
  NCoreLibrary *v15; // rcx
  DWORD LengthSid; // eax
  void *v17; // rax
  struct _ACL *v18; // rsi
  NCoreLibrary *v19; // rcx
  DWORD v20; // edi
  DWORD v21; // esi
  NCoreLibrary *v22; // rcx
  unsigned __int16 *v23; // r9
  char v24; // al
  _DWORD *v25; // rcx
  NCoreLibrary *v26; // rcx
  NCoreLibrary *v27; // rcx
  NCoreLibrary *v28; // rcx
  NCoreLibrary *v29; // rcx
  NCoreLibrary *v30; // rcx
  NCoreLibrary *v31; // rcx
  void *v32; // rdi
  void *v33; // rax
  NCoreLibrary *v34; // rcx
  LPVOID pAce; // [rsp+60h] [rbp-69h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-61h] BYREF
  DWORD dwBufferLength; // [rsp+70h] [rbp-59h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-51h] BYREF
  PSID pSid; // [rsp+80h] [rbp-49h] BYREF
  PSID v40; // [rsp+88h] [rbp-41h] BYREF
  void *v41; // [rsp+90h] [rbp-39h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+98h] [rbp-31h] BYREF
  WINBOOL bDaclPresent; // [rsp+9Ch] [rbp-2Dh] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-9h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C8h] [rbp-1h] BYREF
  _BYTE pAclInformation[12]; // [rsp+D0h] [rbp+7h] BYREF

  v2 = 0;
  pOwner = a2;
  pSid = 0;
  v3 = a2;
  v40 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl);
  *v3 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || IsEnabled
    && !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x63u,
          0xCE5DBACu,
          0x76F17EC4u,
          0xE5F30EDB,
          0x8F58C130,
          0x9C65577D,
          0,
          0,
          &v40) )
  {
    return NCoreLibrary::GetLastErrorAsFailHR(v6);
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
  v9 = operator new[](SecurityDescriptorLength);
  v41 = 0;
  v10 = v9;
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v41);
  if ( v10 )
  {
    v41 = v10;
    LastErrorAsFailHR = 0;
    memcpy_0(v10, Src, (unsigned int)SecurityDescriptorLength);
    Src = v10;
  }
  else
  {
    v41 = 0;
    LastErrorAsFailHR = -2147024882;
  }
  bDaclPresent = 0;
  v12 = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  if ( LastErrorAsFailHR >= 0 )
  {
    if ( !GetSecurityDescriptorDacl(Src, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13);
    v12 = pDacl;
  }
  LODWORD(pAce) = 0;
  v14 = 0;
  if ( LastErrorAsFailHR >= 0 )
  {
    *(_DWORD *)pAclInformation = 0;
    *(_QWORD *)&pAclInformation[4] = 8;
    if ( !v12 )
      goto LABEL_18;
    if ( GetAclInformation(v12, pAclInformation, 0xCu, AclSizeInformation) )
    {
      LengthSid = GetLengthSid(pSid);
      v14 = LengthSid + *(_DWORD *)&pAclInformation[4] + 8;
      LODWORD(pAce) = *(_DWORD *)pAclInformation;
      goto LABEL_19;
    }
    if ( !pDacl )
    {
LABEL_18:
      v14 = GetLengthSid(pSid) + 16;
LABEL_19:
      if ( IsEnabled )
        v14 += GetLengthSid(v40) + 8;
      goto LABEL_21;
    }
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v15);
  }
LABEL_21:
  *(_QWORD *)pAclInformation = 0;
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(pAclInformation);
  *(_QWORD *)pAclInformation = 0;
  if ( LastErrorAsFailHR >= 0 )
  {
    v17 = operator new[](v14);
    NCoreLibrary::TAutoPtrArray<unsigned char>::operator=(pAclInformation, v17);
    v18 = *(struct _ACL **)pAclInformation;
    if ( *(_QWORD *)pAclInformation )
    {
      memset_0(*(void **)pAclInformation, 0, v14);
      if ( !InitializeAcl(v18, v14, 2u) )
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v19);
      v20 = 0;
      v2 = v18;
      if ( LastErrorAsFailHR >= 0 )
      {
        v21 = (unsigned int)pAce;
        while ( v20 < v21 )
        {
          pAce = 0;
          if ( !GetAce(pDacl, v20, &pAce) )
            goto LABEL_39;
          v23 = (unsigned __int16 *)pAce;
          v24 = *(_BYTE *)pAce;
          if ( !*(_BYTE *)pAce || v24 == 1 || v24 == 5 || v24 == 6 )
          {
            v25 = (char *)pAce + 4;
            if ( pAce != (LPVOID)-4LL )
            {
              if ( (*v25 & 4) != 0 )
                *v25 = 983041;
              else
                *v25 = (*v25 & 8) != 0 ? 0x20001 : 0;
              v23 = (unsigned __int16 *)pAce;
            }
          }
          if ( !AddAce(v2, 2u, 0xFFFFFFFF, v23, v23[1]) )
LABEL_39:
            LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v22);
          ++v20;
          if ( LastErrorAsFailHR < 0 )
            goto LABEL_48;
        }
        if ( AddAccessAllowedAce(v2, 2u, 0xF0001u, pSid)
          || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v26), LastErrorAsFailHR >= 0) )
        {
          if ( IsEnabled && !AddAccessAllowedAce(v2, 2u, 0xF0001u, v40) )
            LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v27);
        }
      }
    }
    else
    {
      LastErrorAsFailHR = -2147024882;
    }
LABEL_48:
    v3 = (void **)pOwner;
  }
  v45 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( LastErrorAsFailHR >= 0 )
  {
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v28), LastErrorAsFailHR >= 0) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v2, 0)
        || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v29), LastErrorAsFailHR >= 0) )
      {
        if ( (pOwner = 0, LODWORD(pAce) = 0, GetSecurityDescriptorOwner(Src, &pOwner, (LPBOOL)&pAce))
          && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, (BOOL)pAce)
          || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v30), LastErrorAsFailHR >= 0) )
        {
          pOwner = 0;
          LODWORD(pAce) = 0;
          if ( !GetSecurityDescriptorGroup(Src, &pOwner, (LPBOOL)&pAce)
            || !SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, (BOOL)pAce) )
          {
            LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v31);
          }
        }
      }
    }
  }
  v32 = 0;
  dwBufferLength = 0;
  if ( LastErrorAsFailHR >= 0 )
  {
    dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    v33 = (void *)DllAllocSplMem(dwBufferLength);
    v32 = v33;
    if ( v33 )
    {
      if ( MakeSelfRelativeSD(pSecurityDescriptor, v33, &dwBufferLength)
        || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v34), LastErrorAsFailHR >= 0) )
      {
        *v3 = v32;
        v32 = 0;
      }
    }
    else
    {
      LastErrorAsFailHR = -2147024882;
    }
  }
  DllFreeSplMem(v32);
  if ( pSid )
    FreeSid(pSid);
  if ( v40 )
    FreeSid(v40);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(pAclInformation);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v41);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180015c64  mov     [rsp-8+arg_10], rbx
0x180015c69  push    rbp
0x180015c6a  push    rsi
0x180015c6b  push    rdi
0x180015c6c  push    r12
0x180015c6e  push    r13
0x180015c70  push    r14
0x180015c72  push    r15
0x180015c74  lea     rbp, [rsp-27h]
0x180015c79  sub     rsp, 0F0h
0x180015c80  mov     rax, cs:__security_cookie
0x180015c87  xor     rax, rsp
0x180015c8a  mov     [rbp+57h+var_40], rax
0x180015c8e  xor     r14d, r14d
0x180015c91  mov     [rbp+57h+pOwner], rdx
0x180015c95  mov     [rbp+57h+var_A0], r14
0x180015c99  mov     r15, rdx
0x180015c9c  mov     [rbp+57h+var_98], r14
0x180015ca0  mov     r12, rcx
0x180015ca3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180015ca7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180015cad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180015cb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180015cb9  mov     r13b, al
0x180015cbc  mov     [r15], r14
0x180015cbf  lea     rax, [rbp+57h+var_A0]
0x180015cc3  xor     r9d, r9d; nSubAuthority1
0x180015cc6  mov     [rsp+120h+pSid], rax; pSid
0x180015ccb  lea     r8d, [r14+12h]; nSubAuthority0
0x180015ccf  mov     [rsp+120h+nSubAuthority7], r14d; nSubAuthority7
0x180015cd4  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180015cd8  mov     [rsp+120h+nSubAuthority6], r14d; nSubAuthority6
0x180015cdd  mov     dl, 1; nSubAuthorityCount
0x180015cdf  mov     [rsp+120h+nSubAuthority5], r14d; nSubAuthority5
0x180015ce4  mov     [rsp+120h+nSubAuthority4], r14d; nSubAuthority4
0x180015ce9  mov     [rsp+120h+nSubAuthority3], r14d; nSubAuthority3
0x180015cee  mov     [rsp+120h+nSubAuthority2], r14d; nSubAuthority2
0x180015cf3  call    cs:__imp_AllocateAndInitializeSid
0x180015cfa  nop     dword ptr [rax+rax+00h]
0x180015cff  test    eax, eax
0x180015d01  jnz     short loc_180015D0D
0x180015d03  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015d08  jmp     loc_1800161B9
0x180015d0d  test    r13b, r13b
0x180015d10  jz      short loc_180015D67
0x180015d12  lea     rax, [rbp+57h+var_98]
0x180015d16  mov     r9d, 0CE5DBACh; nSubAuthority1
0x180015d1c  mov     [rsp+120h+pSid], rax; pSid
0x180015d21  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180015d25  mov     [rsp+120h+nSubAuthority7], r14d; nSubAuthority7
0x180015d2a  mov     r8d, 63h ; 'c'; nSubAuthority0
0x180015d30  mov     [rsp+120h+nSubAuthority6], r14d; nSubAuthority6
0x180015d35  mov     dl, 6; nSubAuthorityCount
0x180015d37  mov     [rsp+120h+nSubAuthority5], 9C65577Dh; nSubAuthority5
0x180015d3f  mov     [rsp+120h+nSubAuthority4], 8F58C130h; nSubAuthority4
0x180015d47  mov     [rsp+120h+nSubAuthority3], 0E5F30EDBh; nSubAuthority3
0x180015d4f  mov     [rsp+120h+nSubAuthority2], 76F17EC4h; nSubAuthority2
0x180015d57  call    cs:__imp_AllocateAndInitializeSid
0x180015d5e  nop     dword ptr [rax+rax+00h]
0x180015d63  test    eax, eax
0x180015d65  jz      short loc_180015D03
0x180015d67  mov     rcx, r12; pSecurityDescriptor
0x180015d6a  call    cs:__imp_GetSecurityDescriptorLength
0x180015d71  nop     dword ptr [rax+rax+00h]
0x180015d76  mov     ecx, eax; unsigned __int64
0x180015d78  mov     esi, eax
0x180015d7a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015d7f  lea     rcx, [rbp+57h+var_90]
0x180015d83  mov     [rbp+57h+var_90], r14
0x180015d87  mov     rdi, rax
0x180015d8a  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180015d8f  test    rdi, rdi
0x180015d92  jz      short loc_180015DAE
0x180015d94  mov     r8d, esi; Size
0x180015d97  mov     [rbp+57h+var_90], rdi
0x180015d9b  mov     rdx, r12; Src
0x180015d9e  mov     rcx, rdi; void *
0x180015da1  mov     ebx, r14d
0x180015da4  call    memcpy_0
0x180015da9  mov     r12, rdi
0x180015dac  jmp     short loc_180015DB7
0x180015dae  mov     [rbp+57h+var_90], r14
0x180015db2  mov     ebx, 8007000Eh
0x180015db7  mov     [rbp+57h+bDaclPresent], r14d
0x180015dbb  mov     rcx, r14
0x180015dbe  mov     [rbp+57h+pDacl], rcx
0x180015dc2  mov     [rbp+57h+bDaclDefaulted], r14d
0x180015dc6  test    ebx, ebx
0x180015dc8  js      short loc_180015DF4
0x180015dca  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180015dce  mov     rcx, r12; pSecurityDescriptor
0x180015dd1  lea     r8, [rbp+57h+pDacl]; pDacl
0x180015dd5  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180015dd9  call    cs:__imp_GetSecurityDescriptorDacl
0x180015de0  nop     dword ptr [rax+rax+00h]
0x180015de5  test    eax, eax
0x180015de7  jnz     short loc_180015DF0
0x180015de9  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015dee  mov     ebx, eax
0x180015df0  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180015df4  mov     dword ptr [rbp+57h+pAce], r14d
0x180015df8  mov     edi, r14d
0x180015dfb  test    ebx, ebx
0x180015dfd  js      loc_180015E8E
0x180015e03  xor     eax, eax
0x180015e05  mov     [rbp+57h+pAclInformation], rax
0x180015e09  mov     [rbp+57h+pAclInformation+4], 8
0x180015e11  test    rcx, rcx
0x180015e14  jz      short loc_180015E61
0x180015e16  lea     r9d, [rax+2]; dwAclInformationClass
0x180015e1a  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180015e1e  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180015e22  call    cs:__imp_GetAclInformation
0x180015e29  nop     dword ptr [rax+rax+00h]
0x180015e2e  test    eax, eax
0x180015e30  jz      short loc_180015E52
0x180015e32  mov     rcx, [rbp+57h+var_A0]; pSid
0x180015e36  call    cs:__imp_GetLengthSid
0x180015e3d  nop     dword ptr [rax+rax+00h]
0x180015e42  mov     edi, dword ptr [rbp+57h+pAclInformation+4]
0x180015e45  add     edi, 8
0x180015e48  add     edi, eax
0x180015e4a  mov     eax, dword ptr [rbp+57h+pAclInformation]
0x180015e4d  mov     dword ptr [rbp+57h+pAce], eax
0x180015e50  jmp     short loc_180015E74
0x180015e52  cmp     [rbp+57h+pDacl], r14
0x180015e56  jz      short loc_180015E61
0x180015e58  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015e5d  mov     ebx, eax
0x180015e5f  jmp     short loc_180015E8E
0x180015e61  mov     rcx, [rbp+57h+var_A0]; pSid
0x180015e65  call    cs:__imp_GetLengthSid
0x180015e6c  nop     dword ptr [rax+rax+00h]
0x180015e71  lea     edi, [rax+10h]
0x180015e74  test    r13b, r13b
0x180015e77  jz      short loc_180015E8E
0x180015e79  mov     rcx, [rbp+57h+var_98]; pSid
0x180015e7d  call    cs:__imp_GetLengthSid
0x180015e84  nop     dword ptr [rax+rax+00h]
0x180015e89  add     edi, 8
0x180015e8c  add     edi, eax
0x180015e8e  lea     rcx, [rbp+57h+pAclInformation]
0x180015e92  mov     [rbp+57h+pAclInformation], r14
0x180015e96  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180015e9b  mov     [rbp+57h+pAclInformation], r14
0x180015e9f  test    ebx, ebx
0x180015ea1  js      loc_18001600C
0x180015ea7  mov     ecx, edi; unsigned __int64
0x180015ea9  mov     r15d, edi
0x180015eac  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015eb1  mov     rdx, rax
0x180015eb4  lea     rcx, [rbp+57h+pAclInformation]
0x180015eb8  call    ??4?$TAutoPtrArray@E@NCoreLibrary@@QEAAPEAEPEAE@Z; NCoreLibrary::TAutoPtrArray<uchar>::operator=(uchar *)
0x180015ebd  mov     rsi, [rbp+57h+pAclInformation]
0x180015ec1  test    rsi, rsi
0x180015ec4  jz      loc_180016003
0x180015eca  mov     r8d, r15d; Size
0x180015ecd  xor     edx, edx; Val
0x180015ecf  mov     rcx, rsi; void *
0x180015ed2  call    memset_0
0x180015ed7  mov     r8d, 2; dwAclRevision
0x180015edd  mov     edx, edi; nAclLength
0x180015edf  mov     rcx, rsi; pAcl
0x180015ee2  call    cs:__imp_InitializeAcl
0x180015ee9  nop     dword ptr [rax+rax+00h]
0x180015eee  test    eax, eax
0x180015ef0  jnz     short loc_180015EF9
0x180015ef2  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015ef7  mov     ebx, eax
0x180015ef9  xor     edi, edi
0x180015efb  mov     r14, rsi
0x180015efe  test    ebx, ebx
0x180015f00  js      loc_180016008
0x180015f06  mov     esi, dword ptr [rbp+57h+pAce]
0x180015f09  mov     r15d, 0F0001h
0x180015f0f  cmp     edi, esi
0x180015f11  jnb     loc_180015FAD
0x180015f17  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180015f1b  lea     r8, [rbp+57h+pAce]; pAce
0x180015f1f  mov     edx, edi; dwAceIndex
0x180015f21  mov     [rbp+57h+pAce], 0
0x180015f29  call    cs:__imp_GetAce
0x180015f30  nop     dword ptr [rax+rax+00h]
0x180015f35  test    eax, eax
0x180015f37  jz      short loc_180015F9A
0x180015f39  mov     r9, [rbp+57h+pAce]
0x180015f3d  mov     al, [r9]
0x180015f40  test    al, al
0x180015f42  jz      short loc_180015F50
0x180015f44  cmp     al, 1
0x180015f46  jz      short loc_180015F50
0x180015f48  cmp     al, 5
0x180015f4a  jz      short loc_180015F50
0x180015f4c  cmp     al, 6
0x180015f4e  jnz     short loc_180015F75
0x180015f50  lea     rcx, [r9+4]
0x180015f54  test    rcx, rcx
0x180015f57  jz      short loc_180015F75
0x180015f59  mov     eax, [rcx]
0x180015f5b  test    al, 4
0x180015f5d  jz      short loc_180015F64
0x180015f5f  mov     [rcx], r15d
0x180015f62  jmp     short loc_180015F71
0x180015f64  and     al, 8
0x180015f66  neg     al
0x180015f68  sbb     eax, eax
0x180015f6a  and     eax, 20001h
0x180015f6f  mov     [rcx], eax
0x180015f71  mov     r9, [rbp+57h+pAce]; pAceList
0x180015f75  movzx   eax, word ptr [r9+2]
0x180015f7a  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180015f7e  mov     edx, 2; dwAceRevision
0x180015f83  mov     [rsp+120h+nSubAuthority2], eax; nAceListLength
0x180015f87  mov     rcx, r14; pAcl
0x180015f8a  call    cs:__imp_AddAce
0x180015f91  nop     dword ptr [rax+rax+00h]
0x180015f96  test    eax, eax
0x180015f98  jnz     short loc_180015FA1
0x180015f9a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015f9f  mov     ebx, eax
0x180015fa1  inc     edi
0x180015fa3  test    ebx, ebx
0x180015fa5  jns     loc_180015F0F
0x180015fab  jmp     short loc_180016008
0x180015fad  mov     r9, [rbp+57h+var_A0]; pSid
0x180015fb1  mov     edi, 2
0x180015fb6  mov     edx, edi; dwAceRevision
0x180015fb8  mov     r8d, r15d; AccessMask
0x180015fbb  mov     rcx, r14; pAcl
0x180015fbe  call    cs:__imp_AddAccessAllowedAce
0x180015fc5  nop     dword ptr [rax+rax+00h]
0x180015fca  test    eax, eax
0x180015fcc  jnz     short loc_180015FD9
0x180015fce  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015fd3  mov     ebx, eax
0x180015fd5  test    eax, eax
0x180015fd7  js      short loc_180016008
0x180015fd9  test    r13b, r13b
0x180015fdc  jz      short loc_180016008
0x180015fde  mov     r9, [rbp+57h+var_98]; pSid
0x180015fe2  mov     r8d, r15d; AccessMask
0x180015fe5  mov     edx, edi; dwAceRevision
0x180015fe7  mov     rcx, r14; pAcl
0x180015fea  call    cs:__imp_AddAccessAllowedAce
0x180015ff1  nop     dword ptr [rax+rax+00h]
0x180015ff6  test    eax, eax
0x180015ff8  jnz     short loc_180016008
0x180015ffa  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180015fff  mov     ebx, eax
0x180016001  jmp     short loc_180016008
0x180016003  mov     ebx, 8007000Eh
0x180016008  mov     r15, [rbp+57h+pOwner]
0x18001600c  xor     eax, eax
0x18001600e  xorps   xmm0, xmm0
0x180016011  mov     [rbp+57h+var_60], rax
0x180016015  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180016019  movups  [rbp+57h+var_70], xmm0
0x18001601d  test    ebx, ebx
0x18001601f  js      loc_180016116
0x180016025  lea     edx, [rax+1]; dwRevision
0x180016028  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18001602c  call    cs:__imp_InitializeSecurityDescriptor
0x180016033  nop     dword ptr [rax+rax+00h]
0x180016038  test    eax, eax
0x18001603a  jnz     short loc_18001604B
0x18001603c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180016041  mov     ebx, eax
0x180016043  test    eax, eax
0x180016045  js      loc_180016116
0x18001604b  xor     r9d, r9d; bDaclDefaulted
0x18001604e  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180016052  mov     r8, r14; pDacl
0x180016055  lea     edx, [r9+1]; bDaclPresent
0x180016059  call    cs:__imp_SetSecurityDescriptorDacl
0x180016060  nop     dword ptr [rax+rax+00h]
0x180016065  test    eax, eax
0x180016067  jnz     short loc_180016078
0x180016069  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001606e  mov     ebx, eax
0x180016070  test    eax, eax
0x180016072  js      loc_180016116
0x180016078  lea     r8, [rbp+57h+pAce]; lpbOwnerDefaulted
0x18001607c  mov     [rbp+57h+pOwner], 0
0x180016084  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180016088  mov     dword ptr [rbp+57h+pAce], 0
0x18001608f  mov     rcx, r12; pSecurityDescriptor
0x180016092  call    cs:__imp_GetSecurityDescriptorOwner
0x180016099  nop     dword ptr [rax+rax+00h]
0x18001609e  test    eax, eax
0x1800160a0  jz      short loc_1800160BE
0x1800160a2  mov     r8d, dword ptr [rbp+57h+pAce]; bOwnerDefaulted
0x1800160a6  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800160aa  mov     rdx, [rbp+57h+pOwner]; pOwner
0x1800160ae  call    cs:__imp_SetSecurityDescriptorOwner
0x1800160b5  nop     dword ptr [rax+rax+00h]
0x1800160ba  test    eax, eax
0x1800160bc  jnz     short loc_1800160C9
0x1800160be  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800160c3  mov     ebx, eax
0x1800160c5  test    eax, eax
  ... truncated ...
```
