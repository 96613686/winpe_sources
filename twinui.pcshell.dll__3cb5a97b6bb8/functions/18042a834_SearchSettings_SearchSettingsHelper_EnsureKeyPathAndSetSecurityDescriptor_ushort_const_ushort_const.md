# SearchSettings::SearchSettingsHelper::EnsureKeyPathAndSetSecurityDescriptor(ushort const *,ushort const *)

- ea: `0x18042a834`
- end: `0x18042ab09`
- name: `?EnsureKeyPathAndSetSecurityDescriptor@SearchSettingsHelper@SearchSettings@@SAJPEBG0@Z`
- size: `725`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18042a1f8`

## callees

- `0x18005f410`
- `0x1800c7c34`
- `0x1800d55f0`
- `0x1800d7c50`
- `0x1802bbaf8`
- `0x1802c56a0`
- `0x180356360`
- `0x180421fc0`
- `0x180427b24`
- `0x18042a834`
- `0x180438140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18042a89f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18042a89f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18042a8e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18042a8e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042a96d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042aa65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042aaaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042aacb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042a96d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042aa65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042aaaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18042aacb`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18042a9a4`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18042a9a4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18042a930`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18042a930`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18042aa8e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18042aa8e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18042aa29`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18042aa29`

## string_xrefs

- `0x18042a8f9`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x18042a949`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x18042a9e3`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x18042aa46`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SearchSettings::SearchSettingsHelper::EnsureKeyPathAndSetSecurityDescriptor(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  HKEY *v2; // rax
  unsigned int Key; // eax
  __int64 v4; // rdx
  HKEY *v5; // rax
  unsigned int LastError; // ebx
  BOOL v7; // ebx
  const char *v8; // r9
  HLOCAL v9; // rcx
  unsigned int SecurityInfoSafeDefault; // eax
  DWORD v11; // ebx
  const char *v12; // r9
  __int64 v13; // rdx
  HLOCAL v14; // rcx
  DWORD v15; // eax
  HLOCAL v16; // rcx
  HLOCAL v17; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-79h]
  unsigned int phkResulta; // [rsp+20h] [rbp-79h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-69h]
  HLOCAL hMem; // [rsp+50h] [rbp-49h] BYREF
  HLOCAL v23; // [rsp+58h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR v24; // [rsp+60h] [rbp-39h] BYREF
  HANDLE handle; // [rsp+68h] [rbp-31h] BYREF
  HLOCAL *p_hMem; // [rsp+70h] [rbp-29h] BYREF
  PSID Sid; // [rsp+78h] [rbp-21h] BYREF
  char v28; // [rsp+80h] [rbp-19h]
  PACL OldAcl; // [rsp+88h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-9h] BYREF
  _OWORD v31[2]; // [rsp+C0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v31[0] = 0;
  v31[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  handle = 0;
  v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                 &handle,
                 a2);
  Key = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Search", 0, 0x3001Fu, v2);
  if ( Key - 2 <= 1 || Key == 1168 )
  {
    v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                   &handle,
                   v4);
    Key = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Search",
            0,
            0,
            0,
            0x60000u,
            0,
            v5,
            0);
  }
  if ( Key )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xA3,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  (const char *)Key,
                  phkResult);
    goto LABEL_24;
  }
  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v28 = 1;
  v7 = ConvertStringSidToSidW(
         L"S-1-15-3-1024-1086922356-207614091-3724853071-841836187-4018695103-34218837-3164163255-155871754",
         &Sid);
  wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v7 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA7,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  v8);
    goto LABEL_8;
  }
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
  pListOfExplicitEntries.grfAccessPermissions = 196639;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 2;
  BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, hMem);
  v24 = 0;
  OldAcl = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v24,
    0);
  SecurityInfoSafeDefault = SecurityHelper::GetSecurityInfoSafe<SecurityHelper::GetSecurityInfoSafeDefaultLogger>(
                              handle,
                              phkResult,
                              &OldAcl,
                              lpSecurityAttributes,
                              &v24);
  if ( SecurityInfoSafeDefault )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xB1,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  (const char *)SecurityInfoSafeDefault,
                  phkResulta);
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
LABEL_8:
    v9 = hMem;
    hMem = 0;
    if ( v9 )
      LocalFree(v9);
    goto LABEL_24;
  }
  v23 = 0;
  p_hMem = &v23;
  Sid = 0;
  v28 = 1;
  v11 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, (PACL *)&Sid);
  wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v11 )
  {
    v12 = (const char *)v11;
    v13 = 182;
    goto LABEL_15;
  }
  v15 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)v23, 0);
  if ( v15 )
  {
    v12 = (const char *)v15;
    v13 = 185;
LABEL_15:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  v12,
                  phkResulta);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      LocalFree(v14);
    goto LABEL_12;
  }
  v16 = v23;
  v23 = 0;
  if ( v16 )
    LocalFree(v16);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
  v17 = hMem;
  hMem = 0;
  if ( v17 )
    LocalFree(v17);
  LastError = 0;
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
  std::wstring::_Tidy_deallocate(v31);
  return LastError;
}

```

## disassembly

```asm
0x18042a834  mov     [rsp-8+arg_0], rbx
0x18042a839  mov     [rsp-8+arg_8], rdi
0x18042a83e  push    rbp
0x18042a83f  lea     rbp, [rsp-57h]
0x18042a844  sub     rsp, 0F0h
0x18042a84b  mov     rax, cs:__security_cookie
0x18042a852  xor     rax, rsp
0x18042a855  mov     [rbp+57h+var_10], rax
0x18042a859  xorps   xmm0, xmm0
0x18042a85c  movups  [rbp+57h+var_30], xmm0
0x18042a860  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18042a868  movdqu  [rbp+57h+var_20], xmm1
0x18042a86d  xor     edi, edi
0x18042a86f  mov     word ptr [rbp+57h+var_30], di
0x18042a873  mov     [rbp+57h+handle], rdi
0x18042a877  lea     rcx, [rbp+57h+handle]
0x18042a87b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18042a880  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18042a885  mov     r9d, 3001Fh; samDesired
0x18042a88b  xor     r8d, r8d; ulOptions
0x18042a88e  lea     rdx, aSoftwareMicros_62; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18042a895  mov     rbx, 0FFFFFFFF80000001h
0x18042a89c  mov     rcx, rbx; hKey
0x18042a89f  call    cs:__imp_RegOpenKeyExW
0x18042a8a5  lea     ecx, [rax-2]
0x18042a8a8  cmp     ecx, 1
0x18042a8ab  jbe     short loc_18042A8B4
0x18042a8ad  cmp     eax, 490h
0x18042a8b2  jnz     short loc_18042A8EE
0x18042a8b4  lea     rcx, [rbp+57h+handle]
0x18042a8b8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18042a8bd  mov     [rsp+0F0h+lpdwDisposition], rdi; lpdwDisposition
0x18042a8c2  mov     [rsp+0F0h+var_B8], rax; phkResult
0x18042a8c7  mov     [rsp+0F0h+lpSecurityAttributes], rdi; int
0x18042a8cc  mov     [rsp+0F0h+samDesired], 60000h; samDesired
0x18042a8d4  mov     dword ptr [rsp+0F0h+phkResult], edi; unsigned int
0x18042a8d8  xor     r9d, r9d; lpClass
0x18042a8db  xor     r8d, r8d; Reserved
0x18042a8de  lea     rdx, aSoftwareMicros_62; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18042a8e5  mov     rcx, rbx; hKey
0x18042a8e8  call    cs:__imp_RegCreateKeyExW
0x18042a8ee  test    eax, eax
0x18042a8f0  jz      short loc_18042A911
0x18042a8f2  mov     rcx, [rbp+5Fh]; this
0x18042a8f6  mov     r9d, eax; char *
0x18042a8f9  lea     r8, aShellcommonInt_3; "shellcommon\\internal\\shell\\inc\\Sear"...
0x18042a900  mov     edx, 0A3h; void *
0x18042a905  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18042a90a  mov     ebx, eax
0x18042a90c  jmp     loc_18042AAD3
0x18042a911  mov     [rbp+57h+hMem], rdi
0x18042a915  lea     rax, [rbp+57h+hMem]
0x18042a919  mov     [rbp+57h+var_80], rax
0x18042a91d  mov     [rbp+57h+Sid], rdi
0x18042a921  mov     [rbp+57h+var_70], 1
0x18042a925  lea     rdx, [rbp+57h+Sid]; Sid
0x18042a929  lea     rcx, StringSid; "S-1-15-3-1024-1086922356-207614091-3724"...
0x18042a930  call    cs:__imp_ConvertStringSidToSidW
0x18042a936  mov     ebx, eax
0x18042a938  lea     rcx, [rbp+57h+var_80]
0x18042a93c  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18042a941  test    ebx, ebx
0x18042a943  jnz     short loc_18042A978
0x18042a945  mov     rcx, [rbp+5Fh]; this
0x18042a949  lea     r8, aShellcommonInt_3; "shellcommon\\internal\\shell\\inc\\Sear"...
0x18042a950  mov     edx, 0A7h; void *
0x18042a955  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18042a95a  mov     ebx, eax
0x18042a95c  mov     rcx, [rbp+57h+hMem]; hMem
0x18042a960  mov     [rbp+57h+hMem], rdi
0x18042a964  test    rcx, rcx
0x18042a967  jz      loc_18042AAD3
0x18042a96d  call    cs:__imp_LocalFree
0x18042a973  jmp     loc_18042AAD3
0x18042a978  xorps   xmm0, xmm0
0x18042a97b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18042a97f  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18042a983  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18042a987  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 3001Fh
0x18042a98e  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x18042a995  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 2
0x18042a99c  mov     rdx, [rbp+57h+hMem]; pSid
0x18042a9a0  lea     rcx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x18042a9a4  call    cs:__imp_BuildTrusteeWithSidW
0x18042a9aa  mov     [rbp+57h+var_90], rdi
0x18042a9ae  mov     [rbp+57h+OldAcl], rdi
0x18042a9b2  xor     edx, edx
0x18042a9b4  lea     rcx, [rbp+57h+var_90]
0x18042a9b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18042a9bd  lea     rax, [rbp+57h+var_90]
0x18042a9c1  mov     [rsp+0F0h+var_B8], rax; PSECURITY_DESCRIPTOR *
0x18042a9c6  lea     rax, [rbp+57h+OldAcl]
0x18042a9ca  mov     qword ptr [rsp+0F0h+samDesired], rax; PACL *
0x18042a9cf  mov     rcx, [rbp+57h+handle]; handle
0x18042a9d3  call    ??$GetSecurityInfoSafe@UGetSecurityInfoSafeDefaultLogger@SecurityHelper@@@SecurityHelper@@YAKPEAXW4_SE_OBJECT_TYPE@@KPEAPEAX2PEAPEAU_ACL@@32@Z; SecurityHelper::GetSecurityInfoSafe<SecurityHelper::GetSecurityInfoSafeDefaultLogger>(void *,_SE_OBJECT_TYPE,ulong,void * *,void * *,_ACL * *,_ACL * *,void * *)
0x18042a9d8  test    eax, eax
0x18042a9da  jz      short loc_18042AA04
0x18042a9dc  mov     rcx, [rbp+5Fh]; this
0x18042a9e0  mov     r9d, eax; char *
0x18042a9e3  lea     r8, aShellcommonInt_3; "shellcommon\\internal\\shell\\inc\\Sear"...
0x18042a9ea  mov     edx, 0B1h; void *
0x18042a9ef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18042a9f4  mov     ebx, eax
0x18042a9f6  lea     rcx, [rbp+57h+var_90]
0x18042a9fa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18042a9ff  jmp     loc_18042A95C
0x18042aa04  mov     [rbp+57h+var_98], rdi
0x18042aa08  lea     rax, [rbp+57h+var_98]
0x18042aa0c  mov     [rbp+57h+var_80], rax
0x18042aa10  mov     [rbp+57h+Sid], rdi
0x18042aa14  mov     [rbp+57h+var_70], 1
0x18042aa18  lea     r9, [rbp+57h+Sid]; NewAcl
0x18042aa1c  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x18042aa20  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18042aa24  mov     ecx, 1; cCountOfExplicitEntries
0x18042aa29  call    cs:__imp_SetEntriesInAclW
0x18042aa2f  mov     ebx, eax
0x18042aa31  lea     rcx, [rbp+57h+var_80]
0x18042aa35  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18042aa3a  test    ebx, ebx
0x18042aa3c  jz      short loc_18042AA6D
0x18042aa3e  mov     r9d, ebx; char *
0x18042aa41  mov     edx, 0B6h; void *
0x18042aa46  lea     r8, aShellcommonInt_3; "shellcommon\\internal\\shell\\inc\\Sear"...
0x18042aa4d  mov     rcx, [rbp+5Fh]; this
0x18042aa51  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18042aa56  mov     ebx, eax
0x18042aa58  mov     rcx, [rbp+57h+var_98]; hMem
0x18042aa5c  mov     [rbp+57h+var_98], rdi
0x18042aa60  test    rcx, rcx
0x18042aa63  jz      short loc_18042A9F6
0x18042aa65  call    cs:__imp_LocalFree
0x18042aa6b  jmp     short loc_18042A9F6
0x18042aa6d  mov     rax, [rbp+57h+var_98]
0x18042aa71  mov     [rsp+0F0h+lpSecurityAttributes], rdi; pSacl
0x18042aa76  mov     qword ptr [rsp+0F0h+samDesired], rax; pDacl
0x18042aa7b  mov     [rsp+0F0h+phkResult], rdi; psidGroup
0x18042aa80  xor     r9d, r9d; psidOwner
0x18042aa83  lea     edx, [r9+4]; ObjectType
0x18042aa87  mov     r8d, edx; SecurityInfo
0x18042aa8a  mov     rcx, [rbp+57h+handle]; handle
0x18042aa8e  call    cs:__imp_SetSecurityInfo
0x18042aa94  test    eax, eax
0x18042aa96  jz      short loc_18042AAA2
0x18042aa98  mov     r9d, eax
0x18042aa9b  mov     edx, 0B9h
0x18042aaa0  jmp     short loc_18042AA46
0x18042aaa2  mov     rcx, [rbp+57h+var_98]; hMem
0x18042aaa6  mov     [rbp+57h+var_98], rdi
0x18042aaaa  test    rcx, rcx
0x18042aaad  jz      short loc_18042AAB5
0x18042aaaf  call    cs:__imp_LocalFree
0x18042aab5  lea     rcx, [rbp+57h+var_90]
0x18042aab9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18042aabe  mov     rcx, [rbp+57h+hMem]; hMem
0x18042aac2  mov     [rbp+57h+hMem], rdi
0x18042aac6  test    rcx, rcx
0x18042aac9  jz      short loc_18042AAD1
0x18042aacb  call    cs:__imp_LocalFree
0x18042aad1  mov     ebx, edi
0x18042aad3  lea     rcx, [rbp+57h+handle]
0x18042aad7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18042aadc  nop
0x18042aadd  lea     rcx, [rbp+57h+var_30]
0x18042aae1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18042aae6  mov     eax, ebx
0x18042aae8  mov     rcx, [rbp+57h+var_10]
0x18042aaec  xor     rcx, rsp; StackCookie
0x18042aaef  call    __security_check_cookie
0x18042aaf4  lea     r11, [rsp+0F0h+var_s0]
0x18042aafc  mov     rbx, [r11+10h]
0x18042ab00  mov     rdi, [r11+18h]
0x18042ab04  mov     rsp, r11
0x18042ab07  pop     rbp
0x18042ab08  retn
```
