# SearchSettings::SearchSettingsHelper::EnsureKeyPathAndSetSecurityDescriptor(wchar_t const *,wchar_t const *)

- ea: `0x180461fd4`
- end: `0x18046236a`
- name: `?EnsureKeyPathAndSetSecurityDescriptor@SearchSettingsHelper@SearchSettings@@SAJPEB_W0@Z`
- size: `918`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
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
- `0x1800e3660`
- `0x18015cb00`
- `0x180461aac`
- `0x180461b90`
- `0x180461fd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1804620bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1804620bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18046212b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18046212b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804621b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804622be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046230c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046232b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804621b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804622be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046230c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046232b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180462176`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180462176`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1804622e9`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1804622e9`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180462280`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180462280`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x1804621f0`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x1804621f0`

## string_xrefs

- `0x18046213d`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x18046218f`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x180462235`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x18046229d`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SearchSettings::SearchSettingsHelper::EnsureKeyPathAndSetSecurityDescriptor(
        const wchar_t *a1,
        const wchar_t *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  HKEY *v7; // rax
  const WCHAR *v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned __int64 Key; // r9
  const WCHAR *v12; // rdx
  __int64 v13; // rcx
  unsigned int LastError; // ebx
  BOOL v15; // ebx
  const char *v16; // r9
  HLOCAL v17; // rcx
  unsigned int SecurityInfoSafeDefault; // eax
  DWORD v19; // ebx
  const char *v20; // r9
  __int64 v21; // rdx
  HLOCAL v22; // rcx
  DWORD v23; // eax
  HLOCAL v24; // rcx
  HLOCAL v25; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  HKEY *v30; // [rsp+38h] [rbp-C8h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v32; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE handle; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR v34; // [rsp+68h] [rbp-98h] BYREF
  PACL OldAcl; // [rsp+70h] [rbp-90h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL *p_hMem; // [rsp+A8h] [rbp-58h] BYREF
  PSID Sid; // [rsp+B0h] [rbp-50h] BYREF
  char v39; // [rsp+B8h] [rbp-48h]
  _QWORD v40[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v41; // [rsp+E0h] [rbp-20h]
  _BYTE v42[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v43[32]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  std::wstring::wstring(v40);
  if ( v3 )
  {
    v4 = std::wstring::wstring(v43, v3);
    v5 = std::operator+<wchar_t>(v42, v4, L"\\");
    v6 = std::operator+<wchar_t>(&p_hMem, v5, L"Software\\Microsoft\\Windows\\CurrentVersion\\Search");
    std::wstring::operator=(v40, v6);
    std::filesystem::path::~path((std::filesystem::path *)&p_hMem);
    std::filesystem::path::~path((std::filesystem::path *)v42);
    std::filesystem::path::~path((std::filesystem::path *)v43);
    handle = 0;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
    v8 = (const WCHAR *)v40;
    if ( v41 > 7 )
      v8 = (const WCHAR *)v40[0];
    v9 = -2147483645;
  }
  else
  {
    handle = 0;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
    v8 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Search";
    v9 = -2147483647;
  }
  v10 = RegOpenKeyExW((HKEY)v9, v8, 0, 0x3001Fu, v7);
  Key = v10;
  if ( v10 - 2 <= 1 || v10 == 1168 )
  {
    v30 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
    if ( a2 )
    {
      v12 = (const WCHAR *)v40;
      if ( v41 > 7 )
        v12 = (const WCHAR *)v40[0];
      v13 = -2147483645;
    }
    else
    {
      v12 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Search";
      v13 = -2147483647;
    }
    Key = (unsigned int)RegCreateKeyExW((HKEY)v13, v12, 0, 0, 0, 0x60000u, 0, v30, 0);
  }
  if ( (_DWORD)Key )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xA3,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  (const char *)Key,
                  phkResult);
    goto LABEL_34;
  }
  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v39 = 1;
  v15 = ConvertStringSidToSidW(
          L"S-1-15-3-1024-1086922356-207614091-3724853071-841836187-4018695103-34218837-3164163255-155871754",
          &Sid);
  wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA7,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  v16);
    goto LABEL_18;
  }
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
  pListOfExplicitEntries.grfAccessPermissions = 196639;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 2;
  BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, hMem);
  v34 = 0;
  OldAcl = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v34,
    0);
  SecurityInfoSafeDefault = SecurityHelper::GetSecurityInfoSafe<SecurityHelper::GetSecurityInfoSafeDefaultLogger>(
                              handle,
                              phkResult,
                              &OldAcl,
                              lpSecurityAttributes,
                              &v34);
  if ( SecurityInfoSafeDefault )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xB1,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  (const char *)SecurityInfoSafeDefault,
                  phkResulta);
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v34);
LABEL_18:
    v17 = hMem;
    hMem = 0;
    if ( v17 )
      LocalFree(v17);
    goto LABEL_34;
  }
  v32 = 0;
  p_hMem = &v32;
  Sid = 0;
  v39 = 1;
  v19 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, (PACL *)&Sid);
  wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v19 )
  {
    v20 = (const char *)v19;
    v21 = 182;
    goto LABEL_25;
  }
  v23 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)v32, 0);
  if ( v23 )
  {
    v20 = (const char *)v23;
    v21 = 185;
LABEL_25:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v21,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  v20,
                  phkResulta);
    v22 = v32;
    v32 = 0;
    if ( v22 )
      LocalFree(v22);
    goto LABEL_22;
  }
  v24 = v32;
  v32 = 0;
  if ( v24 )
    LocalFree(v24);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v34);
  v25 = hMem;
  hMem = 0;
  if ( v25 )
    LocalFree(v25);
  LastError = 0;
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
  std::filesystem::path::~path((std::filesystem::path *)v40);
  return LastError;
}

```

## disassembly

```asm
0x180461fd4  mov     [rsp-8+arg_0], rbx
0x180461fd9  mov     [rsp-8+arg_10], rdi
0x180461fde  push    rbp
0x180461fdf  lea     rbp, [rsp-30h]
0x180461fe4  sub     rsp, 130h
0x180461feb  mov     rax, cs:__security_cookie
0x180461ff2  xor     rax, rsp
0x180461ff5  mov     [rbp+30h+var_8], rax
0x180461ff9  mov     rbx, rdx
0x180461ffc  lea     rcx, [rbp+30h+var_68]
0x180462000  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180462005  nop
0x180462006  xor     edi, edi
0x180462008  test    rdx, rdx
0x18046200b  jz      loc_180462091
0x180462011  lea     rcx, [rbp+30h+var_28]
0x180462015  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18046201a  nop
0x18046201b  lea     r8, StringValue; "\\"
0x180462022  mov     rdx, rax
0x180462025  lea     rcx, [rbp+30h+var_48]
0x180462029  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18046202e  nop
0x18046202f  lea     r8, aSoftwareMicros_50; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180462036  mov     rdx, rax
0x180462039  lea     rcx, [rbp+30h+var_88]
0x18046203d  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180462042  mov     rdx, rax
0x180462045  lea     rcx, [rbp+30h+var_68]
0x180462049  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18046204e  lea     rcx, [rbp+30h+var_88]; this
0x180462052  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180462057  nop
0x180462058  lea     rcx, [rbp+30h+var_48]; this
0x18046205c  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180462061  nop
0x180462062  lea     rcx, [rbp+30h+var_28]; this
0x180462066  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18046206b  mov     [rsp+130h+handle], rdi
0x180462070  lea     rcx, [rsp+130h+handle]
0x180462075  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18046207a  lea     rdx, [rbp+30h+var_68]
0x18046207e  cmp     [rbp+30h+var_50], 7
0x180462083  cmova   rdx, [rbp+30h+var_68]
0x180462088  mov     rcx, 0FFFFFFFF80000003h
0x18046208f  jmp     short loc_1804620AE
0x180462091  mov     [rsp+130h+handle], rdi
0x180462096  lea     rcx, [rsp+130h+handle]
0x18046209b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1804620a0  lea     rdx, aSoftwareMicros_50; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1804620a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1804620ae  mov     [rsp+130h+phkResult], rax; phkResult
0x1804620b3  mov     r9d, 3001Fh; samDesired
0x1804620b9  xor     r8d, r8d; ulOptions
0x1804620bc  call    cs:__imp_RegOpenKeyExW
0x1804620c2  mov     r9d, eax
0x1804620c5  lea     eax, [rax-2]
0x1804620c8  cmp     eax, 1
0x1804620cb  jbe     short loc_1804620D6
0x1804620cd  cmp     r9d, 490h
0x1804620d4  jnz     short loc_180462134
0x1804620d6  lea     rcx, [rsp+130h+handle]
0x1804620db  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1804620e0  mov     [rsp+130h+lpdwDisposition], rdi; lpdwDisposition
0x1804620e5  mov     [rsp+130h+var_F8], rax; phkResult
0x1804620ea  mov     [rsp+130h+lpSecurityAttributes], rdi; int
0x1804620ef  mov     [rsp+130h+samDesired], 60000h; samDesired
0x1804620f7  mov     dword ptr [rsp+130h+phkResult], edi; unsigned int
0x1804620fb  test    rbx, rbx
0x1804620fe  jz      short loc_180462117
0x180462100  lea     rdx, [rbp+30h+var_68]
0x180462104  cmp     [rbp+30h+var_50], 7
0x180462109  cmova   rdx, [rbp+30h+var_68]
0x18046210e  mov     rcx, 0FFFFFFFF80000003h
0x180462115  jmp     short loc_180462125
0x180462117  lea     rdx, aSoftwareMicros_50; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18046211e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180462125  xor     r9d, r9d; lpClass
0x180462128  xor     r8d, r8d; Reserved
0x18046212b  call    cs:__imp_RegCreateKeyExW
0x180462131  mov     r9d, eax; char *
0x180462134  test    r9d, r9d
0x180462137  jz      short loc_180462155
0x180462139  mov     rcx, [rbp+38h]; this
0x18046213d  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180462144  mov     edx, 0A3h; void *
0x180462149  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18046214e  mov     ebx, eax
0x180462150  jmp     loc_180462333
0x180462155  mov     [rsp+130h+hMem], rdi
0x18046215a  lea     rax, [rsp+130h+hMem]
0x18046215f  mov     [rbp+30h+var_88], rax
0x180462163  mov     [rbp+30h+Sid], rdi
0x180462167  mov     [rbp+30h+var_78], 1
0x18046216b  lea     rdx, [rbp+30h+Sid]; Sid
0x18046216f  lea     rcx, StringSid; "S-1-15-3-1024-1086922356-207614091-3724"...
0x180462176  call    cs:__imp_ConvertStringSidToSidW
0x18046217c  mov     ebx, eax
0x18046217e  lea     rcx, [rbp+30h+var_88]
0x180462182  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180462187  test    ebx, ebx
0x180462189  jnz     short loc_1804621C0
0x18046218b  mov     rcx, [rbp+38h]; this
0x18046218f  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180462196  mov     edx, 0A7h; void *
0x18046219b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1804621a0  mov     ebx, eax
0x1804621a2  mov     rcx, [rsp+130h+hMem]; hMem
0x1804621a7  mov     [rsp+130h+hMem], rdi
0x1804621ac  test    rcx, rcx
0x1804621af  jz      loc_180462333
0x1804621b5  call    cs:__imp_LocalFree
0x1804621bb  jmp     loc_180462333
0x1804621c0  xorps   xmm0, xmm0
0x1804621c3  movups  xmmword ptr [rsp+130h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1804621c8  movups  xmmword ptr [rbp+30h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1804621cc  movups  xmmword ptr [rbp+30h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1804621d0  mov     [rsp+130h+pListOfExplicitEntries.grfAccessPermissions], 3001Fh
0x1804621d8  mov     [rsp+130h+pListOfExplicitEntries.grfAccessMode], 1
0x1804621e0  mov     [rbp+30h+pListOfExplicitEntries.grfInheritance], 2
0x1804621e7  mov     rdx, [rsp+130h+hMem]; pSid
0x1804621ec  lea     rcx, [rbp+30h+pListOfExplicitEntries.Trustee]; pTrustee
0x1804621f0  call    cs:__imp_BuildTrusteeWithSidW
0x1804621f6  mov     [rsp+130h+var_C8], rdi
0x1804621fb  mov     [rsp+130h+OldAcl], rdi
0x180462200  xor     edx, edx
0x180462202  lea     rcx, [rsp+130h+var_C8]
0x180462207  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18046220c  lea     rax, [rsp+130h+var_C8]
0x180462211  mov     [rsp+130h+var_F8], rax; PSECURITY_DESCRIPTOR *
0x180462216  lea     rax, [rsp+130h+OldAcl]
0x18046221b  mov     qword ptr [rsp+130h+samDesired], rax; PACL *
0x180462220  mov     rcx, [rsp+130h+handle]; handle
0x180462225  call    ??$GetSecurityInfoSafe@UGetSecurityInfoSafeDefaultLogger@SecurityHelper@@@SecurityHelper@@YAKPEAXW4_SE_OBJECT_TYPE@@KPEAPEAX2PEAPEAU_ACL@@32@Z; SecurityHelper::GetSecurityInfoSafe<SecurityHelper::GetSecurityInfoSafeDefaultLogger>(void *,_SE_OBJECT_TYPE,ulong,void * *,void * *,_ACL * *,_ACL * *,void * *)
0x18046222a  test    eax, eax
0x18046222c  jz      short loc_180462257
0x18046222e  mov     rcx, [rbp+38h]; this
0x180462232  mov     r9d, eax; char *
0x180462235  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x18046223c  mov     edx, 0B1h; void *
0x180462241  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180462246  mov     ebx, eax
0x180462248  lea     rcx, [rsp+130h+var_C8]
0x18046224d  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180462252  jmp     loc_1804621A2
0x180462257  mov     [rsp+130h+var_D8], rdi
0x18046225c  lea     rax, [rsp+130h+var_D8]
0x180462261  mov     [rbp+30h+var_88], rax
0x180462265  mov     [rbp+30h+Sid], rdi
0x180462269  mov     [rbp+30h+var_78], 1
0x18046226d  lea     r9, [rbp+30h+Sid]; NewAcl
0x180462271  mov     r8, [rsp+130h+OldAcl]; OldAcl
0x180462276  lea     rdx, [rsp+130h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18046227b  mov     ecx, 1; cCountOfExplicitEntries
0x180462280  call    cs:__imp_SetEntriesInAclW
0x180462286  mov     ebx, eax
0x180462288  lea     rcx, [rbp+30h+var_88]
0x18046228c  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180462291  test    ebx, ebx
0x180462293  jz      short loc_1804622C6
0x180462295  mov     r9d, ebx; char *
0x180462298  mov     edx, 0B6h; void *
0x18046229d  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x1804622a4  mov     rcx, [rbp+38h]; this
0x1804622a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1804622ad  mov     ebx, eax
0x1804622af  mov     rcx, [rsp+130h+var_D8]; hMem
0x1804622b4  mov     [rsp+130h+var_D8], rdi
0x1804622b9  test    rcx, rcx
0x1804622bc  jz      short loc_180462248
0x1804622be  call    cs:__imp_LocalFree
0x1804622c4  jmp     short loc_180462248
0x1804622c6  mov     rax, [rsp+130h+var_D8]
0x1804622cb  mov     [rsp+130h+lpSecurityAttributes], rdi; pSacl
0x1804622d0  mov     qword ptr [rsp+130h+samDesired], rax; pDacl
0x1804622d5  mov     [rsp+130h+phkResult], rdi; psidGroup
0x1804622da  xor     r9d, r9d; psidOwner
0x1804622dd  lea     edx, [r9+4]; ObjectType
0x1804622e1  mov     r8d, edx; SecurityInfo
0x1804622e4  mov     rcx, [rsp+130h+handle]; handle
0x1804622e9  call    cs:__imp_SetSecurityInfo
0x1804622ef  test    eax, eax
0x1804622f1  jz      short loc_1804622FD
0x1804622f3  mov     r9d, eax
0x1804622f6  mov     edx, 0B9h
0x1804622fb  jmp     short loc_18046229D
0x1804622fd  mov     rcx, [rsp+130h+var_D8]; hMem
0x180462302  mov     [rsp+130h+var_D8], rdi
0x180462307  test    rcx, rcx
0x18046230a  jz      short loc_180462312
0x18046230c  call    cs:__imp_LocalFree
0x180462312  lea     rcx, [rsp+130h+var_C8]
0x180462317  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18046231c  mov     rcx, [rsp+130h+hMem]; hMem
0x180462321  mov     [rsp+130h+hMem], rdi
0x180462326  test    rcx, rcx
0x180462329  jz      short loc_180462331
0x18046232b  call    cs:__imp_LocalFree
0x180462331  mov     ebx, edi
0x180462333  lea     rcx, [rsp+130h+handle]
0x180462338  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18046233d  nop
0x18046233e  lea     rcx, [rbp+30h+var_68]; this
0x180462342  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180462347  mov     eax, ebx
0x180462349  mov     rcx, [rbp+30h+var_8]
0x18046234d  xor     rcx, rsp; StackCookie
0x180462350  call    __security_check_cookie
0x180462355  lea     r11, [rsp+130h+var_s0]
0x18046235d  mov     rbx, [r11+10h]
0x180462361  mov     rdi, [r11+20h]
0x180462365  mov     rsp, r11
0x180462368  pop     rbp
0x180462369  retn
```
