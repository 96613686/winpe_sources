# Windows::System::Internal::UserManagerStatics::AutologonWithContext(void)

- ea: `0x18008bcd0`
- end: `0x18008c3e5`
- name: `?AutologonWithContext@UserManagerStatics@Internal@System@Windows@@UEAAJXZ`
- size: `1813`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180012890`
- `0x180013300`
- `0x180014e7c`
- `0x180015250`
- `0x18002618c`
- `0x180039b08`
- `0x18003d38c`
- `0x180042170`
- `0x18004e508`
- `0x18004e75c`
- `0x180052cec`
- `0x180060524`
- `0x180062628`
- `0x18006bac8`
- `0x18006bb20`
- `0x1800822c0`
- `0x18008bcd0`
- `0x180091c50`
- `0x180091eec`
- `0x1800943b4`
- `0x1800948d0`
- `0x180094dc8`
- `0x18009a4ec`
- `0x1800d9a78`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_errno` at `0x18008bf6d`
- `msvcrt!_errno` at `0x18008bf97`
- `msvcrt!_errno` at `0x18008bf6d`
- `msvcrt!_errno` at `0x18008bf97`
- `msvcrt!wcstol` at `0x18008bf83`
- `msvcrt!wcstol` at `0x18008bf83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008bf12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008bf12`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008bdfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008bdfd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008beb3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008beb3`

## string_xrefs

- `0x18008c2e9`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c2fd`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c312`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c327`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c349`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c35e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c372`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c383`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c398`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c3ad`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008c3d2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::System::Internal::UserManagerStatics::AutologonWithContext(
        Windows::System::Internal::UserManagerStatics *this)
{
  Windows::System::Internal::UserManagerStatics *v1; // r13
  const struct _tlgProvider_t *v2; // rax
  void (__fastcall *v3)(void *, __int64 *); // rbx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, HKEY *); // rbx
  unsigned int v6; // eax
  unsigned int v7; // eax
  const char *v8; // r9
  WCHAR *v9; // rbx
  DWORD i; // r14d
  unsigned int v11; // eax
  unsigned int v12; // eax
  const wchar_t *v13; // rdi
  unsigned int v14; // r15d
  __int64 v15; // rdx
  Windows::System::Internal::UserManagerStatics *v16; // rcx
  wil *v17; // rcx
  int ContextFromCredProvCredential; // eax
  Windows::System::Internal::UserManagerStatics *v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // r8
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // r9
  CredProvUtils *v28; // rdi
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  const struct _tlgProvider_t *v32; // rax
  int v33; // r8d
  int v34; // r9d
  __int64 result; // rax
  DWORD v36; // ebx
  const struct _tlgProvider_t *v37; // rax
  __int64 v38; // r9
  int v39; // r8d
  int v40; // r9d
  unsigned int v41; // eax
  const struct _tlgProvider_t *v42; // rax
  int v43; // ebx
  wil *v44; // rcx
  int v45; // r8d
  int v46; // r9d
  int lpcSubKeys; // [rsp+20h] [rbp-168h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-168h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-168h]
  unsigned int lpcSubKeysc; // [rsp+20h] [rbp-168h]
  unsigned int lpcSubKeysd; // [rsp+20h] [rbp-168h]
  int lpcSubKeyse; // [rsp+20h] [rbp-168h]
  wchar_t *EndPtr; // [rsp+60h] [rbp-128h] BYREF
  DWORD v54; // [rsp+68h] [rbp-120h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-11Ch] BYREF
  struct Windows::System::Internal::ISignInResult *v56; // [rsp+70h] [rbp-118h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-110h] BYREF
  HKEY v58; // [rsp+80h] [rbp-108h] BYREF
  struct Windows::System::Internal::ISignInContext *v59; // [rsp+88h] [rbp-100h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-F8h] BYREF
  int v61; // [rsp+98h] [rbp-F0h] BYREF
  unsigned int v62; // [rsp+9Ch] [rbp-ECh]
  DWORD v63; // [rsp+A0h] [rbp-E8h]
  LPWSTR lpName; // [rsp+A8h] [rbp-E0h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-D8h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp-D0h] BYREF
  struct _CRED_PROV_CREDENTIAL *v67; // [rsp+C0h] [rbp-C8h] BYREF
  CredProvUtils *v68; // [rsp+C8h] [rbp-C0h] BYREF
  Windows::System::Internal::UserManagerStatics *v69; // [rsp+D0h] [rbp-B8h]
  CredProvUtils *v70[3]; // [rsp+D8h] [rbp-B0h] BYREF
  unsigned __int16 *v71[3]; // [rsp+F0h] [rbp-98h] BYREF
  HKEY *v72; // [rsp+108h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+110h] [rbp-78h] BYREF
  char v74; // [rsp+118h] [rbp-70h]
  wchar_t *String[4]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v1 = this;
  v69 = this;
  v2 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v2 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v2,
      &dword_180124B94,
      0);
  v67 = 0;
  v65 = 0;
  lpName = 0;
  hKey = 0;
  v3 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  try
  {
    v3(&Windows::System::Internal::Adapters::g_AdapterCollection, &v65);
    v4 = v65;
    v5 = *(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v65 + 24LL);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = v5(v4, 131097, &hKey);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1BA4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)v6,
        lpcSubKeysa);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1BB6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)v7,
        lpcSubKeysb);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v56,
      0,
      ++cbMaxSubKeyLen,
      v8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpName,
      &v56);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v56);
    v9 = lpName;
    if ( !lpName )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BBB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x8007000ELL,
        lpcSubKeysb);
    for ( i = 0; ; ++i )
    {
      v63 = i;
      if ( i >= cSubKeys )
        break;
      v62 = 0;
      try
      {
        cchName = cbMaxSubKeyLen;
        v11 = RegEnumKeyExW(hKey, i, v9, &cchName, 0, 0, 0, 0);
        if ( v11 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x1BCC,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)v11,
            lpcSubKeysc);
        v58 = 0;
        v72 = &v58;
        phkResult = 0;
        v74 = 1;
        v12 = RegOpenKeyExW(hKey, v9, 0, 0x20019u, &phkResult);
        if ( v12 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x1BD4,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)v12,
            lpcSubKeysd);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v72);
        v59 = 0;
        std::wstring::wstring(String, v9);
        v13 = (const wchar_t *)String;
        if ( String[3] >= (wchar_t *)8 )
          v13 = String[0];
        EndPtr = 0;
        *_errno() = 0;
        v14 = wcstol(v13, &EndPtr, 10);
        if ( v13 == EndPtr )
          std::_Xinvalid_argument("invalid stoi argument");
        if ( *_errno() == 34 )
          std::_Xout_of_range("stoi argument out of range");
        v62 = v14;
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(String, v15, 0);
        if ( Windows::System::Internal::UserManagerStatics::GetCredProvCredentialInRegistry(v16, v58, &v67) == -2147023728 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
        }
        else
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
          ContextFromCredProvCredential = Windows::System::Internal::UserManagerStatics::GetContextFromCredProvCredential(
                                            (Windows::System::Internal::UserManagerStatics *)((char *)v1 - 96),
                                            v67,
                                            v14,
                                            &v59);
          if ( ContextFromCredProvCredential < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1BE0,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
              (const char *)(unsigned int)ContextFromCredProvCredential,
              lpcSubKeysd);
          v56 = 0;
          if ( !Windows::System::Internal::UserManagerStatics::IsUserInteractive(
                  (Windows::System::Internal::UserManagerStatics *)((char *)v1 - 96),
                  v14)
            || Windows::System::Internal::UserManagerStatics::IsWarmBloodedAutologonAllowed(v19) )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
            v20 = Windows::System::Internal::UserManagerStatics::SignInHelper((__int64 **)v1 - 12, v14, v59, 0, &v56);
            if ( v20 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1BF0,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v20,
                lpcSubKeyse);
            v61 = 0;
            v21 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInResult *, int *))(*(_QWORD *)v56 + 64LL))(
                    v56,
                    &v61);
            if ( v21 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1BF3,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v21,
                lpcSubKeyse);
            if ( v61 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1BF4,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v61,
                lpcSubKeyse);
            memset(v71, 0, sizeof(v71));
            v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    v71,
                    v58,
                    v22,
                    L"Sid");
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1BFA,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v23,
                lpcSubKeyse);
            memset(v70, 0, sizeof(v70));
            v25 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    v70,
                    v58,
                    v24,
                    L"ProfileName");
            if ( v25 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1BFD,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v25,
                lpcSubKeyse);
            v28 = v70[0];
            CredProvUtils::WriteLastLoggedOnUserinfo(v70[0], v26, v71[0], v27);
            v29 = UserMgrUserModelTelemetry::Provider();
            if ( *(_DWORD *)v29 > 4u )
            {
              v54 = 0;
              LODWORD(EndPtr) = v14;
              v68 = v28;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (_DWORD)v29,
                (unsigned int)&word_180124B3E,
                v30,
                v31,
                (__int64)&v68,
                (__int64)&EndPtr,
                (__int64)&v54);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v70);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v71);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
          }
          else
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
          }
        }
      }
      catch ( ... )
      {
        v36 = wil::ResultFromCaughtException(v17);
        if ( v36 != -2136866045 )
        {
          v37 = UserMgrUserModelTelemetry::Provider();
          if ( *(_DWORD *)v37 > 2u )
          {
            if ( (unsigned __int8)tlgKeywordOn(v37, 0, v37, v38) )
            {
              LODWORD(EndPtr) = v62;
              v54 = v36;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v39,
                (unsigned int)&byte_180124AFF,
                v39,
                v40,
                (__int64)&v54,
                (__int64)&EndPtr);
            }
          }
          v41 = wil::verify_hresult<long>(v36);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1C13,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)v41,
            lpcSubKeys);
        }
        v9 = lpName;
        i = v63;
        v1 = v69;
        continue;
      }
    }
    v32 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v32 > 4u )
    {
      LODWORD(EndPtr) = 0;
      v54 = cSubKeys;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v32,
        (unsigned int)byte_180124AB1,
        v33,
        v34,
        (__int64)&v54,
        (__int64)&EndPtr);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
    result = 0;
  }
  catch ( ... )
  {
    v42 = UserMgrUserModelTelemetry::Provider();
    v43 = (int)v42;
    v44 = (wil *)*(unsigned int *)v42;
    if ( (unsigned int)v44 > 4 )
    {
      LODWORD(EndPtr) = wil::ResultFromCaughtException(v44);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v43,
        (unsigned int)byte_180124A65,
        v45,
        v46,
        (__int64)&EndPtr);
    }
    return (unsigned int)wil::ResultFromCaughtException(v44);
  }
  return result;
}

```

## disassembly

```asm
0x18008bcd0  push    rbx
0x18008bcd2  push    rsi
0x18008bcd3  push    rdi
0x18008bcd4  push    r13
0x18008bcd6  push    r14
0x18008bcd8  push    r15
0x18008bcda  sub     rsp, 158h
0x18008bce1  mov     rax, cs:__security_cookie
0x18008bce8  xor     rax, rsp
0x18008bceb  mov     [rsp+188h+var_48], rax
0x18008bcf3  mov     r13, rcx
0x18008bcf6  mov     [rsp+188h+var_B8], rcx
0x18008bcfe  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18008bd03  mov     edx, [rax]
0x18008bd05  cmp     edx, 4
0x18008bd08  jbe     short loc_18008BD1C
0x18008bd0a  xor     r8d, r8d
0x18008bd0d  lea     rdx, dword_180124B94
0x18008bd14  mov     rcx, rax
0x18008bd17  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18008bd1c  xor     esi, esi
0x18008bd1e  mov     [rsp+188h+var_C8], rsi
0x18008bd26  mov     [rsp+188h+var_D8], rsi
0x18008bd2e  mov     [rsp+188h+lpName], rsi
0x18008bd36  mov     [rsp+188h+hKey], rsi
0x18008bd3e  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18008bd45  mov     rbx, [rax+48h]
0x18008bd49  lea     rcx, [rsp+188h+var_D8]
0x18008bd51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008bd56  lea     rdx, [rsp+188h+var_D8]
0x18008bd5e  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18008bd65  mov     rax, rbx
0x18008bd68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bd6d  mov     rdi, [rsp+188h+var_D8]
0x18008bd75  mov     rax, [rdi]
0x18008bd78  mov     rbx, [rax+18h]
0x18008bd7c  xor     edx, edx
0x18008bd7e  lea     rcx, [rsp+188h+hKey]
0x18008bd86  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008bd8b  lea     r8, [rsp+188h+hKey]
0x18008bd93  mov     edx, 20019h
0x18008bd98  mov     rcx, rdi
0x18008bd9b  mov     rax, rbx
0x18008bd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bda3  mov     rcx, [rsp+188h]; this
0x18008bdab  test    eax, eax
0x18008bdad  jnz     loc_18008C2E6
0x18008bdb3  mov     [rsp+188h+cSubKeys], esi
0x18008bdb7  mov     [rsp+188h+cbMaxSubKeyLen], esi
0x18008bdbb  mov     [rsp+188h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18008bdc0  mov     [rsp+188h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18008bdc5  mov     [rsp+188h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18008bdca  mov     [rsp+188h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18008bdcf  mov     [rsp+188h+lpcValues], rsi; lpcValues
0x18008bdd4  mov     [rsp+188h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18008bdd9  lea     rax, [rsp+188h+cbMaxSubKeyLen]
0x18008bdde  mov     [rsp+188h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18008bde3  lea     rax, [rsp+188h+cSubKeys]
0x18008bde8  mov     [rsp+188h+lpcSubKeys], rax; int
0x18008bded  xor     r9d, r9d; lpReserved
0x18008bdf0  xor     r8d, r8d; lpcchClass
0x18008bdf3  xor     edx, edx; lpClass
0x18008bdf5  mov     rcx, [rsp+188h+hKey]; hKey
0x18008bdfd  call    cs:__imp_RegQueryInfoKeyW
0x18008be03  mov     rcx, [rsp+188h]; this
0x18008be0b  test    eax, eax
0x18008be0d  jnz     loc_18008C2FA
0x18008be13  mov     eax, [rsp+188h+cbMaxSubKeyLen]
0x18008be17  inc     eax
0x18008be19  mov     [rsp+188h+cbMaxSubKeyLen], eax
0x18008be1d  mov     r8d, eax
0x18008be20  xor     edx, edx
0x18008be22  lea     rcx, [rsp+188h+var_118]
0x18008be27  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18008be2c  lea     rdx, [rsp+188h+var_118]
0x18008be31  lea     rcx, [rsp+188h+lpName]
0x18008be39  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18008be3e  lea     rcx, [rsp+188h+var_118]
0x18008be43  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008be48  mov     rcx, [rsp+188h]; this
0x18008be50  mov     rbx, [rsp+188h+lpName]
0x18008be58  test    rbx, rbx
0x18008be5b  jz      loc_18008C3CC
0x18008be61  mov     r14d, esi
0x18008be64  mov     [rsp+188h+var_E8], r14d
0x18008be6c  cmp     r14d, [rsp+188h+cSubKeys]
0x18008be71  jnb     loc_18008C258
0x18008be77  mov     dword ptr [rsp+188h+var_F0+4], esi
0x18008be7e  mov     eax, [rsp+188h+cbMaxSubKeyLen]
0x18008be82  mov     [rsp+188h+cchName], eax
0x18008be89  mov     [rsp+188h+lpcValues], rsi; lpftLastWriteTime
0x18008be8e  mov     [rsp+188h+lpcbMaxClassLen], rsi; lpcchClass
0x18008be93  mov     [rsp+188h+lpcbMaxSubKeyLen], rsi; lpClass
0x18008be98  mov     [rsp+188h+lpcSubKeys], rsi; unsigned int
0x18008be9d  lea     r9, [rsp+188h+cchName]; lpcchName
0x18008bea5  mov     r8, rbx; lpName
0x18008bea8  mov     edx, r14d; dwIndex
0x18008beab  mov     rcx, [rsp+188h+hKey]; hKey
0x18008beb3  call    cs:__imp_RegEnumKeyExW
0x18008beb9  mov     rcx, [rsp+188h]; this
0x18008bec1  test    eax, eax
0x18008bec3  jnz     loc_18008C30F
0x18008bec9  mov     [rsp+188h+var_108], rsi
0x18008bed1  lea     rax, [rsp+188h+var_108]
0x18008bed9  mov     [rsp+188h+var_80], rax
0x18008bee1  mov     [rsp+188h+phkResult], rsi
0x18008bee9  mov     [rsp+188h+var_70], 1
0x18008bef1  lea     rax, [rsp+188h+phkResult]
0x18008bef9  mov     [rsp+188h+lpcSubKeys], rax; int
0x18008befe  mov     r9d, 20019h; samDesired
0x18008bf04  xor     r8d, r8d; ulOptions
0x18008bf07  mov     rdx, rbx; lpSubKey
0x18008bf0a  mov     rcx, [rsp+188h+hKey]; hKey
0x18008bf12  call    cs:__imp_RegOpenKeyExW
0x18008bf18  mov     rcx, [rsp+188h]; this
0x18008bf20  test    eax, eax
0x18008bf22  jnz     loc_18008C324
0x18008bf28  lea     rcx, [rsp+188h+var_80]
0x18008bf30  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008bf35  mov     [rsp+188h+var_100], rsi
0x18008bf3d  mov     rdx, rbx
0x18008bf40  lea     rcx, [rsp+188h+String]
0x18008bf48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18008bf4d  nop
0x18008bf4e  lea     rdi, [rsp+188h+String]
0x18008bf56  cmp     [rsp+188h+var_50], 8
0x18008bf5f  cmovnb  rdi, [rsp+188h+String]
0x18008bf68  mov     [rsp+188h+EndPtr], rsi
0x18008bf6d  call    cs:__imp__errno
0x18008bf73  mov     [rax], esi
0x18008bf75  mov     r8d, 0Ah; Radix
0x18008bf7b  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x18008bf80  mov     rcx, rdi; String
0x18008bf83  call    cs:__imp_wcstol
0x18008bf89  mov     r15d, eax
0x18008bf8c  cmp     rdi, [rsp+188h+EndPtr]
0x18008bf91  jz      loc_18008C339
0x18008bf97  call    cs:__imp__errno
0x18008bf9d  cmp     dword ptr [rax], 22h ; '"'
0x18008bfa0  jz      loc_18008C3BF
0x18008bfa6  mov     dword ptr [rsp+188h+var_F0+4], r15d
0x18008bfae  xor     r8d, r8d
0x18008bfb1  mov     dl, 1
0x18008bfb3  lea     rcx, [rsp+188h+String]
0x18008bfbb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18008bfc0  lea     r8, [rsp+188h+var_C8]; struct _CRED_PROV_CREDENTIAL **
0x18008bfc8  mov     rdx, [rsp+188h+var_108]; HKEY
0x18008bfd0  call    ?GetCredProvCredentialInRegistry@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUHKEY__@@PEAPEAU_CRED_PROV_CREDENTIAL@@@Z; Windows::System::Internal::UserManagerStatics::GetCredProvCredentialInRegistry(HKEY__ *,_CRED_PROV_CREDENTIAL * *)
0x18008bfd5  cmp     eax, 80070490h
0x18008bfda  jnz     short loc_18008BFFC
0x18008bfdc  lea     rcx, [rsp+188h+var_100]
0x18008bfe4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008bfe9  nop
0x18008bfea  lea     rcx, [rsp+188h+var_108]
0x18008bff2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bff7  jmp     loc_18008C234
0x18008bffc  lea     rdi, [r13-60h]
0x18008c000  lea     rcx, [rsp+188h+var_100]
0x18008c008  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c00d  lea     r9, [rsp+188h+var_100]; struct Windows::System::Internal::ISignInContext **
0x18008c015  mov     r8d, r15d; unsigned int
0x18008c018  mov     rdx, [rsp+188h+var_C8]; struct _CRED_PROV_CREDENTIAL *
0x18008c020  mov     rcx, rdi; this
0x18008c023  call    ?GetContextFromCredProvCredential@UserManagerStatics@Internal@System@Windows@@AEAAJPEAU_CRED_PROV_CREDENTIAL@@KPEAPEAUISignInContext@234@@Z; Windows::System::Internal::UserManagerStatics::GetContextFromCredProvCredential(_CRED_PROV_CREDENTIAL *,ulong,Windows::System::Internal::ISignInContext * *)
0x18008c028  mov     rcx, [rsp+188h]; this
0x18008c030  test    eax, eax
0x18008c032  js      loc_18008C346
0x18008c038  mov     [rsp+188h+var_118], rsi
0x18008c03d  mov     edx, r15d; unsigned int
0x18008c040  mov     rcx, rdi; this
0x18008c043  call    ?IsUserInteractive@UserManagerStatics@Internal@System@Windows@@AEAA_NI@Z; Windows::System::Internal::UserManagerStatics::IsUserInteractive(uint)
0x18008c048  test    al, al
0x18008c04a  jz      short loc_18008C080
0x18008c04c  call    ?IsWarmBloodedAutologonAllowed@UserManagerStatics@Internal@System@Windows@@AEAA_NXZ; Windows::System::Internal::UserManagerStatics::IsWarmBloodedAutologonAllowed(void)
0x18008c051  test    al, al
0x18008c053  jnz     short loc_18008C080
0x18008c055  lea     rcx, [rsp+188h+var_118]
0x18008c05a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c05f  nop
0x18008c060  lea     rcx, [rsp+188h+var_100]
0x18008c068  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c06d  nop
0x18008c06e  lea     rcx, [rsp+188h+var_108]
0x18008c076  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c07b  jmp     loc_18008C234
0x18008c080  lea     rcx, [rsp+188h+var_118]
0x18008c085  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c08a  lea     rax, [rsp+188h+var_118]
0x18008c08f  mov     [rsp+188h+lpcSubKeys], rax; int
0x18008c094  xor     r9d, r9d; void *
0x18008c097  mov     r8, [rsp+188h+var_100]; struct Windows::System::Internal::ISignInContext *
0x18008c09f  mov     edx, r15d; unsigned int
0x18008c0a2  mov     rcx, rdi; this
0x18008c0a5  call    ?SignInHelper@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUISignInResult@234@@Z; Windows::System::Internal::UserManagerStatics::SignInHelper(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::Internal::ISignInResult * *)
0x18008c0aa  mov     rcx, [rsp+188h]; this
0x18008c0b2  test    eax, eax
0x18008c0b4  js      loc_18008C35B
0x18008c0ba  mov     dword ptr [rsp+188h+var_F0], esi
0x18008c0c1  mov     rcx, [rsp+188h+var_118]
0x18008c0c6  mov     rax, [rcx]
0x18008c0c9  lea     rdx, [rsp+188h+var_F0]
0x18008c0d1  mov     rax, [rax+40h]
0x18008c0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0da  mov     rcx, [rsp+188h]; this
0x18008c0e2  test    eax, eax
0x18008c0e4  js      loc_18008C36F
0x18008c0ea  mov     r9d, dword ptr [rsp+188h+var_F0]; char *
0x18008c0f2  mov     rcx, [rsp+188h]; this
0x18008c0fa  test    r9d, r9d
0x18008c0fd  js      loc_18008C383
0x18008c103  mov     [rsp+188h+var_98], rsi
0x18008c10b  mov     [rsp+188h+var_90], rsi
0x18008c113  mov     [rsp+188h+var_88], rsi
0x18008c11b  lea     r9, aSid; "Sid"
0x18008c122  mov     rdx, [rsp+188h+var_108]
0x18008c12a  lea     rcx, [rsp+188h+var_98]
0x18008c132  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18008c137  mov     rcx, [rsp+188h]; this
0x18008c13f  test    eax, eax
0x18008c141  js      loc_18008C395
0x18008c147  mov     [rsp+188h+var_B0], rsi
0x18008c14f  mov     [rsp+188h+var_A8], rsi
0x18008c157  mov     [rsp+188h+var_A0], rsi
0x18008c15f  lea     r9, aProfilename; "ProfileName"
0x18008c166  mov     rdx, [rsp+188h+var_108]
0x18008c16e  lea     rcx, [rsp+188h+var_B0]
0x18008c176  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18008c17b  mov     rcx, [rsp+188h]; this
0x18008c183  test    eax, eax
0x18008c185  js      loc_18008C3AA
0x18008c18b  mov     r8, [rsp+188h+var_98]; unsigned __int16 *
0x18008c193  mov     rdi, [rsp+188h+var_B0]
0x18008c19b  mov     rcx, rdi; this
0x18008c19e  call    ?WriteLastLoggedOnUserinfo@CredProvUtils@@YAXPEBG00@Z; CredProvUtils::WriteLastLoggedOnUserinfo(ushort const *,ushort const *,ushort const *)
0x18008c1a3  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18008c1a8  mov     ecx, [rax]
0x18008c1aa  cmp     ecx, 4
0x18008c1ad  jbe     short loc_18008C1F1
0x18008c1af  mov     [rsp+188h+var_120], esi
0x18008c1b3  mov     dword ptr [rsp+188h+EndPtr], r15d
0x18008c1b8  mov     [rsp+188h+var_C0], rdi
0x18008c1c0  lea     rcx, [rsp+188h+var_120]
0x18008c1c5  mov     [rsp+188h+lpcbMaxClassLen], rcx
0x18008c1ca  lea     rcx, [rsp+188h+EndPtr]
0x18008c1cf  mov     [rsp+188h+lpcbMaxSubKeyLen], rcx
0x18008c1d4  lea     rcx, [rsp+188h+var_C0]
0x18008c1dc  mov     [rsp+188h+lpcSubKeys], rcx
0x18008c1e1  lea     rdx, word_180124B3E
0x18008c1e8  mov     rcx, rax
0x18008c1eb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008c1f0  nop
0x18008c1f1  lea     rcx, [rsp+188h+var_B0]
0x18008c1f9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008c1fe  nop
0x18008c1ff  lea     rcx, [rsp+188h+var_98]
0x18008c207  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008c20c  nop
0x18008c20d  lea     rcx, [rsp+188h+var_118]
0x18008c212  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c217  nop
0x18008c218  lea     rcx, [rsp+188h+var_100]
0x18008c220  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c225  nop
0x18008c226  lea     rcx, [rsp+188h+var_108]
0x18008c22e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c233  nop
0x18008c234  jmp     short loc_18008C250
0x18008c236  xor     esi, esi
0x18008c238  mov     rbx, [rsp+188h+lpName]
0x18008c240  mov     r14d, [rsp+188h+var_E8]
0x18008c248  mov     r13, [rsp+188h+var_B8]
0x18008c250  inc     r14d
0x18008c253  jmp     loc_18008BE64
0x18008c258  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18008c25d  mov     ecx, [rax]
0x18008c25f  cmp     ecx, 4
0x18008c262  jbe     short loc_18008C294
0x18008c264  mov     dword ptr [rsp+188h+EndPtr], esi
0x18008c268  mov     ecx, [rsp+188h+cSubKeys]
0x18008c26c  mov     [rsp+188h+var_120], ecx
0x18008c270  lea     rcx, [rsp+188h+EndPtr]
0x18008c275  mov     [rsp+188h+lpcbMaxSubKeyLen], rcx
0x18008c27a  lea     rcx, [rsp+188h+var_120]
0x18008c27f  mov     [rsp+188h+lpcSubKeys], rcx
0x18008c284  lea     rdx, byte_180124AB1
0x18008c28b  mov     rcx, rax
0x18008c28e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008c293  nop
0x18008c294  lea     rcx, [rsp+188h+hKey]
0x18008c29c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c2a1  nop
0x18008c2a2  lea     rcx, [rsp+188h+lpName]
0x18008c2aa  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008c2af  nop
0x18008c2b0  lea     rcx, [rsp+188h+var_D8]
0x18008c2b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c2bd  xor     eax, eax
0x18008c2bf  jmp     short loc_18008C2C5
0x18008c2c1  mov     eax, dword ptr [rsp+188h+EndPtr]
0x18008c2c5  mov     rcx, [rsp+188h+var_48]
  ... truncated ...
```
