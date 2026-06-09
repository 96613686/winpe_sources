# _anonymous_namespace_::GetDefaultAccountSidAsString

- ea: `0x1800a5180`
- end: `0x1800a532d`
- name: `_anonymous_namespace_::GetDefaultAccountSidAsString`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a4d34`

## callees

- `0x1800581b8`
- `0x1800581d8`
- `0x1800a4cd4`
- `0x1800a4cf4`
- `0x1800a4d14`
- `0x1800a5180`
- `0x1800a68d4`
- `0x1800c7366`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a5269`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a5269`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a52a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a52a5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800a520c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800a520c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800a51ce`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800a51ce`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetDefaultAccountSidAsString(LPWSTR *a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  int LastError; // eax
  const char *v6; // r9
  const char *v7; // r9
  LPWSTR StringSid; // [rsp+20h] [rbp-59h] BYREF
  PVOID DomainInfo; // [rsp+28h] [rbp-51h] BYREF
  DWORD cbSid; // [rsp+30h] [rbp-49h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-41h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-39h] BYREF
  _BYTE pSid[80]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a1,
    0);
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x1FD,
           (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
           (const char *)(unsigned int)v2,
           (int)StringSid);
    goto LABEL_14;
  }
  DomainInfo = 0;
  v4 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  if ( v4 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x200,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
                  (const char *)(unsigned int)v4,
                  (int)StringSid);
LABEL_5:
    v3 = LastError;
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&DomainInfo);
    goto LABEL_14;
  }
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          pSid,
          &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x204,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
                  v6);
    goto LABEL_5;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(pSid, &StringSid) )
  {
    v3 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x207,
           (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
           v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_6;
  }
  if ( a1 != &StringSid )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1,
      StringSid);
    StringSid = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&DomainInfo);
  v3 = 0;
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v3;
}

```

## disassembly

```asm
0x1800a5180  mov     [rsp-8+arg_8], rbx
0x1800a5185  push    rbp
0x1800a5186  lea     rbp, [rsp-57h]
0x1800a518b  sub     rsp, 0D0h
0x1800a5192  mov     rax, cs:__security_cookie
0x1800a5199  xor     rax, rsp
0x1800a519c  mov     [rbp+57h+var_10], rax
0x1800a51a0  xor     edx, edx
0x1800a51a2  mov     rbx, rcx
0x1800a51a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a51aa  xorps   xmm0, xmm0
0x1800a51ad  mov     [rbp+57h+PolicyHandle], 0
0x1800a51b5  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800a51b9  mov     edx, 1; AccessMask
0x1800a51be  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800a51c2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800a51c6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800a51ca  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a51ce  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800a51d4  test    eax, eax
0x1800a51d6  jns     short loc_1800A51F7
0x1800a51d8  mov     rcx, [rbp+5Fh]; this
0x1800a51dc  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x1800a51e3  mov     r9d, eax; char *
0x1800a51e6  mov     edx, 1FDh; void *
0x1800a51eb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a51f0  mov     ebx, eax
0x1800a51f2  jmp     loc_1800A5305
0x1800a51f7  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800a51fb  lea     r8, [rbp+57h+DomainInfo]; DomainInfo
0x1800a51ff  mov     edx, 5; DomainInfoClass
0x1800a5204  mov     [rbp+57h+DomainInfo], 0
0x1800a520c  call    cs:__imp_LsaLookupGetDomainInfo
0x1800a5212  test    eax, eax
0x1800a5214  jns     short loc_1800A523E
0x1800a5216  mov     rcx, [rbp+5Fh]; this
0x1800a521a  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x1800a5221  mov     r9d, eax; char *
0x1800a5224  mov     edx, 200h; void *
0x1800a5229  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a522e  mov     ebx, eax
0x1800a5230  lea     rcx, [rbp+57h+DomainInfo]
0x1800a5234  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800a5239  jmp     loc_1800A5305
0x1800a523e  xor     edx, edx; Val
0x1800a5240  lea     rcx, [rbp+57h+pSid]; void *
0x1800a5244  lea     r8d, [rdx+44h]; Size
0x1800a5248  call    memset_0
0x1800a524d  mov     rdx, [rbp+57h+DomainInfo]
0x1800a5251  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800a5255  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800a525c  lea     r8, [rbp+57h+pSid]; pSid
0x1800a5260  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x1800a5265  mov     rdx, [rdx+10h]; DomainSid
0x1800a5269  call    cs:__imp_CreateWellKnownSid
0x1800a526f  test    eax, eax
0x1800a5271  jnz     short loc_1800A528A
0x1800a5273  mov     rcx, [rbp+5Fh]; this
0x1800a5277  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x1800a527e  mov     edx, 204h; void *
0x1800a5283  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a5288  jmp     short loc_1800A522E
0x1800a528a  xor     edx, edx
0x1800a528c  mov     [rbp+57h+StringSid], 0
0x1800a5294  lea     rcx, [rbp+57h+StringSid]
0x1800a5298  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a529d  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800a52a1  lea     rcx, [rbp+57h+pSid]; Sid
0x1800a52a5  call    cs:__imp_ConvertSidToStringSidW
0x1800a52ab  test    eax, eax
0x1800a52ad  jnz     short loc_1800A52D4
0x1800a52af  mov     rcx, [rbp+5Fh]; this
0x1800a52b3  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x1800a52ba  mov     edx, 207h; void *
0x1800a52bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a52c4  lea     rcx, [rbp+57h+StringSid]
0x1800a52c8  mov     ebx, eax
0x1800a52ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a52cf  jmp     loc_1800A5230
0x1800a52d4  lea     rax, [rbp+57h+StringSid]
0x1800a52d8  cmp     rbx, rax
0x1800a52db  jz      short loc_1800A52F1
0x1800a52dd  mov     rdx, [rbp+57h+StringSid]
0x1800a52e1  mov     rcx, rbx
0x1800a52e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a52e9  mov     [rbp+57h+StringSid], 0
0x1800a52f1  lea     rcx, [rbp+57h+StringSid]
0x1800a52f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a52fa  lea     rcx, [rbp+57h+DomainInfo]
0x1800a52fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800a5303  xor     ebx, ebx
0x1800a5305  lea     rcx, [rbp+57h+PolicyHandle]
0x1800a5309  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a530e  mov     eax, ebx
0x1800a5310  mov     rcx, [rbp+57h+var_10]
0x1800a5314  xor     rcx, rsp; StackCookie
0x1800a5317  call    __security_check_cookie
0x1800a531c  mov     rbx, [rsp+0D0h+arg_8]
0x1800a5324  add     rsp, 0D0h
0x1800a532b  pop     rbp
0x1800a532c  retn
```
