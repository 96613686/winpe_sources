# UpdateComSecurityDescriptors(void)

- ea: `0x18009617c`
- end: `0x180096567`
- name: `?UpdateComSecurityDescriptors@@YAJXZ`
- size: `1003`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180096ff8`
- `0x1800970c0`

## callees

- `0x18001ec28`
- `0x18001f828`
- `0x18002ba28`
- `0x18002f058`
- `0x18002f8cc`
- `0x18009617c`
- `0x1800b27e0`
- `0x1800f6eac`
- `0x1800fead0`
- `0x1800feb7c`
- `0x1800feca8`
- `0x1800feed0`
- `0x1800fef9c`
- `0x1800ff16c`
- `0x1800ff244`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800963b4`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800963e2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800963b4`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800963e2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800962ea`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800962ea`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009628f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009628f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180096234`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180096234`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180096388`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180096388`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180096273`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180096273`
- `KERNELBASE!LocalAlloc` at `0x1800963c0`
- `KERNELBASE!LocalAlloc` at `0x1800963c0`

## string_xrefs

- `0x1800961ac`: `MachineAccessRestriction`
- `0x180096242`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009642f`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x180096449`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x180096462`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x180096492`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x1800964c3`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x1800964e4`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x1800964fb`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`
- `0x18009652d`: `onecore\com\combase\rpcss\olescm\fixsecuritydescriptors.cpp`

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
0x18009617c  push    rbp
0x18009617e  push    rbx
0x18009617f  push    rsi
0x180096180  push    rdi
0x180096181  push    r12
0x180096183  push    r14
0x180096185  lea     rbp, [rsp-8]
0x18009618a  sub     rsp, 108h
0x180096191  mov     rax, cs:__security_cookie
0x180096198  xor     rax, rsp
0x18009619b  mov     [rbp+30h+var_40], rax
0x18009619f  mov     ecx, 4
0x1800961a4  mov     [rsp+130h+var_C0], 2
0x1800961ac  lea     rax, aMachineaccessr_0; "MachineAccessRestriction"
0x1800961b3  mov     [rsp+130h+var_BC], cx
0x1800961b8  mov     [rsp+130h+var_C8], rax
0x1800961bd  lea     rsi, [rsp+130h+var_C8]
0x1800961c2  lea     rax, ?g_expectedAccessInMachineAccessRestriction@@3QBUExpectedAccess@@B; ExpectedAccess const near * const g_expectedAccessInMachineAccessRestriction
0x1800961c9  mov     [rbp+30h+var_A4], cx
0x1800961cd  mov     [rsp+130h+var_B8], rax
0x1800961d2  lea     r12d, [rcx-3]
0x1800961d6  lea     rax, aMachinelaunchr; "MachineLaunchRestriction"
0x1800961dd  mov     [rbp+30h+var_A8], r12d
0x1800961e1  mov     [rbp+30h+var_B0], rax
0x1800961e5  lea     rax, ?g_expectedAccessInMachineLaunchRestriction@@3QBUExpectedAccess@@B; ExpectedAccess const near * const g_expectedAccessInMachineLaunchRestriction
0x1800961ec  mov     [rbp+30h+var_A0], rax
0x1800961f0  lea     rax, [rbp+30h+var_98]
0x1800961f4  cmp     rsi, rax
0x1800961f7  jz      loc_180096549
0x1800961fd  xor     r14d, r14d
0x180096200  cmp     r14w, [rsi+0Ch]
0x180096205  jnb     loc_180096422
0x18009620b  mov     rdi, [rsi+10h]
0x18009620f  xor     edx, edx; DomainSid
0x180096211  movzx   eax, r14w
0x180096215  mov     [rsp+130h+cbSid], 44h ; 'D'
0x18009621d  lea     rbx, [rax+rax*2]
0x180096221  cmp     [rdi+rbx*8+8], rdx
0x180096226  jnz     short loc_180096256
0x180096228  mov     ecx, [rdi+rbx*8]; WellKnownSidType
0x18009622b  lea     r9, [rsp+130h+cbSid]; cbSid
0x180096230  lea     r8, [rbp+30h+pSid]; pSid
0x180096234  call    cs:__imp_CreateWellKnownSid
0x18009623a  test    eax, eax
0x18009623c  jnz     short loc_1800962A7
0x18009623e  mov     rcx, [rbp+38h]; this
0x180096242  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096249  lea     edx, [rax+2Dh]; void *
0x18009624c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180096251  jmp     loc_18009654B
0x180096256  lea     rcx, [rsp+130h+Sid]
0x18009625b  mov     [rsp+130h+Sid], 0
0x180096264  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180096269  mov     rcx, [rdi+rbx*8+8]; StringSid
0x18009626e  lea     rdx, [rsp+130h+Sid]; Sid
0x180096273  call    cs:__imp_ConvertStringSidToSidW
0x180096279  test    eax, eax
0x18009627b  jz      loc_180096524
0x180096281  mov     r8, [rsp+130h+Sid]; pSourceSid
0x180096286  lea     rdx, [rbp+30h+pSid]; pDestinationSid
0x18009628a  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18009628f  call    cs:__imp_CopySid
0x180096295  test    eax, eax
0x180096297  jz      loc_18009651D
0x18009629d  lea     rcx, [rsp+130h+Sid]
0x1800962a2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800962a7  mov     r8, [rsi]; unsigned __int16 *
0x1800962aa  lea     r9, [rsp+130h+Sid]; void **
0x1800962af  mov     [rsp+130h+Sid], 0
0x1800962b8  call    ?GetNamedValueSD@@YAKPEAUHKEY__@@PEBG1PEAPEAXPEAH@Z; GetNamedValueSD(HKEY__ *,ushort const *,ushort const *,void * *,int *)
0x1800962bd  test    eax, eax
0x1800962bf  jnz     loc_1800964F7
0x1800962c5  mov     rcx, [rsp+130h+Sid]; pSecurityDescriptor
0x1800962ca  lea     r9, [rsp+130h+bDaclDefaulted]; lpbDaclDefaulted
0x1800962cf  lea     r8, [rsp+130h+pDacl]; pDacl
0x1800962d4  mov     [rsp+130h+bDaclPresent], eax
0x1800962d8  lea     rdx, [rsp+130h+bDaclPresent]; lpbDaclPresent
0x1800962dd  mov     [rsp+130h+pDacl], 0
0x1800962e6  mov     [rsp+130h+bDaclDefaulted], eax
0x1800962ea  call    cs:__imp_GetSecurityDescriptorDacl
0x1800962f0  test    eax, eax
0x1800962f2  jz      loc_1800964E0
0x1800962f8  cmp     [rsp+130h+pDacl], 0
0x1800962fe  jz      loc_18009640F
0x180096304  mov     rcx, [rsp+130h+Sid]; pSelfRelativeSecurityDescriptor
0x180096309  lea     rdx, [rsp+130h+pSecurityDescriptor]; void **
0x18009630e  mov     [rsp+130h+pSecurityDescriptor], 0
0x180096317  call    ?MakeSDAbsolute@@YAKPEAXPEAPEAX@Z; MakeSDAbsolute(void *,void * *)
0x18009631c  test    eax, eax
0x18009631e  jnz     loc_1800964BA
0x180096324  mov     rcx, [rsp+130h+pDacl]; pAcl
0x180096329  lea     rdx, [rbp+30h+pSid]; pSid1
0x18009632d  call    ?RemovePrincipalFromACL@@YAKPEAU_ACL@@PEAXK@Z; RemovePrincipalFromACL(_ACL *,void *,ulong)
0x180096332  test    eax, 0FFFFFFFDh
0x180096337  jnz     loc_1800964B3
0x18009633d  mov     r8d, [rdi+rbx*8+10h]; unsigned int
0x180096342  lea     rdx, [rbp+30h+pSid]; pSid1
0x180096346  mov     rcx, [rsp+130h+pDacl]; pAcl
0x18009634b  call    ?UpdatePrincipalInACL@@YAKPEAU_ACL@@PEAXKHK@Z; UpdatePrincipalInACL(_ACL *,void *,ulong,int,ulong)
0x180096350  test    eax, 0FFFFFFFDh
0x180096355  jnz     loc_1800964AC
0x18009635b  mov     edx, [rdi+rbx*8+10h]; unsigned int
0x18009635f  lea     r8, [rbp+30h+pSid]; void *
0x180096363  lea     rcx, [rsp+130h+pDacl]; struct _ACL **
0x180096368  call    ?AddAccessAllowedACEToACL@@YAKPEAPEAU_ACL@@KPEAX@Z; AddAccessAllowedACEToACL(_ACL * *,ulong,void *)
0x18009636d  test    eax, eax
0x18009636f  jnz     loc_1800964A5
0x180096375  mov     rbx, [rsp+130h+pSecurityDescriptor]
0x18009637a  xor     r9d, r9d; bDaclDefaulted
0x18009637d  mov     r8, [rsp+130h+pDacl]; pDacl
0x180096382  mov     rcx, rbx; pSecurityDescriptor
0x180096385  mov     edx, r12d; bDaclPresent
0x180096388  call    cs:__imp_SetSecurityDescriptorDacl
0x18009638e  test    eax, eax
0x180096390  jz      loc_18009648E
0x180096396  mov     rcx, rbx; void *
0x180096399  call    ?CanonicalizeSD@@YAKPEAX@Z; CanonicalizeSD(void *)
0x18009639e  test    eax, eax
0x1800963a0  jnz     loc_180096487
0x1800963a6  lea     r8, [rsp+130h+dwBufferLength]; lpdwBufferLength
0x1800963ab  mov     [rsp+130h+dwBufferLength], eax
0x1800963af  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800963b1  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800963b4  call    cs:__imp_MakeSelfRelativeSD
0x1800963ba  mov     edx, [rsp+130h+dwBufferLength]; uBytes
0x1800963be  xor     ecx, ecx; uFlags
0x1800963c0  call    cs:__imp_LocalAlloc
0x1800963c6  mov     [rsp+130h+var_E0], rax
0x1800963cb  mov     rdi, rax
0x1800963ce  test    rax, rax
0x1800963d1  jz      loc_18009645E
0x1800963d7  lea     r8, [rsp+130h+dwBufferLength]; lpdwBufferLength
0x1800963dc  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1800963df  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800963e2  call    cs:__imp_MakeSelfRelativeSD
0x1800963e8  test    eax, eax
0x1800963ea  jz      short loc_180096445
0x1800963ec  mov     r8, [rsi]; unsigned __int16 *
0x1800963ef  mov     r9, rdi; void *
0x1800963f2  call    ?SetNamedValueSD@@YAKPEAUHKEY__@@PEBG1PEAX@Z; SetNamedValueSD(HKEY__ *,ushort const *,ushort const *,void *)
0x1800963f7  test    eax, eax
0x1800963f9  jnz     short loc_18009642B
0x1800963fb  lea     rcx, [rsp+130h+var_E0]
0x180096400  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180096405  lea     rcx, [rsp+130h+pSecurityDescriptor]
0x18009640a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009640f  lea     rcx, [rsp+130h+Sid]
0x180096414  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180096419  add     r14w, r12w
0x18009641d  jmp     loc_180096200
0x180096422  add     rsi, 18h
0x180096426  jmp     loc_1800961F0
0x18009642b  mov     rcx, [rbp+38h]; this
0x18009642f  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096436  mov     r9d, eax; char *
0x180096439  mov     edx, 69h ; 'i'; void *
0x18009643e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180096443  jmp     short loc_18009645A
0x180096445  mov     rcx, [rbp+38h]; this
0x180096449  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096450  mov     edx, 65h ; 'e'; void *
0x180096455  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009645a  mov     ebx, eax
0x18009645c  jmp     short loc_18009647B
0x18009645e  mov     rcx, [rbp+38h]; this
0x180096462  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096469  mov     ebx, 8007000Eh
0x18009646e  mov     edx, 62h ; 'b'; void *
0x180096473  mov     r9d, ebx; char *
0x180096476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009647b  lea     rcx, [rsp+130h+var_E0]
0x180096480  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180096485  jmp     short loc_1800964D4
0x180096487  mov     edx, 5Ah ; 'Z'
0x18009648c  jmp     short loc_1800964BF
0x18009648e  mov     rcx, [rbp+38h]; this
0x180096492  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096499  mov     edx, 58h ; 'X'; void *
0x18009649e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800964a3  jmp     short loc_1800964D2
0x1800964a5  mov     edx, 55h ; 'U'
0x1800964aa  jmp     short loc_1800964BF
0x1800964ac  mov     edx, 51h ; 'Q'
0x1800964b1  jmp     short loc_1800964BF
0x1800964b3  mov     edx, 4Ah ; 'J'
0x1800964b8  jmp     short loc_1800964BF
0x1800964ba  mov     edx, 45h ; 'E'; void *
0x1800964bf  mov     rcx, [rbp+38h]; this
0x1800964c3  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x1800964ca  mov     r9d, eax; char *
0x1800964cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800964d2  mov     ebx, eax
0x1800964d4  lea     rcx, [rsp+130h+pSecurityDescriptor]
0x1800964d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800964de  jmp     short loc_180096511
0x1800964e0  mov     rcx, [rbp+38h]; this
0x1800964e4  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x1800964eb  mov     edx, 3Eh ; '>'; void *
0x1800964f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800964f5  jmp     short loc_18009650F
0x1800964f7  mov     rcx, [rbp+38h]; this
0x1800964fb  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096502  mov     r9d, eax; char *
0x180096505  mov     edx, 38h ; '8'; void *
0x18009650a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009650f  mov     ebx, eax
0x180096511  lea     rcx, [rsp+130h+Sid]
0x180096516  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009651b  jmp     short loc_180096545
0x18009651d  mov     edx, 33h ; '3'
0x180096522  jmp     short loc_180096529
0x180096524  mov     edx, 32h ; '2'; void *
0x180096529  mov     rcx, [rbp+38h]; this
0x18009652d  lea     r8, aOnecoreComComb_89; "onecore\\com\\combase\\rpcss\\olescm\\f"...
0x180096534  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180096539  lea     rcx, [rsp+130h+Sid]
0x18009653e  mov     ebx, eax
0x180096540  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180096545  mov     eax, ebx
0x180096547  jmp     short loc_18009654B
0x180096549  xor     eax, eax
0x18009654b  mov     rcx, [rbp+30h+var_40]
0x18009654f  xor     rcx, rsp; StackCookie
0x180096552  call    __security_check_cookie
0x180096557  add     rsp, 108h
0x18009655e  pop     r14
0x180096560  pop     r12
0x180096562  pop     rdi
0x180096563  pop     rsi
0x180096564  pop     rbx
0x180096565  pop     rbp
0x180096566  retn
```
