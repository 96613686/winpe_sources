# _TakeOwnerAndAddAccess(ushort const *)

- ea: `0x18001b3e8`
- end: `0x18001b614`
- name: `?_TakeOwnerAndAddAccess@@YAJPEBG@Z`
- size: `556`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800070c8`
- `0x180007834`

## callees

- `0x180005b78`
- `0x1800065d8`
- `0x18000dae0`
- `0x18000db08`
- `0x18000dc30`
- `0x18000e640`
- `0x18001a4b8`
- `0x18001b3e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001b4a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001b4a9`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001b561`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001b561`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001b4fa`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001b5b9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001b4fa`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001b5b9`

## string_xrefs

- `0x18001b450`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001b4bd`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001b50e`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001b57a`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall _TakeOwnerAndAddAccess(LPWSTR pObjectName)
{
  int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  int LastError; // eax
  DWORD v6; // eax
  DWORD v7; // eax
  __int64 v8; // rdx
  int nSubAuthority2; // [rsp+20h] [rbp-89h]
  unsigned int nSubAuthority2a; // [rsp+20h] [rbp-89h]
  PSID psidOwner; // [rsp+60h] [rbp-49h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-41h] BYREF
  unsigned int v14; // [rsp+70h] [rbp-39h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+78h] [rbp-31h] BYREF
  int v16; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+7h]
  __int64 v18; // [rsp+B8h] [rbp+Fh]
  int v19; // [rsp+C0h] [rbp+17h]
  __int128 v20; // [rsp+C8h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v14 = 9;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v2 = CThreadContext::EnablePrivileges((CThreadContext *)&v16, &v14, 1u);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    psidOwner = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
    {
      v6 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, psidOwner, 0, 0, 0);
      if ( !v6 )
      {
        pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
        *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
        *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 2;
        pListOfExplicitEntries.grfAccessPermissions = 2032127;
        pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
        pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
        *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
        NewAcl = 0;
        v7 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
        if ( v7 )
        {
          v8 = 3090;
        }
        else
        {
          v7 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
          if ( !v7 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&NewAcl);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
            v3 = 0;
            goto LABEL_15;
          }
          v8 = 3099;
        }
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v8,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
               (const char *)v7,
               nSubAuthority2a);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&NewAcl);
        goto LABEL_6;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xC02,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                    (const char *)v6,
                    nSubAuthority2a);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBF9,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                    v4);
    }
    v3 = LastError;
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBEA,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)(unsigned int)v2,
    nSubAuthority2);
LABEL_15:
  CThreadContext::~CThreadContext((CThreadContext *)&v16);
  return v3;
}

```

## disassembly

```asm
0x18001b3e8  mov     [rsp-8+arg_8], rbx
0x18001b3ed  mov     [rsp-8+arg_10], rsi
0x18001b3f2  push    rbp
0x18001b3f3  push    rdi
0x18001b3f4  push    r14
0x18001b3f6  lea     rbp, [rsp-47h]
0x18001b3fb  sub     rsp, 0F0h
0x18001b402  mov     rax, cs:__security_cookie
0x18001b409  xor     rax, rsp
0x18001b40c  mov     [rbp+57h+var_20], rax
0x18001b410  xor     esi, esi
0x18001b412  mov     [rbp+57h+var_90], 9
0x18001b419  mov     rdi, rcx
0x18001b41c  mov     [rbp+57h+var_58], esi
0x18001b41f  xorps   xmm0, xmm0
0x18001b422  mov     [rbp+57h+var_50], rsi
0x18001b426  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x18001b42a  mov     [rbp+57h+var_48], rsi
0x18001b42e  lea     r14d, [rsi+1]
0x18001b432  mov     [rbp+57h+var_40], esi
0x18001b435  mov     r8d, r14d; unsigned int
0x18001b438  lea     rcx, [rbp+57h+var_58]; this
0x18001b43c  movdqu  [rbp+57h+var_38], xmm0
0x18001b441  call    ?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z; CThreadContext::EnablePrivileges(ulong *,ulong)
0x18001b446  mov     ebx, eax
0x18001b448  test    eax, eax
0x18001b44a  jns     short loc_18001B469
0x18001b44c  mov     rcx, [rbp+5Fh]; this
0x18001b450  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001b457  mov     r9d, eax; char *
0x18001b45a  mov     edx, 0BEAh; void *
0x18001b45f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b464  jmp     loc_18001B5E4
0x18001b469  lea     rax, [rbp+57h+psidOwner]
0x18001b46d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18001b470  mov     [rsp+100h+pSid], rax; pSid
0x18001b475  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001b479  mov     [rsp+100h+nSubAuthority7], esi; nSubAuthority7
0x18001b47d  mov     r9d, 220h; nSubAuthority1
0x18001b483  mov     [rsp+100h+nSubAuthority6], esi; nSubAuthority6
0x18001b487  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001b48d  mov     [rsp+100h+nSubAuthority5], esi; nSubAuthority5
0x18001b491  mov     dl, 2; nSubAuthorityCount
0x18001b493  mov     [rsp+100h+nSubAuthority4], esi; nSubAuthority4
0x18001b497  mov     [rsp+100h+nSubAuthority3], esi; nSubAuthority3
0x18001b49b  mov     [rsp+100h+nSubAuthority2], esi; nSubAuthority2
0x18001b49f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001b4a5  mov     [rbp+57h+psidOwner], rsi
0x18001b4a9  call    cs:__imp_AllocateAndInitializeSid
0x18001b4b0  nop     dword ptr [rax+rax+00h]
0x18001b4b5  test    eax, eax
0x18001b4b7  jnz     short loc_18001B4DE
0x18001b4b9  mov     rcx, [rbp+5Fh]; this
0x18001b4bd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001b4c4  mov     edx, 0BF9h; void *
0x18001b4c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b4ce  mov     ebx, eax
0x18001b4d0  lea     rcx, [rbp+57h+psidOwner]
0x18001b4d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b4d9  jmp     loc_18001B5E4
0x18001b4de  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x18001b4e2  mov     r8d, r14d; SecurityInfo
0x18001b4e5  mov     qword ptr [rsp+100h+nSubAuthority4], rsi; pSacl
0x18001b4ea  mov     edx, r14d; ObjectType
0x18001b4ed  mov     qword ptr [rsp+100h+nSubAuthority3], rsi; pDacl
0x18001b4f2  mov     rcx, rdi; pObjectName
0x18001b4f5  mov     qword ptr [rsp+100h+nSubAuthority2], rsi; unsigned int
0x18001b4fa  call    cs:__imp_SetNamedSecurityInfoW
0x18001b501  nop     dword ptr [rax+rax+00h]
0x18001b506  test    eax, eax
0x18001b508  jz      short loc_18001B524
0x18001b50a  mov     rcx, [rbp+5Fh]; this
0x18001b50e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001b515  mov     r9d, eax; char *
0x18001b518  mov     edx, 0C02h; void *
0x18001b51d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b522  jmp     short loc_18001B4CE
0x18001b524  mov     rax, [rbp+57h+psidOwner]
0x18001b528  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18001b52c  xor     r8d, r8d; OldAcl
0x18001b52f  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18001b533  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001b537  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18001b53f  mov     ecx, r14d; cCountOfExplicitEntries
0x18001b542  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18001b54a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 1F01FFh
0x18001b551  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r14d
0x18001b555  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x18001b559  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x18001b55d  mov     [rbp+57h+NewAcl], rsi
0x18001b561  call    cs:__imp_SetEntriesInAclW
0x18001b568  nop     dword ptr [rax+rax+00h]
0x18001b56d  test    eax, eax
0x18001b56f  jz      short loc_18001B599
0x18001b571  mov     edx, 0C12h; void *
0x18001b576  mov     rcx, [rbp+5Fh]; this
0x18001b57a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001b581  mov     r9d, eax; char *
0x18001b584  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b589  lea     rcx, [rbp+57h+NewAcl]
0x18001b58d  mov     ebx, eax
0x18001b58f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b594  jmp     loc_18001B4D0
0x18001b599  mov     rax, [rbp+57h+NewAcl]
0x18001b59d  xor     r9d, r9d; psidOwner
0x18001b5a0  mov     qword ptr [rsp+100h+nSubAuthority4], rsi; pSacl
0x18001b5a5  mov     edx, r14d; ObjectType
0x18001b5a8  mov     qword ptr [rsp+100h+nSubAuthority3], rax; pDacl
0x18001b5ad  mov     rcx, rdi; pObjectName
0x18001b5b0  mov     qword ptr [rsp+100h+nSubAuthority2], rsi; psidGroup
0x18001b5b5  lea     r8d, [r9+4]; SecurityInfo
0x18001b5b9  call    cs:__imp_SetNamedSecurityInfoW
0x18001b5c0  nop     dword ptr [rax+rax+00h]
0x18001b5c5  test    eax, eax
0x18001b5c7  jz      short loc_18001B5D0
0x18001b5c9  mov     edx, 0C1Bh
0x18001b5ce  jmp     short loc_18001B576
0x18001b5d0  lea     rcx, [rbp+57h+NewAcl]
0x18001b5d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b5d9  lea     rcx, [rbp+57h+psidOwner]
0x18001b5dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b5e2  mov     ebx, esi
0x18001b5e4  lea     rcx, [rbp+57h+var_58]; this
0x18001b5e8  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001b5ed  mov     eax, ebx
0x18001b5ef  mov     rcx, [rbp+57h+var_20]
0x18001b5f3  xor     rcx, rsp; StackCookie
0x18001b5f6  call    __security_check_cookie
0x18001b5fb  lea     r11, [rsp+100h+var_10]
0x18001b603  mov     rbx, [r11+28h]
0x18001b607  mov     rsi, [r11+30h]
0x18001b60b  mov     rsp, r11
0x18001b60e  pop     r14
0x18001b610  pop     rdi
0x18001b611  pop     rbp
0x18001b612  retn
```
