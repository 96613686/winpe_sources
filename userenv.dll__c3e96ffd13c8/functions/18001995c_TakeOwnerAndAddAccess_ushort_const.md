# _TakeOwnerAndAddAccess(ushort const *)

- ea: `0x18001995c`
- end: `0x180019b6f`
- name: `?_TakeOwnerAndAddAccess@@YAJPEBG@Z`
- size: `531`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007a7c`
- `0x18000814c`

## callees

- `0x18000542c`
- `0x180005de0`
- `0x18000ce7c`
- `0x18000cea0`
- `0x18000cfc4`
- `0x18000d9b0`
- `0x180018b04`
- `0x18001995c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019a1d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019a1d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180019ac9`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180019ac9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019a68`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019b1b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019a68`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019b1b`

## string_xrefs

- `0x1800199c4`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180019a2b`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180019a76`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180019adc`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
          v8 = 3086;
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
          v8 = 3095;
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
                    (void *)0xBFE,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                    (const char *)v6,
                    nSubAuthority2a);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBF5,
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
    (void *)0xBE6,
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
0x18001995c  mov     [rsp-8+arg_8], rbx
0x180019961  mov     [rsp-8+arg_10], rsi
0x180019966  push    rbp
0x180019967  push    rdi
0x180019968  push    r14
0x18001996a  lea     rbp, [rsp-47h]
0x18001996f  sub     rsp, 0F0h
0x180019976  mov     rax, cs:__security_cookie
0x18001997d  xor     rax, rsp
0x180019980  mov     [rbp+57h+var_20], rax
0x180019984  xor     esi, esi
0x180019986  mov     [rbp+57h+var_90], 9
0x18001998d  mov     rdi, rcx
0x180019990  mov     [rbp+57h+var_58], esi
0x180019993  xorps   xmm0, xmm0
0x180019996  mov     [rbp+57h+var_50], rsi
0x18001999a  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x18001999e  mov     [rbp+57h+var_48], rsi
0x1800199a2  lea     r14d, [rsi+1]
0x1800199a6  mov     [rbp+57h+var_40], esi
0x1800199a9  mov     r8d, r14d; unsigned int
0x1800199ac  lea     rcx, [rbp+57h+var_58]; this
0x1800199b0  movdqu  [rbp+57h+var_38], xmm0
0x1800199b5  call    ?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z; CThreadContext::EnablePrivileges(ulong *,ulong)
0x1800199ba  mov     ebx, eax
0x1800199bc  test    eax, eax
0x1800199be  jns     short loc_1800199DD
0x1800199c0  mov     rcx, [rbp+5Fh]; this
0x1800199c4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800199cb  mov     r9d, eax; char *
0x1800199ce  mov     edx, 0BE6h; void *
0x1800199d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199d8  jmp     loc_180019B40
0x1800199dd  lea     rax, [rbp+57h+psidOwner]
0x1800199e1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800199e4  mov     [rsp+100h+pSid], rax; pSid
0x1800199e9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800199ed  mov     [rsp+100h+nSubAuthority7], esi; nSubAuthority7
0x1800199f1  mov     r9d, 220h; nSubAuthority1
0x1800199f7  mov     [rsp+100h+nSubAuthority6], esi; nSubAuthority6
0x1800199fb  mov     r8d, 20h ; ' '; nSubAuthority0
0x180019a01  mov     [rsp+100h+nSubAuthority5], esi; nSubAuthority5
0x180019a05  mov     dl, 2; nSubAuthorityCount
0x180019a07  mov     [rsp+100h+nSubAuthority4], esi; nSubAuthority4
0x180019a0b  mov     [rsp+100h+nSubAuthority3], esi; nSubAuthority3
0x180019a0f  mov     [rsp+100h+nSubAuthority2], esi; nSubAuthority2
0x180019a13  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180019a19  mov     [rbp+57h+psidOwner], rsi
0x180019a1d  call    cs:__imp_AllocateAndInitializeSid
0x180019a23  test    eax, eax
0x180019a25  jnz     short loc_180019A4C
0x180019a27  mov     rcx, [rbp+5Fh]; this
0x180019a2b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019a32  mov     edx, 0BF5h; void *
0x180019a37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019a3c  mov     ebx, eax
0x180019a3e  lea     rcx, [rbp+57h+psidOwner]
0x180019a42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019a47  jmp     loc_180019B40
0x180019a4c  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x180019a50  mov     r8d, r14d; SecurityInfo
0x180019a53  mov     qword ptr [rsp+100h+nSubAuthority4], rsi; pSacl
0x180019a58  mov     edx, r14d; ObjectType
0x180019a5b  mov     qword ptr [rsp+100h+nSubAuthority3], rsi; pDacl
0x180019a60  mov     rcx, rdi; pObjectName
0x180019a63  mov     qword ptr [rsp+100h+nSubAuthority2], rsi; unsigned int
0x180019a68  call    cs:__imp_SetNamedSecurityInfoW
0x180019a6e  test    eax, eax
0x180019a70  jz      short loc_180019A8C
0x180019a72  mov     rcx, [rbp+5Fh]; this
0x180019a76  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019a7d  mov     r9d, eax; char *
0x180019a80  mov     edx, 0BFEh; void *
0x180019a85  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019a8a  jmp     short loc_180019A3C
0x180019a8c  mov     rax, [rbp+57h+psidOwner]
0x180019a90  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180019a94  xor     r8d, r8d; OldAcl
0x180019a97  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180019a9b  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180019a9f  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x180019aa7  mov     ecx, r14d; cCountOfExplicitEntries
0x180019aaa  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x180019ab2  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 1F01FFh
0x180019ab9  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r14d
0x180019abd  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x180019ac1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x180019ac5  mov     [rbp+57h+NewAcl], rsi
0x180019ac9  call    cs:__imp_SetEntriesInAclW
0x180019acf  test    eax, eax
0x180019ad1  jz      short loc_180019AFB
0x180019ad3  mov     edx, 0C0Eh; void *
0x180019ad8  mov     rcx, [rbp+5Fh]; this
0x180019adc  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019ae3  mov     r9d, eax; char *
0x180019ae6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019aeb  lea     rcx, [rbp+57h+NewAcl]
0x180019aef  mov     ebx, eax
0x180019af1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019af6  jmp     loc_180019A3E
0x180019afb  mov     rax, [rbp+57h+NewAcl]
0x180019aff  xor     r9d, r9d; psidOwner
0x180019b02  mov     qword ptr [rsp+100h+nSubAuthority4], rsi; pSacl
0x180019b07  mov     edx, r14d; ObjectType
0x180019b0a  mov     qword ptr [rsp+100h+nSubAuthority3], rax; pDacl
0x180019b0f  mov     rcx, rdi; pObjectName
0x180019b12  mov     qword ptr [rsp+100h+nSubAuthority2], rsi; psidGroup
0x180019b17  lea     r8d, [r9+4]; SecurityInfo
0x180019b1b  call    cs:__imp_SetNamedSecurityInfoW
0x180019b21  test    eax, eax
0x180019b23  jz      short loc_180019B2C
0x180019b25  mov     edx, 0C17h
0x180019b2a  jmp     short loc_180019AD8
0x180019b2c  lea     rcx, [rbp+57h+NewAcl]
0x180019b30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019b35  lea     rcx, [rbp+57h+psidOwner]
0x180019b39  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019b3e  mov     ebx, esi
0x180019b40  lea     rcx, [rbp+57h+var_58]; this
0x180019b44  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180019b49  mov     eax, ebx
0x180019b4b  mov     rcx, [rbp+57h+var_20]
0x180019b4f  xor     rcx, rsp; StackCookie
0x180019b52  call    __security_check_cookie
0x180019b57  lea     r11, [rsp+100h+var_10]
0x180019b5f  mov     rbx, [r11+28h]
0x180019b63  mov     rsi, [r11+30h]
0x180019b67  mov     rsp, r11
0x180019b6a  pop     r14
0x180019b6c  pop     rdi
0x180019b6d  pop     rbp
0x180019b6e  retn
```
