# MakeSDAbsolute(void *,void * *)

- ea: `0x1801074fc`
- end: `0x180107765`
- name: `?MakeSDAbsolute@@YAKPEAXPEAPEAX@Z`
- size: `617`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009b67c`

## callees

- `0x1800b8428`
- `0x1800fee9c`
- `0x1801074fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801076ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801076ca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180107557`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180107557`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1801075ce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1801075ce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1801075fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1801075fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18010759d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18010759d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180107673`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180107727`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180107673`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180107727`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801075e2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180107614`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801075e2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180107614`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801076ba`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801076ba`
- `KERNELBASE!LocalAlloc` at `0x180107684`
- `KERNELBASE!LocalAlloc` at `0x180107684`

## pseudocode

```c
DWORD __fastcall MakeSDAbsolute(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **a2)
{
  HLOCAL v5; // rax
  void *v6; // rbx
  DWORD LastError; // ebx
  WINBOOL bSaclDefaulted; // [rsp+60h] [rbp+7h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+64h] [rbp+Bh] BYREF
  DWORD dwOwnerSize; // [rsp+68h] [rbp+Fh] BYREF
  DWORD dwSaclSize; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD dwDaclSize; // [rsp+70h] [rbp+17h] BYREF
  PSID pGroup; // [rsp+78h] [rbp+1Fh] BYREF
  PSID pOwner; // [rsp+80h] [rbp+27h] BYREF
  PACL pSacl; // [rsp+88h] [rbp+2Fh] BYREF
  PACL pDacl; // [rsp+90h] [rbp+37h] BYREF
  HLOCAL v17; // [rsp+98h] [rbp+3Fh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+D0h] [rbp+77h] BYREF
  WINBOOL bSaclPresent; // [rsp+D8h] [rbp+7Fh] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  pDacl = 0;
  pSacl = 0;
  pOwner = 0;
  pGroup = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(pSelfRelativeSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    return GetLastError();
  if ( pSacl && bSaclPresent )
    dwSaclSize = pSacl->AclSize;
  if ( !GetSecurityDescriptorDacl(pSelfRelativeSecurityDescriptor, &bSaclPresent, &pDacl, &bSaclDefaulted) )
    return GetLastError();
  if ( pDacl && bSaclPresent )
    dwDaclSize = pDacl->AclSize;
  if ( !GetSecurityDescriptorOwner(pSelfRelativeSecurityDescriptor, &pOwner, &bSaclDefaulted) )
    return GetLastError();
  dwOwnerSize = GetLengthSid(pOwner);
  if ( !GetSecurityDescriptorGroup(pSelfRelativeSecurityDescriptor, &pGroup, &bSaclDefaulted) )
    return GetLastError();
  dwPrimaryGroupSize = GetLengthSid(pGroup);
  dwAbsoluteSecurityDescriptorSize = 0;
  MakeAbsoluteSD(
    pSelfRelativeSecurityDescriptor,
    0,
    &dwAbsoluteSecurityDescriptorSize,
    pDacl,
    &dwDaclSize,
    pSacl,
    &dwSaclSize,
    pOwner,
    &dwOwnerSize,
    pGroup,
    &dwPrimaryGroupSize);
  v5 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
  v17 = v5;
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, dwAbsoluteSecurityDescriptorSize);
    if ( InitializeSecurityDescriptor(v6, 1u)
      && MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           v6,
           &dwAbsoluteSecurityDescriptorSize,
           pDacl,
           &dwDaclSize,
           pSacl,
           &dwSaclSize,
           pOwner,
           &dwOwnerSize,
           pGroup,
           &dwPrimaryGroupSize) )
    {
      *a2 = v6;
      LastError = 0;
      v17 = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 14;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastError;
}

```

## disassembly

```asm
0x1801074fc  mov     [rsp-8+arg_0], rbx
0x180107501  mov     [rsp-8+arg_8], rsi
0x180107506  push    rbp
0x180107507  push    rdi
0x180107508  push    r14
0x18010750a  lea     rbp, [rsp-47h]
0x18010750f  sub     rsp, 0A0h
0x180107516  xor     r14d, r14d
0x180107519  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18010751d  mov     rsi, rdx
0x180107520  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r14d
0x180107524  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180107528  mov     [rbp+57h+dwDaclSize], r14d
0x18010752c  lea     r8, [rbp+57h+pSacl]; pSacl
0x180107530  mov     [rbp+57h+dwSaclSize], r14d
0x180107534  mov     [rbp+57h+dwOwnerSize], r14d
0x180107538  mov     rdi, rcx
0x18010753b  mov     [rbp+57h+dwPrimaryGroupSize], r14d
0x18010753f  mov     [rbp+57h+pDacl], r14
0x180107543  mov     [rbp+57h+pSacl], r14
0x180107547  mov     [rbp+57h+pOwner], r14
0x18010754b  mov     [rbp+57h+pGroup], r14
0x18010754f  mov     [rbp+57h+bSaclPresent], r14d
0x180107553  mov     [rbp+57h+bSaclDefaulted], r14d
0x180107557  call    cs:__imp_GetSecurityDescriptorSacl
0x18010755e  nop     dword ptr [rax+rax+00h]
0x180107563  test    eax, eax
0x180107565  jnz     short loc_180107578
0x180107567  call    cs:__imp_GetLastError
0x18010756e  nop     dword ptr [rax+rax+00h]
0x180107573  jmp     loc_18010774C
0x180107578  mov     rax, [rbp+57h+pSacl]
0x18010757c  test    rax, rax
0x18010757f  jz      short loc_18010758E
0x180107581  cmp     [rbp+57h+bSaclPresent], r14d
0x180107585  jz      short loc_18010758E
0x180107587  movzx   eax, word ptr [rax+2]
0x18010758b  mov     [rbp+57h+dwSaclSize], eax
0x18010758e  lea     r9, [rbp+57h+bSaclDefaulted]; lpbDaclDefaulted
0x180107592  mov     rcx, rdi; pSecurityDescriptor
0x180107595  lea     r8, [rbp+57h+pDacl]; pDacl
0x180107599  lea     rdx, [rbp+57h+bSaclPresent]; lpbDaclPresent
0x18010759d  call    cs:__imp_GetSecurityDescriptorDacl
0x1801075a4  nop     dword ptr [rax+rax+00h]
0x1801075a9  test    eax, eax
0x1801075ab  jz      short loc_180107567
0x1801075ad  mov     rax, [rbp+57h+pDacl]
0x1801075b1  test    rax, rax
0x1801075b4  jz      short loc_1801075C3
0x1801075b6  cmp     [rbp+57h+bSaclPresent], r14d
0x1801075ba  jz      short loc_1801075C3
0x1801075bc  movzx   eax, word ptr [rax+2]
0x1801075c0  mov     [rbp+57h+dwDaclSize], eax
0x1801075c3  lea     r8, [rbp+57h+bSaclDefaulted]; lpbOwnerDefaulted
0x1801075c7  mov     rcx, rdi; pSecurityDescriptor
0x1801075ca  lea     rdx, [rbp+57h+pOwner]; pOwner
0x1801075ce  call    cs:__imp_GetSecurityDescriptorOwner
0x1801075d5  nop     dword ptr [rax+rax+00h]
0x1801075da  test    eax, eax
0x1801075dc  jz      short loc_180107567
0x1801075de  mov     rcx, [rbp+57h+pOwner]; pSid
0x1801075e2  call    cs:__imp_GetLengthSid
0x1801075e9  nop     dword ptr [rax+rax+00h]
0x1801075ee  lea     r8, [rbp+57h+bSaclDefaulted]; lpbGroupDefaulted
0x1801075f2  mov     rcx, rdi; pSecurityDescriptor
0x1801075f5  lea     rdx, [rbp+57h+pGroup]; pGroup
0x1801075f9  mov     [rbp+57h+dwOwnerSize], eax
0x1801075fc  call    cs:__imp_GetSecurityDescriptorGroup
0x180107603  nop     dword ptr [rax+rax+00h]
0x180107608  test    eax, eax
0x18010760a  jz      loc_180107567
0x180107610  mov     rcx, [rbp+57h+pGroup]; pSid
0x180107614  call    cs:__imp_GetLengthSid
0x18010761b  nop     dword ptr [rax+rax+00h]
0x180107620  mov     r9, [rbp+57h+pDacl]; pDacl
0x180107624  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180107628  mov     [rbp+57h+dwPrimaryGroupSize], eax
0x18010762b  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18010762d  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180107631  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r14d
0x180107635  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18010763a  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x18010763d  mov     rax, [rbp+57h+pGroup]
0x180107641  mov     [rsp+0B0h+pPrimaryGroup], rax; pPrimaryGroup
0x180107646  lea     rax, [rbp+57h+dwOwnerSize]
0x18010764a  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18010764f  mov     rax, [rbp+57h+pOwner]
0x180107653  mov     [rsp+0B0h+var_78], rax; pOwner
0x180107658  lea     rax, [rbp+57h+dwSaclSize]
0x18010765c  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x180107661  mov     rax, [rbp+57h+pSacl]
0x180107665  mov     [rsp+0B0h+var_88], rax; pSacl
0x18010766a  lea     rax, [rbp+57h+dwDaclSize]
0x18010766e  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x180107673  call    cs:__imp_MakeAbsoluteSD
0x18010767a  nop     dword ptr [rax+rax+00h]
0x18010767f  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x180107682  xor     ecx, ecx; uFlags
0x180107684  call    cs:__imp_LocalAlloc
0x18010768b  nop     dword ptr [rax+rax+00h]
0x180107690  mov     [rbp+57h+var_18], rax
0x180107694  mov     rbx, rax
0x180107697  test    rax, rax
0x18010769a  jnz     short loc_1801076A4
0x18010769c  lea     ebx, [rax+0Eh]
0x18010769f  jmp     loc_180107741
0x1801076a4  mov     r8d, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x1801076a8  xor     edx, edx; Val
0x1801076aa  mov     rcx, rbx; void *
0x1801076ad  call    memset_0
0x1801076b2  mov     edx, 1; dwRevision
0x1801076b7  mov     rcx, rbx; pSecurityDescriptor
0x1801076ba  call    cs:__imp_InitializeSecurityDescriptor
0x1801076c1  nop     dword ptr [rax+rax+00h]
0x1801076c6  test    eax, eax
0x1801076c8  jnz     short loc_1801076DA
0x1801076ca  call    cs:__imp_GetLastError
0x1801076d1  nop     dword ptr [rax+rax+00h]
0x1801076d6  mov     ebx, eax
0x1801076d8  jmp     short loc_180107741
0x1801076da  mov     rax, [rbp+57h+pGroup]
0x1801076de  lea     r8, [rbp+57h+dwPrimaryGroupSize]
0x1801076e2  mov     rcx, [rbp+57h+pOwner]
0x1801076e6  mov     rdx, [rbp+57h+pSacl]
0x1801076ea  mov     r9, [rbp+57h+pDacl]; pDacl
0x1801076ee  mov     [rsp+0B0h+lpdwPrimaryGroupSize], r8; lpdwPrimaryGroupSize
0x1801076f3  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1801076f7  mov     [rsp+0B0h+pPrimaryGroup], rax; pPrimaryGroup
0x1801076fc  lea     rax, [rbp+57h+dwOwnerSize]
0x180107700  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180107705  lea     rax, [rbp+57h+dwSaclSize]
0x180107709  mov     [rsp+0B0h+var_78], rcx; pOwner
0x18010770e  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x180107711  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x180107716  lea     rax, [rbp+57h+dwDaclSize]
0x18010771a  mov     [rsp+0B0h+var_88], rdx; pSacl
0x18010771f  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x180107722  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x180107727  call    cs:__imp_MakeAbsoluteSD
0x18010772e  nop     dword ptr [rax+rax+00h]
0x180107733  test    eax, eax
0x180107735  jz      short loc_1801076CA
0x180107737  mov     [rsi], rbx
0x18010773a  mov     ebx, r14d
0x18010773d  mov     [rbp+57h+var_18], r14
0x180107741  lea     rcx, [rbp+57h+var_18]
0x180107745  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010774a  mov     eax, ebx
0x18010774c  lea     r11, [rsp+0B0h+var_10]
0x180107754  mov     rbx, [r11+20h]
0x180107758  mov     rsi, [r11+28h]
0x18010775c  mov     rsp, r11
0x18010775f  pop     r14
0x180107761  pop     rdi
0x180107762  pop     rbp
0x180107763  retn
```
