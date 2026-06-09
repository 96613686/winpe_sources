# ConvertPrinterSDToRestrictedDeviceSD(void *,void * *)

- ea: `0x180014360`
- end: `0x18001484e`
- name: `?ConvertPrinterSDToRestrictedDeviceSD@@YAJPEAXPEAPEAX@Z`
- size: `1262`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800114cc`

## callees

- `0x180001b50`
- `0x180001ba0`
- `0x180004f0c`
- `0x180005320`
- `0x180005cac`
- `0x18000bb44`
- `0x180012130`
- `0x1800131d4`
- `0x180013bd4`
- `0x180014360`
- `0x18001503c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180014674`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001469a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180014674`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001469a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180014646`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180014646`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800145eb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800145eb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800145aa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800145aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014510`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014539`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001454b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014510`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014539`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001454b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180014502`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180014502`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800144c3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800144c3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800143ef`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001444d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800143ef`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001444d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001445a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800147a9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001445a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800147a9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800146fd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800146fd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180014730`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180014730`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180014746`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180014746`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800146d6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800146d6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800147fe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001480d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800147fe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001480d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800147d3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800147d3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001478b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001478b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180014775`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180014775`

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
0x180014360  mov     [rsp-8+arg_10], rbx
0x180014365  push    rbp
0x180014366  push    rsi
0x180014367  push    rdi
0x180014368  push    r12
0x18001436a  push    r13
0x18001436c  push    r14
0x18001436e  push    r15
0x180014370  lea     rbp, [rsp-27h]
0x180014375  sub     rsp, 0F0h
0x18001437c  mov     rax, cs:__security_cookie
0x180014383  xor     rax, rsp
0x180014386  mov     [rbp+57h+var_40], rax
0x18001438a  xor     r14d, r14d
0x18001438d  mov     [rbp+57h+pOwner], rdx
0x180014391  mov     [rbp+57h+var_A0], r14
0x180014395  mov     r15, rdx
0x180014398  mov     [rbp+57h+var_98], r14
0x18001439c  mov     r12, rcx
0x18001439f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800143a3  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800143a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800143b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800143b5  mov     r13b, al
0x1800143b8  mov     [r15], r14
0x1800143bb  lea     rax, [rbp+57h+var_A0]
0x1800143bf  xor     r9d, r9d; nSubAuthority1
0x1800143c2  mov     [rsp+120h+pSid], rax; pSid
0x1800143c7  lea     r8d, [r14+12h]; nSubAuthority0
0x1800143cb  mov     [rsp+120h+nSubAuthority7], r14d; nSubAuthority7
0x1800143d0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800143d4  mov     [rsp+120h+nSubAuthority6], r14d; nSubAuthority6
0x1800143d9  mov     dl, 1; nSubAuthorityCount
0x1800143db  mov     [rsp+120h+nSubAuthority5], r14d; nSubAuthority5
0x1800143e0  mov     [rsp+120h+nSubAuthority4], r14d; nSubAuthority4
0x1800143e5  mov     [rsp+120h+nSubAuthority3], r14d; nSubAuthority3
0x1800143ea  mov     [rsp+120h+nSubAuthority2], r14d; nSubAuthority2
0x1800143ef  call    cs:__imp_AllocateAndInitializeSid
0x1800143f5  test    eax, eax
0x1800143f7  jnz     short loc_180014403
0x1800143f9  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800143fe  jmp     loc_180014827
0x180014403  test    r13b, r13b
0x180014406  jz      short loc_180014457
0x180014408  lea     rax, [rbp+57h+var_98]
0x18001440c  mov     r9d, 0CE5DBACh; nSubAuthority1
0x180014412  mov     [rsp+120h+pSid], rax; pSid
0x180014417  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001441b  mov     [rsp+120h+nSubAuthority7], r14d; nSubAuthority7
0x180014420  mov     r8d, 63h ; 'c'; nSubAuthority0
0x180014426  mov     [rsp+120h+nSubAuthority6], r14d; nSubAuthority6
0x18001442b  mov     dl, 6; nSubAuthorityCount
0x18001442d  mov     [rsp+120h+nSubAuthority5], 9C65577Dh; nSubAuthority5
0x180014435  mov     [rsp+120h+nSubAuthority4], 8F58C130h; nSubAuthority4
0x18001443d  mov     [rsp+120h+nSubAuthority3], 0E5F30EDBh; nSubAuthority3
0x180014445  mov     [rsp+120h+nSubAuthority2], 76F17EC4h; nSubAuthority2
0x18001444d  call    cs:__imp_AllocateAndInitializeSid
0x180014453  test    eax, eax
0x180014455  jz      short loc_1800143F9
0x180014457  mov     rcx, r12; pSecurityDescriptor
0x18001445a  call    cs:__imp_GetSecurityDescriptorLength
0x180014460  mov     ecx, eax; unsigned __int64
0x180014462  mov     esi, eax
0x180014464  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014469  lea     rcx, [rbp+57h+var_90]
0x18001446d  mov     [rbp+57h+var_90], r14
0x180014471  mov     rdi, rax
0x180014474  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180014479  test    rdi, rdi
0x18001447c  jz      short loc_180014498
0x18001447e  mov     r8d, esi; Size
0x180014481  mov     [rbp+57h+var_90], rdi
0x180014485  mov     rdx, r12; Src
0x180014488  mov     rcx, rdi; void *
0x18001448b  mov     ebx, r14d
0x18001448e  call    memcpy_0
0x180014493  mov     r12, rdi
0x180014496  jmp     short loc_1800144A1
0x180014498  mov     [rbp+57h+var_90], r14
0x18001449c  mov     ebx, 8007000Eh
0x1800144a1  mov     [rbp+57h+bDaclPresent], r14d
0x1800144a5  mov     rcx, r14
0x1800144a8  mov     [rbp+57h+pDacl], rcx
0x1800144ac  mov     [rbp+57h+bDaclDefaulted], r14d
0x1800144b0  test    ebx, ebx
0x1800144b2  js      short loc_1800144D8
0x1800144b4  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x1800144b8  mov     rcx, r12; pSecurityDescriptor
0x1800144bb  lea     r8, [rbp+57h+pDacl]; pDacl
0x1800144bf  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x1800144c3  call    cs:__imp_GetSecurityDescriptorDacl
0x1800144c9  test    eax, eax
0x1800144cb  jnz     short loc_1800144D4
0x1800144cd  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800144d2  mov     ebx, eax
0x1800144d4  mov     rcx, [rbp+57h+pDacl]; pAcl
0x1800144d8  mov     dword ptr [rbp+57h+pAce], r14d
0x1800144dc  mov     edi, r14d
0x1800144df  test    ebx, ebx
0x1800144e1  js      short loc_180014556
0x1800144e3  xor     eax, eax
0x1800144e5  mov     [rbp+57h+pAclInformation], rax
0x1800144e9  mov     [rbp+57h+pAclInformation+4], 8
0x1800144f1  test    rcx, rcx
0x1800144f4  jz      short loc_180014535
0x1800144f6  lea     r9d, [rax+2]; dwAclInformationClass
0x1800144fa  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1800144fe  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180014502  call    cs:__imp_GetAclInformation
0x180014508  test    eax, eax
0x18001450a  jz      short loc_180014526
0x18001450c  mov     rcx, [rbp+57h+var_A0]; pSid
0x180014510  call    cs:__imp_GetLengthSid
0x180014516  mov     edi, dword ptr [rbp+57h+pAclInformation+4]
0x180014519  add     edi, 8
0x18001451c  add     edi, eax
0x18001451e  mov     eax, dword ptr [rbp+57h+pAclInformation]
0x180014521  mov     dword ptr [rbp+57h+pAce], eax
0x180014524  jmp     short loc_180014542
0x180014526  cmp     [rbp+57h+pDacl], r14
0x18001452a  jz      short loc_180014535
0x18001452c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180014531  mov     ebx, eax
0x180014533  jmp     short loc_180014556
0x180014535  mov     rcx, [rbp+57h+var_A0]; pSid
0x180014539  call    cs:__imp_GetLengthSid
0x18001453f  lea     edi, [rax+10h]
0x180014542  test    r13b, r13b
0x180014545  jz      short loc_180014556
0x180014547  mov     rcx, [rbp+57h+var_98]; pSid
0x18001454b  call    cs:__imp_GetLengthSid
0x180014551  add     edi, 8
0x180014554  add     edi, eax
0x180014556  lea     rcx, [rbp+57h+pAclInformation]
0x18001455a  mov     [rbp+57h+pAclInformation], r14
0x18001455e  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180014563  mov     [rbp+57h+pAclInformation], r14
0x180014567  test    ebx, ebx
0x180014569  js      loc_1800146B6
0x18001456f  mov     ecx, edi; unsigned __int64
0x180014571  mov     r15d, edi
0x180014574  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014579  mov     rdx, rax
0x18001457c  lea     rcx, [rbp+57h+pAclInformation]
0x180014580  call    ??4?$TAutoPtrArray@E@NCoreLibrary@@QEAAPEAEPEAE@Z; NCoreLibrary::TAutoPtrArray<uchar>::operator=(uchar *)
0x180014585  mov     rsi, [rbp+57h+pAclInformation]
0x180014589  test    rsi, rsi
0x18001458c  jz      loc_1800146AD
0x180014592  mov     r8d, r15d; Size
0x180014595  xor     edx, edx; Val
0x180014597  mov     rcx, rsi; void *
0x18001459a  call    memset_0
0x18001459f  mov     r8d, 2; dwAclRevision
0x1800145a5  mov     edx, edi; nAclLength
0x1800145a7  mov     rcx, rsi; pAcl
0x1800145aa  call    cs:__imp_InitializeAcl
0x1800145b0  test    eax, eax
0x1800145b2  jnz     short loc_1800145BB
0x1800145b4  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800145b9  mov     ebx, eax
0x1800145bb  xor     edi, edi
0x1800145bd  mov     r14, rsi
0x1800145c0  test    ebx, ebx
0x1800145c2  js      loc_1800146B2
0x1800145c8  mov     esi, dword ptr [rbp+57h+pAce]
0x1800145cb  mov     r15d, 0F0001h
0x1800145d1  cmp     edi, esi
0x1800145d3  jnb     loc_180014663
0x1800145d9  mov     rcx, [rbp+57h+pDacl]; pAcl
0x1800145dd  lea     r8, [rbp+57h+pAce]; pAce
0x1800145e1  mov     edx, edi; dwAceIndex
0x1800145e3  mov     [rbp+57h+pAce], 0
0x1800145eb  call    cs:__imp_GetAce
0x1800145f1  test    eax, eax
0x1800145f3  jz      short loc_180014650
0x1800145f5  mov     r9, [rbp+57h+pAce]
0x1800145f9  mov     al, [r9]
0x1800145fc  test    al, al
0x1800145fe  jz      short loc_18001460C
0x180014600  cmp     al, 1
0x180014602  jz      short loc_18001460C
0x180014604  cmp     al, 5
0x180014606  jz      short loc_18001460C
0x180014608  cmp     al, 6
0x18001460a  jnz     short loc_180014631
0x18001460c  lea     rcx, [r9+4]
0x180014610  test    rcx, rcx
0x180014613  jz      short loc_180014631
0x180014615  mov     eax, [rcx]
0x180014617  test    al, 4
0x180014619  jz      short loc_180014620
0x18001461b  mov     [rcx], r15d
0x18001461e  jmp     short loc_18001462D
0x180014620  and     al, 8
0x180014622  neg     al
0x180014624  sbb     eax, eax
0x180014626  and     eax, 20001h
0x18001462b  mov     [rcx], eax
0x18001462d  mov     r9, [rbp+57h+pAce]; pAceList
0x180014631  movzx   eax, word ptr [r9+2]
0x180014636  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18001463a  mov     edx, 2; dwAceRevision
0x18001463f  mov     [rsp+120h+nSubAuthority2], eax; nAceListLength
0x180014643  mov     rcx, r14; pAcl
0x180014646  call    cs:__imp_AddAce
0x18001464c  test    eax, eax
0x18001464e  jnz     short loc_180014657
0x180014650  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180014655  mov     ebx, eax
0x180014657  inc     edi
0x180014659  test    ebx, ebx
0x18001465b  jns     loc_1800145D1
0x180014661  jmp     short loc_1800146B2
0x180014663  mov     r9, [rbp+57h+var_A0]; pSid
0x180014667  mov     edi, 2
0x18001466c  mov     edx, edi; dwAceRevision
0x18001466e  mov     r8d, r15d; AccessMask
0x180014671  mov     rcx, r14; pAcl
0x180014674  call    cs:__imp_AddAccessAllowedAce
0x18001467a  test    eax, eax
0x18001467c  jnz     short loc_180014689
0x18001467e  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180014683  mov     ebx, eax
0x180014685  test    eax, eax
0x180014687  js      short loc_1800146B2
0x180014689  test    r13b, r13b
0x18001468c  jz      short loc_1800146B2
0x18001468e  mov     r9, [rbp+57h+var_98]; pSid
0x180014692  mov     r8d, r15d; AccessMask
0x180014695  mov     edx, edi; dwAceRevision
0x180014697  mov     rcx, r14; pAcl
0x18001469a  call    cs:__imp_AddAccessAllowedAce
0x1800146a0  test    eax, eax
0x1800146a2  jnz     short loc_1800146B2
0x1800146a4  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800146a9  mov     ebx, eax
0x1800146ab  jmp     short loc_1800146B2
0x1800146ad  mov     ebx, 8007000Eh
0x1800146b2  mov     r15, [rbp+57h+pOwner]
0x1800146b6  xor     eax, eax
0x1800146b8  xorps   xmm0, xmm0
0x1800146bb  mov     [rbp+57h+var_60], rax
0x1800146bf  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1800146c3  movups  [rbp+57h+var_70], xmm0
0x1800146c7  test    ebx, ebx
0x1800146c9  js      loc_18001479C
0x1800146cf  lea     edx, [rax+1]; dwRevision
0x1800146d2  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800146d6  call    cs:__imp_InitializeSecurityDescriptor
0x1800146dc  test    eax, eax
0x1800146de  jnz     short loc_1800146EF
0x1800146e0  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800146e5  mov     ebx, eax
0x1800146e7  test    eax, eax
0x1800146e9  js      loc_18001479C
0x1800146ef  xor     r9d, r9d; bDaclDefaulted
0x1800146f2  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800146f6  mov     r8, r14; pDacl
0x1800146f9  lea     edx, [r9+1]; bDaclPresent
0x1800146fd  call    cs:__imp_SetSecurityDescriptorDacl
0x180014703  test    eax, eax
0x180014705  jnz     short loc_180014716
0x180014707  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001470c  mov     ebx, eax
0x18001470e  test    eax, eax
0x180014710  js      loc_18001479C
0x180014716  lea     r8, [rbp+57h+pAce]; lpbOwnerDefaulted
0x18001471a  mov     [rbp+57h+pOwner], 0
0x180014722  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180014726  mov     dword ptr [rbp+57h+pAce], 0
0x18001472d  mov     rcx, r12; pSecurityDescriptor
0x180014730  call    cs:__imp_GetSecurityDescriptorOwner
0x180014736  test    eax, eax
0x180014738  jz      short loc_180014750
0x18001473a  mov     r8d, dword ptr [rbp+57h+pAce]; bOwnerDefaulted
0x18001473e  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180014742  mov     rdx, [rbp+57h+pOwner]; pOwner
0x180014746  call    cs:__imp_SetSecurityDescriptorOwner
0x18001474c  test    eax, eax
0x18001474e  jnz     short loc_18001475B
0x180014750  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180014755  mov     ebx, eax
0x180014757  test    eax, eax
0x180014759  js      short loc_18001479C
0x18001475b  lea     r8, [rbp+57h+pAce]; lpbGroupDefaulted
0x18001475f  mov     [rbp+57h+pOwner], 0
0x180014767  lea     rdx, [rbp+57h+pOwner]; pGroup
0x18001476b  mov     dword ptr [rbp+57h+pAce], 0
0x180014772  mov     rcx, r12; pSecurityDescriptor
0x180014775  call    cs:__imp_GetSecurityDescriptorGroup
0x18001477b  test    eax, eax
0x18001477d  jz      short loc_180014795
0x18001477f  mov     r8d, dword ptr [rbp+57h+pAce]; bGroupDefaulted
0x180014783  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180014787  mov     rdx, [rbp+57h+pOwner]; pGroup
0x18001478b  call    cs:__imp_SetSecurityDescriptorGroup
0x180014791  test    eax, eax
0x180014793  jnz     short loc_18001479C
0x180014795  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001479a  mov     ebx, eax
  ... truncated ...
```
