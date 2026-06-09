# UpdateComSecurityDescriptors(void)

- ea: `0x18009b67c`
- end: `0x18009ba98`
- name: `?UpdateComSecurityDescriptors@@YAJXZ`
- size: `1052`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009c580`
- `0x18009c648`

## callees

- `0x18000ce5c`
- `0x18000ce7c`
- `0x1800210f8`
- `0x180025088`
- `0x180025950`
- `0x18009b67c`
- `0x1800b7ac0`
- `0x1800fee9c`
- `0x1801072f0`
- `0x1801073a8`
- `0x1801074fc`
- `0x18010776c`
- `0x180107850`
- `0x180107a60`
- `0x180107b58`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009b8d2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009b90c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009b8d2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009b90c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18009b7fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18009b7fc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009b79b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009b79b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009b734`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009b734`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009b8a0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009b8a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009b779`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009b779`
- `KERNELBASE!LocalAlloc` at `0x18009b8e4`
- `KERNELBASE!LocalAlloc` at `0x18009b8e4`

## string_xrefs

- `0x18009b6ac`: `MachineAccessRestriction`
- `0x18009b748`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009b95f`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009b979`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009b992`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009b9c2`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009b9f3`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009ba14`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009ba2b`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009ba5d`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`

## pseudocode

```c
__int64 UpdateComSecurityDescriptors(void)
{
  const WCHAR **v0; // rsi
  unsigned __int16 i; // r14
  const WCHAR *v2; // rdi
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  const char *v5; // r9
  const char *v7; // r9
  const unsigned __int16 *v8; // r8
  unsigned int NamedValueSD; // eax
  const char *v10; // r9
  unsigned int SDAbsolute; // eax
  unsigned int v12; // r8d
  int v13; // r9d
  PSECURITY_DESCRIPTOR v14; // rbx
  const char *v15; // r9
  HLOCAL v16; // rax
  void *v17; // rdi
  const unsigned __int16 *v18; // rdx
  HKEY v19; // rcx
  const char *v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int LastError; // eax
  __int64 v27; // rdx
  int *v28; // [rsp+20h] [rbp-E0h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwBufferLength; // [rsp+40h] [rbp-C0h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL v33; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+5Ch] [rbp-A4h] BYREF
  WINBOOL bDaclPresent; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v37; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+70h] [rbp-90h]
  __int16 v39; // [rsp+74h] [rbp-8Ch]
  const struct ExpectedAccess near *const *v40; // [rsp+78h] [rbp-88h]
  const WCHAR *v41; // [rsp+80h] [rbp-80h]
  int v42; // [rsp+88h] [rbp-78h]
  __int16 v43; // [rsp+8Ch] [rbp-74h]
  const struct ExpectedAccess near *const *v44; // [rsp+90h] [rbp-70h]
  char v45; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pSid[80]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v38 = 2;
  v39 = 4;
  v37 = L"MachineAccessRestriction";
  v0 = &v37;
  v43 = 4;
  v40 = &g_expectedAccessInMachineAccessRestriction;
  v42 = 1;
  v41 = L"MachineLaunchRestriction";
  v44 = &g_expectedAccessInMachineLaunchRestriction;
LABEL_2:
  if ( v0 == (const WCHAR **)&v45 )
    return 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_WORD *)v0 + 6) )
    {
      v0 += 3;
      goto LABEL_2;
    }
    v2 = v0[2];
    cbSid = 68;
    if ( !*(_QWORD *)&v2[12 * i + 4] )
    {
      if ( !CreateWellKnownSid(*(WELL_KNOWN_SID_TYPE *)&v2[12 * i], 0, pSid, &cbSid) )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x2D,
                 (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                 v5);
      goto LABEL_11;
    }
    Sid = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &Sid,
      0);
    if ( !ConvertStringSidToSidW(*(LPCWSTR *)&v2[12 * i + 4], &Sid) )
      break;
    if ( !CopySid(0x44u, pSid, Sid) )
    {
      v27 = 51;
      goto LABEL_46;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_11:
    v8 = *v0;
    Sid = 0;
    NamedValueSD = GetNamedValueSD(v4, v3, v8, &Sid, v28);
    if ( NamedValueSD )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x38,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                    (const char *)NamedValueSD,
                    (unsigned int)v28);
      goto LABEL_42;
    }
    bDaclPresent = 0;
    pDacl = 0;
    bDaclDefaulted = 0;
    if ( !GetSecurityDescriptorDacl(Sid, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3E,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                    v10);
LABEL_42:
      v23 = LastError;
      goto LABEL_43;
    }
    if ( pDacl )
    {
      pSecurityDescriptor = 0;
      SDAbsolute = MakeSDAbsolute(Sid, &pSecurityDescriptor);
      if ( SDAbsolute )
      {
        v24 = 69;
        goto LABEL_37;
      }
      SDAbsolute = RemovePrincipalFromACL(pDacl, pSid, v12);
      if ( (SDAbsolute & 0xFFFFFFFD) != 0 )
      {
        v24 = 74;
        goto LABEL_37;
      }
      SDAbsolute = UpdatePrincipalInACL(pDacl, pSid, *(_DWORD *)&v2[12 * i + 8], v13, (unsigned int)v28);
      if ( (SDAbsolute & 0xFFFFFFFD) != 0 )
      {
        v24 = 81;
        goto LABEL_37;
      }
      SDAbsolute = AddAccessAllowedACEToACL(&pDacl, *(_DWORD *)&v2[12 * i + 8], pSid);
      if ( SDAbsolute )
      {
        v24 = 85;
LABEL_37:
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v24,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                (const char *)SDAbsolute,
                (unsigned int)v28);
        goto LABEL_38;
      }
      v14 = pSecurityDescriptor;
      if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
      {
        v25 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x58,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                v15);
LABEL_38:
        v23 = v25;
        goto LABEL_39;
      }
      SDAbsolute = CanonicalizeSD(v14);
      if ( SDAbsolute )
      {
        v24 = 90;
        goto LABEL_37;
      }
      dwBufferLength = 0;
      MakeSelfRelativeSD(v14, 0, &dwBufferLength);
      v16 = LocalAlloc(0, dwBufferLength);
      v33 = v16;
      v17 = v16;
      if ( !v16 )
      {
        v23 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
          (const char *)0x8007000ELL,
          (int)v28);
        goto LABEL_30;
      }
      if ( !MakeSelfRelativeSD(v14, v16, &dwBufferLength) )
      {
        v22 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x65,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                v20);
LABEL_28:
        v23 = v22;
LABEL_30:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
LABEL_39:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pSecurityDescriptor);
LABEL_43:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Sid);
        return v23;
      }
      v21 = SetNamedValueSD(v19, v18, *v0, v17);
      if ( v21 )
      {
        v22 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x69,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
                (const char *)v21,
                (unsigned int)v28);
        goto LABEL_28;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pSecurityDescriptor);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Sid);
  }
  v27 = 50;
LABEL_46:
  v23 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\fixsecuritydescriptors.cpp",
          v7);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return v23;
}

```

## disassembly

```asm
0x18009b67c  push    rbp
0x18009b67e  push    rbx
0x18009b67f  push    rsi
0x18009b680  push    rdi
0x18009b681  push    r12
0x18009b683  push    r14
0x18009b685  lea     rbp, [rsp-8]
0x18009b68a  sub     rsp, 108h
0x18009b691  mov     rax, cs:__security_cookie
0x18009b698  xor     rax, rsp
0x18009b69b  mov     [rbp+30h+var_40], rax
0x18009b69f  mov     ecx, 4
0x18009b6a4  mov     [rsp+130h+var_C0], 2
0x18009b6ac  lea     rax, aMachineaccessr_0; "MachineAccessRestriction"
0x18009b6b3  mov     [rsp+130h+var_BC], cx
0x18009b6b8  mov     [rsp+130h+var_C8], rax
0x18009b6bd  lea     rsi, [rsp+130h+var_C8]
0x18009b6c2  lea     rax, ?g_expectedAccessInMachineAccessRestriction@@3QBUExpectedAccess@@B; ExpectedAccess const near * const g_expectedAccessInMachineAccessRestriction
0x18009b6c9  mov     [rbp+30h+var_A4], cx
0x18009b6cd  mov     [rsp+130h+var_B8], rax
0x18009b6d2  lea     r12d, [rcx-3]
0x18009b6d6  lea     rax, aMachinelaunchr; "MachineLaunchRestriction"
0x18009b6dd  mov     [rbp+30h+var_A8], r12d
0x18009b6e1  mov     [rbp+30h+var_B0], rax
0x18009b6e5  lea     rax, ?g_expectedAccessInMachineLaunchRestriction@@3QBUExpectedAccess@@B; ExpectedAccess const near * const g_expectedAccessInMachineLaunchRestriction
0x18009b6ec  mov     [rbp+30h+var_A0], rax
0x18009b6f0  lea     rax, [rbp+30h+var_98]
0x18009b6f4  cmp     rsi, rax
0x18009b6f7  jz      loc_18009BA79
0x18009b6fd  xor     r14d, r14d
0x18009b700  cmp     r14w, [rsi+0Ch]
0x18009b705  jnb     loc_18009B952
0x18009b70b  mov     rdi, [rsi+10h]
0x18009b70f  xor     edx, edx; DomainSid
0x18009b711  movzx   eax, r14w
0x18009b715  mov     [rsp+130h+cbSid], 44h ; 'D'
0x18009b71d  lea     rbx, [rax+rax*2]
0x18009b721  cmp     [rdi+rbx*8+8], rdx
0x18009b726  jnz     short loc_18009B75C
0x18009b728  mov     ecx, [rdi+rbx*8]; WellKnownSidType
0x18009b72b  lea     r9, [rsp+130h+cbSid]; cbSid
0x18009b730  lea     r8, [rbp+30h+pSid]; pSid
0x18009b734  call    cs:__imp_CreateWellKnownSid
0x18009b73b  nop     dword ptr [rax+rax+00h]
0x18009b740  test    eax, eax
0x18009b742  jnz     short loc_18009B7B9
0x18009b744  mov     rcx, [rbp+38h]; this
0x18009b748  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009b74f  lea     edx, [rax+2Dh]; void *
0x18009b752  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b757  jmp     loc_18009BA7B
0x18009b75c  lea     rcx, [rsp+130h+Sid]
0x18009b761  mov     [rsp+130h+Sid], 0
0x18009b76a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18009b76f  mov     rcx, [rdi+rbx*8+8]; StringSid
0x18009b774  lea     rdx, [rsp+130h+Sid]; Sid
0x18009b779  call    cs:__imp_ConvertStringSidToSidW
0x18009b780  nop     dword ptr [rax+rax+00h]
0x18009b785  test    eax, eax
0x18009b787  jz      loc_18009BA54
0x18009b78d  mov     r8, [rsp+130h+Sid]; pSourceSid
0x18009b792  lea     rdx, [rbp+30h+pSid]; pDestinationSid
0x18009b796  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18009b79b  call    cs:__imp_CopySid
0x18009b7a2  nop     dword ptr [rax+rax+00h]
0x18009b7a7  test    eax, eax
0x18009b7a9  jz      loc_18009BA4D
0x18009b7af  lea     rcx, [rsp+130h+Sid]
0x18009b7b4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009b7b9  mov     r8, [rsi]; unsigned __int16 *
0x18009b7bc  lea     r9, [rsp+130h+Sid]; void **
0x18009b7c1  mov     [rsp+130h+Sid], 0
0x18009b7ca  call    ?GetNamedValueSD@@YAKPEAUHKEY__@@PEBG1PEAPEAXPEAH@Z; GetNamedValueSD(HKEY__ *,ushort const *,ushort const *,void * *,int *)
0x18009b7cf  test    eax, eax
0x18009b7d1  jnz     loc_18009BA27
0x18009b7d7  mov     rcx, [rsp+130h+Sid]; pSecurityDescriptor
0x18009b7dc  lea     r9, [rsp+130h+bDaclDefaulted]; lpbDaclDefaulted
0x18009b7e1  lea     r8, [rsp+130h+pDacl]; pDacl
0x18009b7e6  mov     [rsp+130h+bDaclPresent], eax
0x18009b7ea  lea     rdx, [rsp+130h+bDaclPresent]; lpbDaclPresent
0x18009b7ef  mov     [rsp+130h+pDacl], 0
0x18009b7f8  mov     [rsp+130h+bDaclDefaulted], eax
0x18009b7fc  call    cs:__imp_GetSecurityDescriptorDacl
0x18009b803  nop     dword ptr [rax+rax+00h]
0x18009b808  test    eax, eax
0x18009b80a  jz      loc_18009BA10
0x18009b810  cmp     [rsp+130h+pDacl], 0
0x18009b816  jz      loc_18009B93F
0x18009b81c  mov     rcx, [rsp+130h+Sid]; pSelfRelativeSecurityDescriptor
0x18009b821  lea     rdx, [rsp+130h+pSecurityDescriptor]; void **
0x18009b826  mov     [rsp+130h+pSecurityDescriptor], 0
0x18009b82f  call    ?MakeSDAbsolute@@YAKPEAXPEAPEAX@Z; MakeSDAbsolute(void *,void * *)
0x18009b834  test    eax, eax
0x18009b836  jnz     loc_18009B9EA
0x18009b83c  mov     rcx, [rsp+130h+pDacl]; pAcl
0x18009b841  lea     rdx, [rbp+30h+pSid]; pSid1
0x18009b845  call    ?RemovePrincipalFromACL@@YAKPEAU_ACL@@PEAXK@Z; RemovePrincipalFromACL(_ACL *,void *,ulong)
0x18009b84a  test    eax, 0FFFFFFFDh
0x18009b84f  jnz     loc_18009B9E3
0x18009b855  mov     r8d, [rdi+rbx*8+10h]; unsigned int
0x18009b85a  lea     rdx, [rbp+30h+pSid]; pSid1
0x18009b85e  mov     rcx, [rsp+130h+pDacl]; pAcl
0x18009b863  call    ?UpdatePrincipalInACL@@YAKPEAU_ACL@@PEAXKHK@Z; UpdatePrincipalInACL(_ACL *,void *,ulong,int,ulong)
0x18009b868  test    eax, 0FFFFFFFDh
0x18009b86d  jnz     loc_18009B9DC
0x18009b873  mov     edx, [rdi+rbx*8+10h]; unsigned int
0x18009b877  lea     r8, [rbp+30h+pSid]; void *
0x18009b87b  lea     rcx, [rsp+130h+pDacl]; struct _ACL **
0x18009b880  call    ?AddAccessAllowedACEToACL@@YAKPEAPEAU_ACL@@KPEAX@Z; AddAccessAllowedACEToACL(_ACL * *,ulong,void *)
0x18009b885  test    eax, eax
0x18009b887  jnz     loc_18009B9D5
0x18009b88d  mov     rbx, [rsp+130h+pSecurityDescriptor]
0x18009b892  xor     r9d, r9d; bDaclDefaulted
0x18009b895  mov     r8, [rsp+130h+pDacl]; pDacl
0x18009b89a  mov     rcx, rbx; pSecurityDescriptor
0x18009b89d  mov     edx, r12d; bDaclPresent
0x18009b8a0  call    cs:__imp_SetSecurityDescriptorDacl
0x18009b8a7  nop     dword ptr [rax+rax+00h]
0x18009b8ac  test    eax, eax
0x18009b8ae  jz      loc_18009B9BE
0x18009b8b4  mov     rcx, rbx; void *
0x18009b8b7  call    ?CanonicalizeSD@@YAKPEAX@Z; CanonicalizeSD(void *)
0x18009b8bc  test    eax, eax
0x18009b8be  jnz     loc_18009B9B7
0x18009b8c4  lea     r8, [rsp+130h+dwBufferLength]; lpdwBufferLength
0x18009b8c9  mov     [rsp+130h+dwBufferLength], eax
0x18009b8cd  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18009b8cf  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18009b8d2  call    cs:__imp_MakeSelfRelativeSD
0x18009b8d9  nop     dword ptr [rax+rax+00h]
0x18009b8de  mov     edx, [rsp+130h+dwBufferLength]; uBytes
0x18009b8e2  xor     ecx, ecx; uFlags
0x18009b8e4  call    cs:__imp_LocalAlloc
0x18009b8eb  nop     dword ptr [rax+rax+00h]
0x18009b8f0  mov     [rsp+130h+var_E0], rax
0x18009b8f5  mov     rdi, rax
0x18009b8f8  test    rax, rax
0x18009b8fb  jz      loc_18009B98E
0x18009b901  lea     r8, [rsp+130h+dwBufferLength]; lpdwBufferLength
0x18009b906  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18009b909  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18009b90c  call    cs:__imp_MakeSelfRelativeSD
0x18009b913  nop     dword ptr [rax+rax+00h]
0x18009b918  test    eax, eax
0x18009b91a  jz      short loc_18009B975
0x18009b91c  mov     r8, [rsi]; unsigned __int16 *
0x18009b91f  mov     r9, rdi; void *
0x18009b922  call    ?SetNamedValueSD@@YAKPEAUHKEY__@@PEBG1PEAX@Z; SetNamedValueSD(HKEY__ *,ushort const *,ushort const *,void *)
0x18009b927  test    eax, eax
0x18009b929  jnz     short loc_18009B95B
0x18009b92b  lea     rcx, [rsp+130h+var_E0]
0x18009b930  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009b935  lea     rcx, [rsp+130h+pSecurityDescriptor]
0x18009b93a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009b93f  lea     rcx, [rsp+130h+Sid]
0x18009b944  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009b949  add     r14w, r12w
0x18009b94d  jmp     loc_18009B700
0x18009b952  add     rsi, 18h
0x18009b956  jmp     loc_18009B6F0
0x18009b95b  mov     rcx, [rbp+38h]; this
0x18009b95f  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009b966  mov     r9d, eax; char *
0x18009b969  mov     edx, 69h ; 'i'; void *
0x18009b96e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b973  jmp     short loc_18009B98A
0x18009b975  mov     rcx, [rbp+38h]; this
0x18009b979  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009b980  mov     edx, 65h ; 'e'; void *
0x18009b985  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b98a  mov     ebx, eax
0x18009b98c  jmp     short loc_18009B9AB
0x18009b98e  mov     rcx, [rbp+38h]; this
0x18009b992  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009b999  mov     ebx, 8007000Eh
0x18009b99e  mov     edx, 62h ; 'b'; void *
0x18009b9a3  mov     r9d, ebx; char *
0x18009b9a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b9ab  lea     rcx, [rsp+130h+var_E0]
0x18009b9b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009b9b5  jmp     short loc_18009BA04
0x18009b9b7  mov     edx, 5Ah ; 'Z'
0x18009b9bc  jmp     short loc_18009B9EF
0x18009b9be  mov     rcx, [rbp+38h]; this
0x18009b9c2  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009b9c9  mov     edx, 58h ; 'X'; void *
0x18009b9ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b9d3  jmp     short loc_18009BA02
0x18009b9d5  mov     edx, 55h ; 'U'
0x18009b9da  jmp     short loc_18009B9EF
0x18009b9dc  mov     edx, 51h ; 'Q'
0x18009b9e1  jmp     short loc_18009B9EF
0x18009b9e3  mov     edx, 4Ah ; 'J'
0x18009b9e8  jmp     short loc_18009B9EF
0x18009b9ea  mov     edx, 45h ; 'E'; void *
0x18009b9ef  mov     rcx, [rbp+38h]; this
0x18009b9f3  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009b9fa  mov     r9d, eax; char *
0x18009b9fd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009ba02  mov     ebx, eax
0x18009ba04  lea     rcx, [rsp+130h+pSecurityDescriptor]
0x18009ba09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009ba0e  jmp     short loc_18009BA41
0x18009ba10  mov     rcx, [rbp+38h]; this
0x18009ba14  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009ba1b  mov     edx, 3Eh ; '>'; void *
0x18009ba20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009ba25  jmp     short loc_18009BA3F
0x18009ba27  mov     rcx, [rbp+38h]; this
0x18009ba2b  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009ba32  mov     r9d, eax; char *
0x18009ba35  mov     edx, 38h ; '8'; void *
0x18009ba3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009ba3f  mov     ebx, eax
0x18009ba41  lea     rcx, [rsp+130h+Sid]
0x18009ba46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009ba4b  jmp     short loc_18009BA75
0x18009ba4d  mov     edx, 33h ; '3'
0x18009ba52  jmp     short loc_18009BA59
0x18009ba54  mov     edx, 32h ; '2'; void *
0x18009ba59  mov     rcx, [rbp+38h]; this
0x18009ba5d  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x18009ba64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009ba69  lea     rcx, [rsp+130h+Sid]
0x18009ba6e  mov     ebx, eax
0x18009ba70  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009ba75  mov     eax, ebx
0x18009ba77  jmp     short loc_18009BA7B
0x18009ba79  xor     eax, eax
0x18009ba7b  mov     rcx, [rbp+30h+var_40]
0x18009ba7f  xor     rcx, rsp; StackCookie
0x18009ba82  call    __security_check_cookie
0x18009ba87  add     rsp, 108h
0x18009ba8e  pop     r14
0x18009ba90  pop     r12
0x18009ba92  pop     rdi
0x18009ba93  pop     rsi
0x18009ba94  pop     rbx
0x18009ba95  pop     rbp
0x18009ba96  retn
```
