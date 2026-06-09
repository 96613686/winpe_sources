# WamObjectStoreManagerImplementation::GetEntry(IUnknown *,HSTRING__ *,Windows::Internal::Security::Authentication::Web::IWamObjectStore * *)

- ea: `0x180008730`
- end: `0x180008e66`
- name: `?GetEntry@WamObjectStoreManagerImplementation@@QEAAJPEAUIUnknown@@PEAUHSTRING__@@PEAPEAUIWamObjectStore@Web@Authentication@Security@Internal@Windows@@@Z`
- size: `1846`
- prototype: `int(WamObjectStoreManagerImplementation *__hidden this, struct IUnknown *, HSTRING, struct Windows::Internal::Security::Authentication::Web::IWamObjectStore **)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800086c0`

## callees

- `0x18000730c`
- `0x180007350`
- `0x180008030`
- `0x180008730`
- `0x180008e6c`
- `0x180009ab0`
- `0x180009e40`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001ffdc`
- `0x180041824`
- `0x180055498`
- `0x18005d1fc`
- `0x18008e690`
- `0x18009a6fc`
- `0x18009a8a0`
- `0x1800d6ce0`
- `0x1800d7150`
- `0x18011b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000890d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000890d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008835`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008835`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008941`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008a77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008941`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008a77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008aef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008aef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800089f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008799`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c6a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008aaa`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008aaa`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008a40`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008a40`

## string_xrefs

- `0x180008a67`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008abf`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008b26`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008ba5`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008bcd`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008d67`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008db0`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008dff`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WamObjectStoreManagerImplementation::GetEntry(
        WamObjectStoreManagerImplementation *this,
        struct IUnknown *a2,
        HSTRING a3,
        struct Windows::Internal::Security::Authentication::Web::IWamObjectStore **a4)
{
  _lambda_570d6c12d7f446ca7443779868589c96_ *v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v11; // r15
  int UniqueUserCollection; // eax
  int v13; // ecx
  int v14; // ebx
  int Entry; // eax
  char v16; // r14
  HRESULT v18; // eax
  __int64 v19; // rdx
  signed int LastError; // eax
  __int64 v21; // r8
  int v22; // eax
  int v23; // ecx
  PSECURITY_DESCRIPTOR v24; // rcx
  __int64 v25; // rdi
  PSECURITY_DESCRIPTOR v26; // rax
  __int64 v27; // rcx
  __int64 *v28; // rax
  __int64 v29; // rbx
  PSECURITY_DESCRIPTOR v30; // rcx
  int ObjectStoreSDForCaller; // eax
  unsigned int v32; // edi
  int v33; // eax
  __int64 v34; // r14
  int v35; // eax
  int PrivilegeSet; // [rsp+20h] [rbp-E0h]
  int PrivilegeSeta; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD GrantedAccess[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v41[16]; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  WINBOOL AccessStatus[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v45[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _PRIVILEGE_SET v46; // [rsp+90h] [rbp-70h] BYREF
  __int16 v47; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-48h]
  __int64 v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C8h] [rbp-38h]
  HSTRING v51[2]; // [rsp+D0h] [rbp-30h]
  HSTRING string[2]; // [rsp+E0h] [rbp-20h]
  HSTRING v53[28]; // [rsp+F0h] [rbp-10h]
  HANDLE v54[2]; // [rsp+1D0h] [rbp+D0h]
  HANDLE hObject[2]; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v38 = 0;
  v7 = _lambda_570d6c12d7f446ca7443779868589c96_::_lambda_570d6c12d7f446ca7443779868589c96_(
         (_lambda_570d6c12d7f446ca7443779868589c96_ *)v45,
         &v38);
  wil::ScopeExit<_lambda_3876c2633569fbadd92ad93bfc26ac25_>(v41, v7);
  if ( !a2 || WindowsIsStringEmpty(a3) || !a4 )
  {
    wil::details::ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___::_ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___(v41);
    return 2147942487LL;
  }
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  *(_OWORD *)v51 = 0;
  *(_OWORD *)string = 0;
  *(_OWORD *)v53 = 0;
  *(_OWORD *)v54 = 0;
  *(_OWORD *)hObject = 0;
  v43 = 0;
  v8 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
         (Windows::Internal::Security::Authentication::Web::CallerContext *)&v47,
         a2,
         0,
         0);
  v9 = v8;
  v38 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)(unsigned int)v8,
      PrivilegeSet);
    Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v47);
    wil::details::ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___::_ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___(v41);
    return v9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
  v45[0] = StringRawBuffer;
  v11 = WindowsGetStringRawBuffer(a3, 0);
  AcquireSRWLockShared(&g_ObjectStoreManagerImpl);
  *(_QWORD *)PrivilegeSetLength = &g_ObjectStoreManagerImpl;
  UniqueUserCollection = WamObjectStoreManagerImplementation::GetUniqueUserCollection(
                           &g_ObjectStoreManagerImpl,
                           &v47,
                           0,
                           &v43);
  v14 = UniqueUserCollection;
  v38 = UniqueUserCollection;
  if ( UniqueUserCollection < 0 )
  {
    v19 = 429;
    goto LABEL_41;
  }
  if ( UniqueUserCollection )
    goto LABEL_16;
  pSecurityDescriptor = 0;
  Entry = WamObjectStoreManagerImplementation::InternalGetEntry(
            v13,
            v43,
            (_DWORD)v11,
            (unsigned int)&pSecurityDescriptor,
            (__int64)a4);
  v14 = Entry;
  v38 = Entry;
  if ( Entry < 0 )
  {
    v19 = 438;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)(unsigned int)v14,
      PrivilegeSet);
    ReleaseSRWLockShared(&g_ObjectStoreManagerImpl);
LABEL_42:
    Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v47);
LABEL_37:
    wil::details::ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___::_ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___(v41);
    return (unsigned int)v14;
  }
  if ( Entry )
    goto LABEL_16;
  GrantedAccess[0] = 0;
  AccessStatus[0] = 0;
  memset(&v46, 0, sizeof(v46));
  PrivilegeSetLength[0] = 20;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    v16 = 0;
  }
  else
  {
    v18 = CoImpersonateClient();
    v14 = v18;
    if ( v18 < 0 )
    {
      v38 = v18;
      goto LABEL_71;
    }
    v16 = 1;
  }
  if ( AccessCheck(
         pSecurityDescriptor,
         (HANDLE)0xFFFFFFFFFFFFFFFALL,
         3u,
         &gWAMStoreGenericMapping,
         &v46,
         PrivilegeSetLength,
         GrantedAccess,
         AccessStatus) )
  {
    v14 = -2147024891;
    if ( AccessStatus[0] )
      v14 = 0;
    if ( !v16 )
      goto LABEL_15;
LABEL_46:
    CoRevertToSelf();
    goto LABEL_15;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  if ( v16 )
    goto LABEL_46;
LABEL_15:
  v38 = v14;
  if ( v14 < 0 )
  {
LABEL_71:
    v19 = 443;
    goto LABEL_41;
  }
LABEL_16:
  ReleaseSRWLockShared(&g_ObjectStoreManagerImpl);
  v14 = v38;
  if ( v38 != 1 )
  {
LABEL_17:
    if ( (unsigned __int64)hObject[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[1]);
    if ( hObject[0] )
      CloseHandle(hObject[0]);
    if ( (unsigned __int64)v54[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v54[1]);
    if ( (unsigned __int64)v54[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v54[0]);
    if ( v53[1] )
      WindowsDeleteString(v53[1]);
    if ( v53[0] )
      WindowsDeleteString(v53[0]);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      WindowsDeleteString(string[0]);
    if ( v51[1] )
      WindowsDeleteString(v51[1]);
    if ( v51[0] )
      WindowsDeleteString(v51[0]);
    goto LABEL_37;
  }
  AcquireSRWLockExclusive(&g_ObjectStoreManagerImpl);
  *(_QWORD *)AccessStatus = &g_ObjectStoreManagerImpl;
  LOBYTE(v21) = 1;
  v22 = WamObjectStoreManagerImplementation::GetUniqueUserCollection(&g_ObjectStoreManagerImpl, &v47, v21, &v43);
  v14 = v22;
  v38 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)(unsigned int)v22,
      PrivilegeSet);
    ReleaseSRWLockExclusive(&g_ObjectStoreManagerImpl);
    goto LABEL_42;
  }
  v34 = v43;
  v35 = WamObjectStoreManagerImplementation::InternalGetEntry(v23, v43, (_DWORD)v11, 0, (__int64)a4);
  v14 = v35;
  v38 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)(unsigned int)v35,
      PrivilegeSeta);
    ReleaseSRWLockExclusive(&g_ObjectStoreManagerImpl);
    goto LABEL_42;
  }
  if ( v35 != 1 )
    goto LABEL_63;
  if ( *(_QWORD *)(v34 + 16) == 2 )
  {
    v38 = -2147023604;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)0x8007050CLL,
      PrivilegeSeta);
    ReleaseSRWLockExclusive(&g_ObjectStoreManagerImpl);
    Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v47);
    wil::details::ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___::_ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___(v41);
    return 2147943692LL;
  }
  *(_QWORD *)GrantedAccess = 0;
  v28 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::Security::Authentication::Web::CWamObjectStore,unsigned short const * &>(
                     &pSecurityDescriptor,
                     v45);
  v29 = *v28;
  *v28 = 0;
  v45[0] = 0;
  *(_QWORD *)GrantedAccess = v29;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v45);
  v30 = pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    pSecurityDescriptor = 0;
    (*(void (__fastcall **)(PSECURITY_DESCRIPTOR))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( v29 )
  {
    *(_QWORD *)PrivilegeSetLength = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      PrivilegeSetLength,
      0);
    ObjectStoreSDForCaller = CreateObjectStoreSDForCaller(StringRawBuffer, PrivilegeSetLength);
    v32 = ObjectStoreSDForCaller;
    v38 = ObjectStoreSDForCaller;
    if ( ObjectStoreSDForCaller < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DD,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
        (const char *)(unsigned int)ObjectStoreSDForCaller,
        PrivilegeSeta);
      v24 = *(PSECURITY_DESCRIPTOR *)PrivilegeSetLength;
      if ( !*(_QWORD *)PrivilegeSetLength )
        goto LABEL_53;
      goto LABEL_52;
    }
    v33 = WamStoreAccessCheckForCaller(*(PSECURITY_DESCRIPTOR *)PrivilegeSetLength, 3u);
    v32 = v33;
    v38 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
        (const char *)(unsigned int)v33,
        PrivilegeSeta);
      v24 = *(PSECURITY_DESCRIPTOR *)PrivilegeSetLength;
      if ( !*(_QWORD *)PrivilegeSetLength )
        goto LABEL_53;
LABEL_52:
      LocalFree(v24);
LABEL_53:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(GrantedAccess);
      ReleaseSRWLockExclusive(&g_ObjectStoreManagerImpl);
      Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v47);
      wil::details::ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___::_ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___(v41);
      return v32;
    }
    std::wstring::wstring(&v46, v11);
    v25 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,WamObjectStoreManagerEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,WamObjectStoreManagerEntry>>,0>>::_Try_emplace<std::wstring,>(
                       v34,
                       v45,
                       &v46);
    std::wstring::_Tidy_deallocate(&v46);
    v26 = *(PSECURITY_DESCRIPTOR *)PrivilegeSetLength;
    *(_QWORD *)PrivilegeSetLength = 0;
    *(_QWORD *)(v25 + 48) = v26;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
    *(_QWORD *)(v25 + 56) = v29;
    v38 = 0;
    v27 = *(_QWORD *)(v25 + 56);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
    *a4 = *(struct Windows::Internal::Security::Authentication::Web::IWamObjectStore **)(v25 + 56);
    v38 = 0;
    if ( *(_QWORD *)PrivilegeSetLength )
      LocalFree(*(HLOCAL *)PrivilegeSetLength);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(GrantedAccess);
LABEL_63:
    ReleaseSRWLockExclusive(&g_ObjectStoreManagerImpl);
    v14 = v38;
    goto LABEL_17;
  }
  v38 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E9,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
    (const char *)0x8007000ELL,
    PrivilegeSeta);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(GrantedAccess);
  ReleaseSRWLockExclusive(&g_ObjectStoreManagerImpl);
  Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v47);
  wil::details::ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___::_ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___(v41);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180008730  mov     [rsp-8+arg_0], rbx
0x180008735  push    rbp
0x180008736  push    rsi
0x180008737  push    rdi
0x180008738  push    r12
0x18000873a  push    r13
0x18000873c  push    r14
0x18000873e  push    r15
0x180008740  lea     rbp, [rsp-100h]
0x180008748  sub     rsp, 200h
0x18000874f  mov     rax, cs:__security_cookie
0x180008756  xor     rax, rsp
0x180008759  mov     [rbp+130h+var_40], rax
0x180008760  mov     rsi, r9
0x180008763  mov     rbx, r8
0x180008766  mov     rdi, rdx
0x180008769  xor     r12d, r12d
0x18000876c  mov     [rsp+230h+var_1F0], r12d
0x180008771  lea     rdx, [rsp+230h+var_1F0]; int *
0x180008776  lea     rcx, [rbp+130h+var_1B0]; this
0x18000877a  call    ??0_lambda_570d6c12d7f446ca7443779868589c96_@@QEAA@AEAJ@Z; _lambda_570d6c12d7f446ca7443779868589c96_::_lambda_570d6c12d7f446ca7443779868589c96_(long &)
0x18000877f  mov     rdx, rax
0x180008782  lea     rcx, [rsp+230h+var_1D8]
0x180008787  call    ??$ScopeExit@V_lambda_3876c2633569fbadd92ad93bfc26ac25_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_3876c2633569fbadd92ad93bfc26ac25_@@@details@0@$$QEAV_lambda_3876c2633569fbadd92ad93bfc26ac25_@@@Z; wil::ScopeExit<_lambda_3876c2633569fbadd92ad93bfc26ac25_>(_lambda_3876c2633569fbadd92ad93bfc26ac25_ &&)
0x18000878c  nop
0x18000878d  test    rdi, rdi
0x180008790  jz      loc_180008B46
0x180008796  mov     rcx, rbx; string
0x180008799  call    cs:__imp_WindowsIsStringEmpty
0x18000879f  test    eax, eax
0x1800087a1  jnz     loc_180008B46
0x1800087a7  test    rsi, rsi
0x1800087aa  jz      loc_180008B46
0x1800087b0  mov     [rbp+130h+var_180], ax
0x1800087b4  mov     [rbp+130h+var_178], r12
0x1800087b8  mov     [rbp+130h+var_170], r12
0x1800087bc  mov     [rbp+130h+var_168], r12d
0x1800087c0  xorps   xmm0, xmm0
0x1800087c3  movdqa  xmmword ptr [rbp+130h+var_160], xmm0
0x1800087c8  xorps   xmm1, xmm1
0x1800087cb  movdqa  xmmword ptr [rbp+130h+string], xmm1
0x1800087d0  movdqa  xmmword ptr [rbp+130h+var_140], xmm0
0x1800087d5  movdqa  xmmword ptr [rbp+130h+var_60], xmm1
0x1800087dd  movdqa  xmmword ptr [rbp+130h+hObject], xmm0
0x1800087e5  mov     [rsp+230h+var_1C0], r12
0x1800087ea  xor     r9d, r9d; bool
0x1800087ed  xor     r8d, r8d; unsigned __int64
0x1800087f0  mov     rdx, rdi; struct IUnknown *
0x1800087f3  lea     rcx, [rbp+130h+var_180]; this
0x1800087f7  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800087fc  mov     edi, eax
0x1800087fe  mov     [rsp+230h+var_1F0], eax
0x180008802  test    eax, eax
0x180008804  js      loc_180008AB5
0x18000880a  xor     edx, edx; length
0x18000880c  mov     rcx, [rbp+130h+string]; string
0x180008810  call    cs:__imp_WindowsGetStringRawBuffer
0x180008816  mov     rdi, rax
0x180008819  mov     [rbp+130h+var_1B0], rax
0x18000881d  xor     edx, edx; length
0x18000881f  mov     rcx, rbx; string
0x180008822  call    cs:__imp_WindowsGetStringRawBuffer
0x180008828  mov     r15, rax
0x18000882b  lea     r13, ?g_ObjectStoreManagerImpl@@3UWamObjectStoreManagerImplementation@@A; WamObjectStoreManagerImplementation g_ObjectStoreManagerImpl
0x180008832  mov     rcx, r13; SRWLock
0x180008835  call    cs:__imp_AcquireSRWLockShared
0x18000883b  mov     qword ptr [rsp+230h+var_1E8], r13
0x180008840  lea     r9, [rsp+230h+var_1C0]
0x180008845  xor     r8d, r8d
0x180008848  lea     rdx, [rbp+130h+var_180]
0x18000884c  mov     rcx, r13
0x18000884f  call    ?GetUniqueUserCollection@WamObjectStoreManagerImplementation@@AEAAJAEAVCallerContext@Web@Authentication@Security@Internal@Windows@@_NPEAPEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@@std@@@2@@std@@@Z; WamObjectStoreManagerImplementation::GetUniqueUserCollection(Windows::Internal::Security::Authentication::Web::CallerContext &,bool,std::unordered_map<std::wstring,WamObjectStoreManagerEntry> * *)
0x180008854  mov     ebx, eax
0x180008856  mov     [rsp+230h+var_1F0], eax
0x18000885a  test    eax, eax
0x18000885c  js      loc_180008B5A
0x180008862  test    eax, eax
0x180008864  jnz     loc_18000893E
0x18000886a  mov     [rsp+230h+pSecurityDescriptor], r12
0x18000886f  mov     [rsp+230h+PrivilegeSet], rsi; int
0x180008874  lea     r9, [rsp+230h+pSecurityDescriptor]
0x180008879  mov     r8, r15
0x18000887c  mov     rdx, [rsp+230h+var_1C0]
0x180008881  call    ?InternalGetEntry@WamObjectStoreManagerImplementation@@AEAAJPEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@@std@@@2@@std@@PEBGPEAPEAXPEAPEAUIWamObjectStore@Web@Authentication@Security@Internal@Windows@@@Z; WamObjectStoreManagerImplementation::InternalGetEntry(std::unordered_map<std::wstring,WamObjectStoreManagerEntry> *,ushort const *,void * *,Windows::Internal::Security::Authentication::Web::IWamObjectStore * *)
0x180008886  mov     ebx, eax
0x180008888  mov     [rsp+230h+var_1F0], eax
0x18000888c  test    eax, eax
0x18000888e  js      loc_180008A58
0x180008894  test    eax, eax
0x180008896  jnz     loc_18000893E
0x18000889c  mov     [rsp+230h+var_1E0], r12d
0x1800088a1  mov     [rsp+230h+var_1B8], r12d
0x1800088a6  xorps   xmm0, xmm0
0x1800088a9  xor     eax, eax
0x1800088ab  movups  xmmword ptr [rbp+130h+var_1A0.PrivilegeCount], xmm0
0x1800088af  mov     [rbp+130h+var_1A0.Privilege.Attributes], eax
0x1800088b2  mov     [rsp+230h+var_1E8], 14h
0x1800088ba  mov     eax, gs:179Ch
0x1800088c2  test    eax, eax
0x1800088c4  jz      loc_180008A40
0x1800088ca  xor     r14b, r14b
0x1800088cd  lea     rax, [rsp+230h+var_1B8]
0x1800088d2  mov     [rsp+230h+AccessStatus], rax; AccessStatus
0x1800088d7  lea     rax, [rsp+230h+var_1E0]
0x1800088dc  mov     [rsp+230h+GrantedAccess], rax; GrantedAccess
0x1800088e1  lea     rax, [rsp+230h+var_1E8]
0x1800088e6  mov     [rsp+230h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800088eb  lea     rax, [rbp+130h+var_1A0]
0x1800088ef  mov     [rsp+230h+PrivilegeSet], rax; int
0x1800088f4  lea     r9, ?gWAMStoreGenericMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x1800088fb  mov     rdx, 0FFFFFFFFFFFFFFFAh; ClientToken
0x180008902  mov     r8d, 3; DesiredAccess
0x180008908  mov     rcx, [rsp+230h+pSecurityDescriptor]; pSecurityDescriptor
0x18000890d  call    cs:__imp_AccessCheck
0x180008913  test    eax, eax
0x180008915  jz      loc_180008A8C
0x18000891b  mov     ebx, 80070005h
0x180008920  cmp     [rsp+230h+var_1B8], 0
0x180008925  cmovnz  ebx, r12d
0x180008929  test    r14b, r14b
0x18000892c  jnz     loc_180008AAA
0x180008932  mov     [rsp+230h+var_1F0], ebx
0x180008936  test    ebx, ebx
0x180008938  js      loc_180008D31
0x18000893e  mov     rcx, r13; SRWLock
0x180008941  call    cs:__imp_ReleaseSRWLockShared
0x180008947  mov     ebx, [rsp+230h+var_1F0]
0x18000894b  cmp     ebx, 1
0x18000894e  jz      loc_180008AEC
0x180008954  mov     rcx, [rbp+130h+hObject+8]; hObject
0x18000895b  lea     rax, [rcx-1]
0x18000895f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008963  jbe     loc_180008E44
0x180008969  mov     rcx, [rbp+130h+hObject]; hObject
0x180008970  test    rcx, rcx
0x180008973  jnz     loc_180008A34
0x180008979  mov     rcx, [rbp+130h+var_60+8]; hObject
0x180008980  lea     rax, [rcx-1]
0x180008984  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008988  jbe     loc_180008E4F
0x18000898e  mov     rcx, [rbp+130h+var_60]; hObject
0x180008995  lea     rax, [rcx-1]
0x180008999  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000899d  jbe     loc_180008E5A
0x1800089a3  mov     rcx, [rbp+130h+var_140+8]; string
0x1800089a7  test    rcx, rcx
0x1800089aa  jz      short loc_1800089B2
0x1800089ac  call    cs:__imp_WindowsDeleteString
0x1800089b2  mov     rcx, [rbp+130h+var_140]; string
0x1800089b6  test    rcx, rcx
0x1800089b9  jz      short loc_1800089C1
0x1800089bb  call    cs:__imp_WindowsDeleteString
0x1800089c1  mov     rcx, [rbp+130h+string+8]; string
0x1800089c5  test    rcx, rcx
0x1800089c8  jz      short loc_1800089D0
0x1800089ca  call    cs:__imp_WindowsDeleteString
0x1800089d0  mov     rcx, [rbp+130h+string]; string
0x1800089d4  test    rcx, rcx
0x1800089d7  jz      short loc_1800089DF
0x1800089d9  call    cs:__imp_WindowsDeleteString
0x1800089df  mov     rcx, [rbp+130h+var_160+8]; string
0x1800089e3  test    rcx, rcx
0x1800089e6  jz      short loc_1800089EE
0x1800089e8  call    cs:__imp_WindowsDeleteString
0x1800089ee  mov     rcx, [rbp+130h+var_160]; string
0x1800089f2  test    rcx, rcx
0x1800089f5  jz      short loc_1800089FE
0x1800089f7  call    cs:__imp_WindowsDeleteString
0x1800089fd  nop
0x1800089fe  lea     rcx, [rsp+230h+var_1D8]
0x180008a03  call    wil__details__ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01______ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___
0x180008a08  mov     eax, ebx
0x180008a0a  mov     rcx, [rbp+130h+var_40]
0x180008a11  xor     rcx, rsp; StackCookie
0x180008a14  call    __security_check_cookie
0x180008a19  mov     rbx, [rsp+230h+arg_0]
0x180008a21  add     rsp, 200h
0x180008a28  pop     r15
0x180008a2a  pop     r14
0x180008a2c  pop     r13
0x180008a2e  pop     r12
0x180008a30  pop     rdi
0x180008a31  pop     rsi
0x180008a32  pop     rbp
0x180008a33  retn
0x180008a34  call    cs:__imp_CloseHandle
0x180008a3a  nop
0x180008a3b  jmp     loc_180008979
0x180008a40  call    cs:__imp_CoImpersonateClient
0x180008a46  mov     ebx, eax
0x180008a48  test    eax, eax
0x180008a4a  js      loc_180008D2D
0x180008a50  mov     r14b, 1
0x180008a53  jmp     loc_1800088CD
0x180008a58  mov     edx, 1B6h; void *
0x180008a5d  mov     rcx, [rbp+138h]; this
0x180008a64  mov     r9d, ebx; char *
0x180008a67  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180008a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a73  nop
0x180008a74  mov     rcx, r13; SRWLock
0x180008a77  call    cs:__imp_ReleaseSRWLockShared
0x180008a7d  nop
0x180008a7e  lea     rcx, [rbp+130h+var_180]; this
0x180008a82  call    ??1CallerContext@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(void)
0x180008a87  jmp     loc_1800089FE
0x180008a8c  call    cs:__imp_GetLastError
0x180008a92  mov     ebx, eax
0x180008a94  test    eax, eax
0x180008a96  jle     short loc_180008AA1
0x180008a98  movzx   ebx, ax
0x180008a9b  or      ebx, 80070000h
0x180008aa1  test    r14b, r14b
0x180008aa4  jz      loc_180008932
0x180008aaa  call    cs:__imp_CoRevertToSelf
0x180008ab0  jmp     loc_180008932
0x180008ab5  mov     rcx, [rbp+138h]; this
0x180008abc  mov     r9d, edi; char *
0x180008abf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180008ac6  mov     edx, 19Eh; void *
0x180008acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ad0  nop
0x180008ad1  lea     rcx, [rbp+130h+var_180]; this
0x180008ad5  call    ??1CallerContext@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(void)
0x180008ada  nop
0x180008adb  lea     rcx, [rsp+230h+var_1D8]
0x180008ae0  call    wil__details__ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01______ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___
0x180008ae5  mov     eax, edi
0x180008ae7  jmp     loc_180008A0A
0x180008aec  mov     rcx, r13; SRWLock
0x180008aef  call    cs:__imp_AcquireSRWLockExclusive
0x180008af5  mov     qword ptr [rsp+230h+var_1B8], r13
0x180008afa  lea     r9, [rsp+230h+var_1C0]
0x180008aff  mov     r8b, 1
0x180008b02  lea     rdx, [rbp+130h+var_180]
0x180008b06  mov     rcx, r13
0x180008b09  call    ?GetUniqueUserCollection@WamObjectStoreManagerImplementation@@AEAAJAEAVCallerContext@Web@Authentication@Security@Internal@Windows@@_NPEAPEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@@std@@@2@@std@@@Z; WamObjectStoreManagerImplementation::GetUniqueUserCollection(Windows::Internal::Security::Authentication::Web::CallerContext &,bool,std::unordered_map<std::wstring,WamObjectStoreManagerEntry> * *)
0x180008b0e  mov     ebx, eax
0x180008b10  mov     [rsp+230h+var_1F0], eax
0x180008b14  test    eax, eax
0x180008b16  jns     loc_180008D3B
0x180008b1c  mov     rcx, [rbp+138h]; this
0x180008b23  mov     r9d, eax; char *
0x180008b26  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180008b2d  mov     edx, 1CCh; void *
0x180008b32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b37  nop
0x180008b38  mov     rcx, r13; SRWLock
0x180008b3b  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b41  jmp     loc_180008A7E
0x180008b46  lea     rcx, [rsp+230h+var_1D8]
0x180008b4b  call    wil__details__ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01______ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___
0x180008b50  mov     eax, 80070057h
0x180008b55  jmp     loc_180008A0A
0x180008b5a  mov     edx, 1ADh
0x180008b5f  jmp     loc_180008A5D
0x180008b64  call    cs:__imp_LocalFree
0x180008b6a  nop
0x180008b6b  lea     rcx, [rsp+230h+var_1E0]
0x180008b70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008b75  nop
0x180008b76  mov     rcx, r13; SRWLock
0x180008b79  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b7f  nop
0x180008b80  lea     rcx, [rbp+130h+var_180]; this
0x180008b84  call    ??1CallerContext@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(void)
0x180008b89  nop
0x180008b8a  lea     rcx, [rsp+230h+var_1D8]
0x180008b8f  call    wil__details__ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01______ScopeExitFn__lambda_4ff1959cb998b463f12c99642f4eab01___
0x180008b94  mov     eax, edi
0x180008b96  jmp     loc_180008A0A
0x180008b9b  mov     rcx, [rbp+138h]; this
0x180008ba2  mov     r9d, edi; char *
0x180008ba5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180008bac  mov     edx, 1DDh; void *
0x180008bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bb6  nop
0x180008bb7  mov     rcx, qword ptr [rsp+230h+var_1E8]; hMem
0x180008bbc  test    rcx, rcx
0x180008bbf  jz      short loc_180008B6B
0x180008bc1  jmp     short loc_180008B64
0x180008bc3  mov     rcx, [rbp+138h]; this
0x180008bca  mov     r9d, edi; char *
0x180008bcd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180008bd4  mov     edx, 1E0h; void *
0x180008bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bde  nop
0x180008bdf  mov     rcx, qword ptr [rsp+230h+var_1E8]
0x180008be4  test    rcx, rcx
0x180008be7  jz      short loc_180008B6B
0x180008be9  jmp     loc_180008B64
0x180008bee  mov     rdx, r15
0x180008bf1  lea     rcx, [rbp+130h+var_1A0]
0x180008bf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008bfa  nop
0x180008bfb  lea     r8, [rbp+130h+var_1A0]
0x180008bff  lea     rdx, [rbp+130h+var_1B0]
0x180008c03  mov     rcx, r14
0x180008c06  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectStoreManagerEntry@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,WamObjectStoreManagerEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,WamObjectStoreManagerEntry>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x180008c0b  mov     rdi, [rax]
  ... truncated ...
```
