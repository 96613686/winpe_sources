# SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)

- ea: `0x180461be8`
- end: `0x180461efa`
- name: `?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z`
- size: `786`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const wchar_t *, struct _EXPLICIT_ACCESS_W *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180132ed8`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x180020a14`
- `0x1800245ac`
- `0x180025264`
- `0x180026860`
- `0x18008fc6c`
- `0x1800a8430`
- `0x1800d971c`
- `0x1800e2988`
- `0x1800e34bc`
- `0x1800e3660`
- `0x18015cb00`
- `0x180461aac`
- `0x180461b90`
- `0x180461be8`
- `0x1804623c8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180461e5c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180461e5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180461cbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180461cbb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180461d26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180461d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180461e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180461eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180461e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180461eb8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180461e33`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180461e33`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180461dce`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180461dce`

## string_xrefs

- `0x180461d38`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x180461d89`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x180461deb`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x180461e6a`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x180461e88`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
        LPCWSTR lpSubKey,
        const wchar_t *a2,
        struct _EXPLICIT_ACCESS_W *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned __int64 Key; // r9
  const WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  unsigned int SecurityInfoSafeDefault; // eax
  DWORD v18; // ebx
  const char *v19; // r9
  __int64 v20; // rdx
  HLOCAL v21; // rcx
  DWORD v22; // eax
  HKEY v23; // rbx
  const char *v24; // r9
  int LastError; // eax
  HLOCAL v26; // rcx
  HKEY *phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A9h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-99h]
  HKEY *v32; // [rsp+38h] [rbp-91h]
  HLOCAL hMem; // [rsp+50h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR v34; // [rsp+58h] [rbp-71h] BYREF
  HANDLE handle; // [rsp+60h] [rbp-69h] BYREF
  PACL OldAcl; // [rsp+68h] [rbp-61h] BYREF
  struct _ACL pAcl; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v38[3]; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int64 v39; // [rsp+90h] [rbp-39h]
  HLOCAL *p_hMem; // [rsp+98h] [rbp-31h] BYREF
  PACL NewAcl; // [rsp+A0h] [rbp-29h] BYREF
  char v42; // [rsp+A8h] [rbp-21h]
  _BYTE v43[32]; // [rsp+B8h] [rbp-11h] BYREF
  _BYTE v44[32]; // [rsp+D8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  std::wstring::wstring(v38);
  if ( v6 )
  {
    v7 = std::wstring::wstring(v44, v6);
    v8 = std::operator+<wchar_t>(v43, v7, L"\\");
    v9 = std::operator+<wchar_t>(&p_hMem, v8, lpSubKey);
    std::wstring::operator=(v38, v9);
    std::filesystem::path::~path((std::filesystem::path *)&p_hMem);
    std::filesystem::path::~path((std::filesystem::path *)v43);
    std::filesystem::path::~path((std::filesystem::path *)v44);
  }
  handle = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
  if ( a2 )
  {
    v10 = (const WCHAR *)v38;
    if ( v39 > 7 )
      v10 = (const WCHAR *)v38[0];
    v11 = -2147483645;
  }
  else
  {
    v10 = lpSubKey;
    v11 = -2147483647;
  }
  v12 = RegOpenKeyExW((HKEY)v11, v10, 0, 0x3001Fu, phkResult);
  Key = v12;
  if ( v12 - 2 <= 1 || v12 == 1168 )
  {
    v32 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
    if ( a2 )
    {
      v14 = (const WCHAR *)v38;
      if ( v39 > 7 )
        v14 = (const WCHAR *)v38[0];
      v15 = -2147483645;
    }
    else
    {
      v14 = lpSubKey;
      v15 = -2147483647;
    }
    Key = (unsigned int)RegCreateKeyExW((HKEY)v15, v14, 0, 0, 0, 0x60000u, 0, v32, 0);
  }
  if ( (_DWORD)Key )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x36C,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
            (const char *)Key,
            phkResulta);
    goto LABEL_35;
  }
  v34 = 0;
  OldAcl = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v34,
    0);
  SecurityInfoSafeDefault = SecurityHelper::GetSecurityInfoSafe<SecurityHelper::GetSecurityInfoSafeDefaultLogger>(
                              handle,
                              phkResulta,
                              &OldAcl,
                              lpSecurityAttributes,
                              &v34);
  if ( SecurityInfoSafeDefault )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x371,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
            (const char *)SecurityInfoSafeDefault,
            phkResultb);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v34);
    goto LABEL_35;
  }
  hMem = 0;
  p_hMem = &hMem;
  NewAcl = 0;
  v42 = 1;
  v18 = SetEntriesInAclW(1u, a3, OldAcl, &NewAcl);
  wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v18 )
  {
    v19 = (const char *)v18;
    v20 = 886;
LABEL_23:
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v20,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
            v19,
            phkResultb);
    goto LABEL_24;
  }
  v22 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)hMem, 0);
  if ( v22 )
  {
    v19 = (const char *)v22;
    v20 = 889;
    goto LABEL_23;
  }
  v23 = (HKEY)handle;
  pAcl = 0;
  if ( InitializeAcl(&pAcl, 8u, 2u) )
  {
    SearchSettings::SearchSettingsHelper::SetUnprotectedDaclRecursive(v23, &pAcl);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x387,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  v24);
    v16 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37E,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
        (const char *)(unsigned int)LastError,
        phkResultb);
LABEL_24:
      v21 = hMem;
      hMem = 0;
      if ( v21 )
        LocalFree(v21);
      goto LABEL_20;
    }
  }
  v26 = hMem;
  hMem = 0;
  if ( v26 )
    LocalFree(v26);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v34);
  v16 = 0;
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
  std::filesystem::path::~path((std::filesystem::path *)v38);
  return v16;
}

```

## disassembly

```asm
0x180461be8  push    rbp
0x180461bea  push    rbx
0x180461beb  push    rsi
0x180461bec  push    rdi
0x180461bed  push    r14
0x180461bef  lea     rbp, [rsp-37h]
0x180461bf4  sub     rsp, 100h
0x180461bfb  mov     rax, cs:__security_cookie
0x180461c02  xor     rax, rsp
0x180461c05  mov     [rbp+57h+var_28], rax
0x180461c09  mov     rsi, r8
0x180461c0c  mov     rbx, rdx
0x180461c0f  mov     rdi, rcx
0x180461c12  lea     rcx, [rbp+57h+var_A8]
0x180461c16  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180461c1b  nop
0x180461c1c  xor     r14d, r14d
0x180461c1f  test    rdx, rdx
0x180461c22  jz      short loc_180461C7A
0x180461c24  lea     rcx, [rbp+57h+var_48]
0x180461c28  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180461c2d  nop
0x180461c2e  lea     r8, StringValue; "\\"
0x180461c35  mov     rdx, rax
0x180461c38  lea     rcx, [rbp+57h+var_68]
0x180461c3c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180461c41  nop
0x180461c42  mov     r8, rdi
0x180461c45  mov     rdx, rax
0x180461c48  lea     rcx, [rbp+57h+var_88]
0x180461c4c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180461c51  mov     rdx, rax
0x180461c54  lea     rcx, [rbp+57h+var_A8]
0x180461c58  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180461c5d  lea     rcx, [rbp+57h+var_88]; this
0x180461c61  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180461c66  nop
0x180461c67  lea     rcx, [rbp+57h+var_68]; this
0x180461c6b  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180461c70  nop
0x180461c71  lea     rcx, [rbp+57h+var_48]; this
0x180461c75  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180461c7a  mov     [rbp+57h+handle], r14
0x180461c7e  lea     rcx, [rbp+57h+handle]
0x180461c82  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180461c87  mov     [rsp+120h+phkResult], rax; phkResult
0x180461c8c  mov     r9d, 3001Fh; samDesired
0x180461c92  test    rbx, rbx
0x180461c95  jz      short loc_180461CAE
0x180461c97  lea     rdx, [rbp+57h+var_A8]
0x180461c9b  cmp     [rbp+57h+var_90], 7
0x180461ca0  cmova   rdx, [rbp+57h+var_A8]
0x180461ca5  mov     rcx, 0FFFFFFFF80000003h
0x180461cac  jmp     short loc_180461CB8
0x180461cae  mov     rdx, rdi; lpSubKey
0x180461cb1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180461cb8  xor     r8d, r8d; ulOptions
0x180461cbb  call    cs:__imp_RegOpenKeyExW
0x180461cc1  mov     r9d, eax
0x180461cc4  lea     eax, [rax-2]
0x180461cc7  cmp     eax, 1
0x180461cca  jbe     short loc_180461CD5
0x180461ccc  cmp     r9d, 490h
0x180461cd3  jnz     short loc_180461D2F
0x180461cd5  lea     rcx, [rbp+57h+handle]
0x180461cd9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180461cde  mov     [rsp+120h+lpdwDisposition], r14; lpdwDisposition
0x180461ce3  mov     [rsp+120h+var_E8], rax; phkResult
0x180461ce8  mov     [rsp+120h+lpSecurityAttributes], r14; int
0x180461ced  mov     [rsp+120h+samDesired], 60000h; samDesired
0x180461cf5  mov     dword ptr [rsp+120h+phkResult], r14d; unsigned int
0x180461cfa  test    rbx, rbx
0x180461cfd  jz      short loc_180461D16
0x180461cff  lea     rdx, [rbp+57h+var_A8]
0x180461d03  cmp     [rbp+57h+var_90], 7
0x180461d08  cmova   rdx, [rbp+57h+var_A8]
0x180461d0d  mov     rcx, 0FFFFFFFF80000003h
0x180461d14  jmp     short loc_180461D20
0x180461d16  mov     rdx, rdi; lpSubKey
0x180461d19  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180461d20  xor     r9d, r9d; lpClass
0x180461d23  xor     r8d, r8d; Reserved
0x180461d26  call    cs:__imp_RegCreateKeyExW
0x180461d2c  mov     r9d, eax; char *
0x180461d2f  test    r9d, r9d
0x180461d32  jz      short loc_180461D50
0x180461d34  mov     rcx, [rbp+5Fh]; this
0x180461d38  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180461d3f  mov     edx, 36Ch; void *
0x180461d44  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180461d49  mov     ebx, eax
0x180461d4b  jmp     loc_180461ECB
0x180461d50  mov     [rbp+57h+var_C8], r14
0x180461d54  mov     [rbp+57h+OldAcl], r14
0x180461d58  xor     edx, edx
0x180461d5a  lea     rcx, [rbp+57h+var_C8]
0x180461d5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180461d63  lea     rax, [rbp+57h+var_C8]
0x180461d67  mov     [rsp+120h+var_E8], rax; PSECURITY_DESCRIPTOR *
0x180461d6c  lea     rax, [rbp+57h+OldAcl]
0x180461d70  mov     qword ptr [rsp+120h+samDesired], rax; PACL *
0x180461d75  mov     rcx, [rbp+57h+handle]; handle
0x180461d79  call    ??$GetSecurityInfoSafe@UGetSecurityInfoSafeDefaultLogger@SecurityHelper@@@SecurityHelper@@YAKPEAXW4_SE_OBJECT_TYPE@@KPEAPEAX2PEAPEAU_ACL@@32@Z; SecurityHelper::GetSecurityInfoSafe<SecurityHelper::GetSecurityInfoSafeDefaultLogger>(void *,_SE_OBJECT_TYPE,ulong,void * *,void * *,_ACL * *,_ACL * *,void * *)
0x180461d7e  test    eax, eax
0x180461d80  jz      short loc_180461DAA
0x180461d82  mov     rcx, [rbp+5Fh]; this
0x180461d86  mov     r9d, eax; char *
0x180461d89  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180461d90  mov     edx, 371h; void *
0x180461d95  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180461d9a  mov     ebx, eax
0x180461d9c  lea     rcx, [rbp+57h+var_C8]
0x180461da0  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180461da5  jmp     loc_180461ECB
0x180461daa  mov     [rbp+57h+hMem], r14
0x180461dae  lea     rax, [rbp+57h+hMem]
0x180461db2  mov     [rbp+57h+var_88], rax
0x180461db6  mov     [rbp+57h+NewAcl], r14
0x180461dba  mov     [rbp+57h+var_78], 1
0x180461dbe  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180461dc2  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x180461dc6  mov     rdx, rsi; pListOfExplicitEntries
0x180461dc9  mov     ecx, 1; cCountOfExplicitEntries
0x180461dce  call    cs:__imp_SetEntriesInAclW
0x180461dd4  mov     ebx, eax
0x180461dd6  lea     rcx, [rbp+57h+var_88]
0x180461dda  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180461ddf  test    ebx, ebx
0x180461de1  jz      short loc_180461E12
0x180461de3  mov     r9d, ebx; char *
0x180461de6  mov     edx, 376h; void *
0x180461deb  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180461df2  mov     rcx, [rbp+5Fh]; this
0x180461df6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180461dfb  mov     ebx, eax
0x180461dfd  mov     rcx, [rbp+57h+hMem]; hMem
0x180461e01  mov     [rbp+57h+hMem], r14
0x180461e05  test    rcx, rcx
0x180461e08  jz      short loc_180461D9C
0x180461e0a  call    cs:__imp_LocalFree
0x180461e10  jmp     short loc_180461D9C
0x180461e12  mov     rax, [rbp+57h+hMem]
0x180461e16  mov     [rsp+120h+lpSecurityAttributes], r14; pSacl
0x180461e1b  mov     qword ptr [rsp+120h+samDesired], rax; pDacl
0x180461e20  mov     [rsp+120h+phkResult], r14; int
0x180461e25  xor     r9d, r9d; psidOwner
0x180461e28  lea     edx, [r9+4]; ObjectType
0x180461e2c  mov     r8d, edx; SecurityInfo
0x180461e2f  mov     rcx, [rbp+57h+handle]; handle
0x180461e33  call    cs:__imp_SetSecurityInfo
0x180461e39  test    eax, eax
0x180461e3b  jz      short loc_180461E47
0x180461e3d  mov     r9d, eax
0x180461e40  mov     edx, 379h
0x180461e45  jmp     short loc_180461DEB
0x180461e47  mov     rbx, [rbp+57h+handle]
0x180461e4b  mov     qword ptr [rbp+57h+pAcl.AclRevision], r14
0x180461e4f  mov     edx, 8; nAclLength
0x180461e54  lea     r8d, [rdx-6]; dwAclRevision
0x180461e58  lea     rcx, [rbp+57h+pAcl]; pAcl
0x180461e5c  call    cs:__imp_InitializeAcl
0x180461e62  test    eax, eax
0x180461e64  jnz     short loc_180461E9E
0x180461e66  mov     rcx, [rbp+5Fh]; this
0x180461e6a  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180461e71  mov     edx, 387h; void *
0x180461e76  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180461e7b  mov     ebx, eax
0x180461e7d  test    eax, eax
0x180461e7f  jns     short loc_180461EAB
0x180461e81  mov     rcx, [rbp+5Fh]; this
0x180461e85  mov     r9d, eax; char *
0x180461e88  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180461e8f  mov     edx, 37Eh; void *
0x180461e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180461e99  jmp     loc_180461DFD
0x180461e9e  lea     rdx, [rbp+57h+pAcl]; struct _ACL *
0x180461ea2  mov     rcx, rbx; HKEY
0x180461ea5  call    ?SetUnprotectedDaclRecursive@SearchSettingsHelper@SearchSettings@@CAXPEAUHKEY__@@PEAU_ACL@@@Z; SearchSettings::SearchSettingsHelper::SetUnprotectedDaclRecursive(HKEY__ *,_ACL *)
0x180461eaa  nop
0x180461eab  mov     rcx, [rbp+57h+hMem]; hMem
0x180461eaf  mov     [rbp+57h+hMem], r14
0x180461eb3  test    rcx, rcx
0x180461eb6  jz      short loc_180461EBF
0x180461eb8  call    cs:__imp_LocalFree
0x180461ebe  nop
0x180461ebf  lea     rcx, [rbp+57h+var_C8]
0x180461ec3  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180461ec8  mov     ebx, r14d
0x180461ecb  lea     rcx, [rbp+57h+handle]
0x180461ecf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180461ed4  nop
0x180461ed5  lea     rcx, [rbp+57h+var_A8]; this
0x180461ed9  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180461ede  mov     eax, ebx
0x180461ee0  mov     rcx, [rbp+57h+var_28]
0x180461ee4  xor     rcx, rsp; StackCookie
0x180461ee7  call    __security_check_cookie
0x180461eec  add     rsp, 100h
0x180461ef3  pop     r14
0x180461ef5  pop     rdi
0x180461ef6  pop     rsi
0x180461ef7  pop     rbx
0x180461ef8  pop     rbp
0x180461ef9  retn
```
