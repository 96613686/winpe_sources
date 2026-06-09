# Windows::System::Internal::UserManagerStatics::UpdateUserPictureCache(Windows::System::IUser *)

- ea: `0x1800a44a0`
- end: `0x1800a4c64`
- name: `?UpdateUserPictureCache@UserManagerStatics@Internal@System@Windows@@UEAAJPEAUIUser@34@@Z`
- size: `1988`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, struct Windows::System::IUser *)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000acdc`
- `0x180012890`
- `0x180013278`
- `0x1800132d0`
- `0x180015250`
- `0x1800154b0`
- `0x1800179c0`
- `0x1800181f0`
- `0x180025440`
- `0x18002799c`
- `0x18003b578`
- `0x18004ba28`
- `0x18004bfa0`
- `0x18004e58c`
- `0x1800544a0`
- `0x180054544`
- `0x180063fac`
- `0x1800641b8`
- `0x180067934`
- `0x18006900c`
- `0x1800695a0`
- `0x18006c380`
- `0x1800878e8`
- `0x180087e04`
- `0x1800a44a0`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a455b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a455b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a491e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a4969`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a491e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a4969`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a495e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a49a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a495e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a49a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a494d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a494d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a4943`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a4943`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800a4870`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800a4870`

## string_xrefs

- `0x1800a4b6c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800a4b96`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800a4b19`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4b2e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4b43`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4b58`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4b81`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4bab`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4bbf`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4bd3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4be5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4c15`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4c27`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4c3c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a4c51`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::UserManagerStatics::UpdateUserPictureCache(
        Windows::System::Internal::UserManagerStatics *this,
        struct Windows::System::IUser *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 result; // rax
  __int64 (__fastcall *v6)(char *, struct Windows::System::IUser *, __int64, __int64 **); // rsi
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // ebx
  void *v15; // rax
  int v16; // edx
  int v17; // r9d
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, unsigned __int16 *, _QWORD, _QWORD); // rdi
  __int64 v21; // rcx
  int v22; // eax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rbx
  int v25; // eax
  __int64 v26; // rbx
  const char *v27; // r9
  signed int LastError; // eax
  struct Windows::Storage::Streams::IBuffer *v29; // r8
  const char *v30; // r9
  int v31; // eax
  int v32; // eax
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  unsigned int v36; // eax
  const struct _tlgProvider_t *v37; // rax
  int v38; // ebx
  wil *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  int v42; // [rsp+20h] [rbp-128h]
  _BYTE v43[4]; // [rsp+30h] [rbp-118h] BYREF
  unsigned int v44; // [rsp+34h] [rbp-114h] BYREF
  unsigned __int16 *v45; // [rsp+38h] [rbp-110h] BYREF
  char v46; // [rsp+41h] [rbp-107h]
  __int64 *v47; // [rsp+48h] [rbp-100h] BYREF
  int v48; // [rsp+50h] [rbp-F8h] BYREF
  int v49[2]; // [rsp+58h] [rbp-F0h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-E0h] BYREF
  __int64 v52; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v53; // [rsp+78h] [rbp-D0h] BYREF
  unsigned __int64 v54; // [rsp+80h] [rbp-C8h] BYREF
  Windows::System::Internal *v55; // [rsp+88h] [rbp-C0h] BYREF
  LPCWSTR lpPathName; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-98h] BYREF
  PWSTR ppszPath; // [rsp+B8h] [rbp-90h] BYREF
  __int64 v62; // [rsp+C0h] [rbp-88h] BYREF
  char *v63; // [rsp+C8h] [rbp-80h] BYREF
  Windows::System::Internal *v64; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v65; // [rsp+D8h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-68h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-50h]
  _BYTE v68[32]; // [rsp+100h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v4 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v4 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      byte_18012596B,
      0);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1321,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)0x80004003LL,
      v42);
  wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(
    &v53,
    a2);
  try
  {
    v47 = 0;
    v48 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 56LL))(v53, &v48);
    if ( v48 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      v63 = (char *)this + 104;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl'::`2'::impl) )
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v63);
      v6 = *(__int64 (__fastcall **)(char *, struct Windows::System::IUser *, __int64, __int64 **))(*((_QWORD *)this - 4)
                                                                                                  + 56LL);
      v47 = 0;
      v7 = v6((char *)this - 32, a2, 3, &v47);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1334,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v7,
          v42);
      wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(
        &v53,
        &v60);
      hToken = 0;
      (*(void (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v60 + 80LL))(v60, &hToken);
      v43[0] = 0;
      v65 = 0;
      v45 = 0;
      wil::ActivateInstance<Windows::Foundation::Collections::IPropertySet>(&v59);
      wil::com_ptr_t<Windows::Foundation::Collections::IPropertySet,wil::err_exception_policy>::query<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
        &v59,
        &v62);
      v52 = 0;
      v8 = *v47;
      v52 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 48))(v47, &v52);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1343,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v9,
          v42);
      v51 = 0;
      v10 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>,Windows::Storage::Streams::IRandomAccessStreamWithContentType *>(
              v52,
              &v51);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1346,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v10,
          v42);
      v54 = 0;
      v58 = 0;
      v11 = (**v51)(v51, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v58);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v11,
          v42);
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v58 + 48LL))(v58, &v54);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x134A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v12,
          v42);
      *(_QWORD *)v49 = 0;
      v57 = 0;
      v13 = (**v51)(v51, &GUID_905a0fe2_bc53_11df_8c49_001e4fc686da, &v57);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v13,
          v42);
      v14 = v54;
      v45 = 0;
      v15 = operator new[]((unsigned int)v54, (const struct std::nothrow_t *)std::nothrow);
      if ( v15 )
      {
        LOBYTE(v17) = v43[0];
        v18 = Windows::Storage::Streams::MakeCBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup>(
                v14,
                v16,
                (_DWORD)v15,
                v17,
                (__int64)&v45);
      }
      else
      {
        v18 = -2147024882;
      }
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x134E,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v18,
          v42);
      v19 = v57;
      v20 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v57 + 48LL);
      v21 = *(_QWORD *)v49;
      *(_QWORD *)v49 = 0;
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v22 = v20(v19, v45, (unsigned int)v54, 0);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x134F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v22,
          (int)v49);
      v23 = v45;
      v45 = 0;
      if ( v23 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v23 + 16LL))(v23);
      v24 = *(_QWORD *)v49;
      v25 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>>(*(_QWORD *)v49);
      if ( v25 >= 0 )
        v25 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v24 + 80LL))(v24, &v45);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1351,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v25,
          (int)v49);
      ppszPath = 0;
      if ( SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, hToken, &ppszPath) >= 0 )
      {
        wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short * &,unsigned short const (&)[34]>(
          &lpPathName,
          &ppszPath);
        wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &,unsigned short const (&)[15]>(
          &v55,
          &lpPathName);
        v64 = v55;
        v26 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v68, &v64) + 24);
        v67 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserPicture", 0xCu, 0xBu);
        Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(v62, v67, v26, v43);
        if ( !ImpersonateLoggedOnUser(hToken) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x135E,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            v27);
        v46 = 1;
        if ( !CreateDirectoryW(lpPathName, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v36 = wil::verify_hresult<long>((unsigned int)LastError);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1366,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
              (const char *)v36,
              (int)v49);
          }
        }
        RevertToSelf();
        if ( !ImpersonateLoggedOnUser(hToken) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x1378,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            v30);
        v46 = 1;
        v31 = Windows::System::Internal::StoreBuffer((const WCHAR *)v55, v45, v29);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x137B,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v31,
            (int)v49);
        RevertToSelf();
        v44 = 0;
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v60 + 48LL))(v60, &v44);
        v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 53) + 112LL))(
                *((_QWORD *)this + 53),
                v44,
                v59);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1381,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v32,
            (int)v49);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v55);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpPathName);
      }
      v33 = UserMgrUserModelTelemetry::Provider();
      if ( *(_DWORD *)v33 > 5u )
      {
        v44 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v33,
          (unsigned int)&unk_180125930,
          v34,
          v35,
          (__int64)&v44);
      }
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v57);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v49);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v58);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v52);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v62);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v59);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v45);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v65);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v60);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v63);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v53);
      result = 0;
    }
    else
    {
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v53);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    v37 = UserMgrUserModelTelemetry::Provider();
    v38 = (int)v37;
    v39 = (wil *)*(unsigned int *)v37;
    if ( (unsigned int)v39 > 5 )
    {
      v44 = wil::ResultFromCaughtException(v39);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v38,
        (unsigned int)word_1801258E2,
        v40,
        v41,
        (__int64)&v44);
    }
    return (unsigned int)wil::ResultFromCaughtException(v39);
  }
  return result;
}

```

## disassembly

```asm
0x1800a44a0  mov     [rsp+arg_10], rbx
0x1800a44a5  mov     [rsp+arg_18], rsi
0x1800a44aa  push    rdi
0x1800a44ab  push    r14
0x1800a44ad  push    r15
0x1800a44af  sub     rsp, 130h
0x1800a44b6  mov     rax, cs:__security_cookie
0x1800a44bd  xor     rax, rsp
0x1800a44c0  mov     [rsp+148h+var_28], rax
0x1800a44c8  mov     rdi, rdx
0x1800a44cb  mov     r14, rcx
0x1800a44ce  xor     r15d, r15d
0x1800a44d1  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800a44d6  mov     edx, [rax]
0x1800a44d8  cmp     edx, 5
0x1800a44db  jbe     short loc_1800A44EF
0x1800a44dd  xor     r8d, r8d
0x1800a44e0  lea     rdx, byte_18012596B
0x1800a44e7  mov     rcx, rax
0x1800a44ea  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a44ef  mov     rcx, [rsp+148h]; this
0x1800a44f7  test    rdi, rdi
0x1800a44fa  jz      loc_1800A4B13
0x1800a4500  mov     rdx, rdi
0x1800a4503  lea     rcx, [rsp+148h+var_D0]
0x1800a4508  call    ??0?$com_ptr_t@UISignInContext@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUISignInContext@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(Windows::System::Internal::ISignInContext *)
0x1800a450d  nop
0x1800a450e  mov     [rsp+148h+var_100], r15
0x1800a4513  mov     [rsp+148h+var_F8], r15d
0x1800a4518  mov     rcx, [rsp+148h+var_D0]
0x1800a451d  mov     rax, [rcx]
0x1800a4520  lea     rdx, [rsp+148h+var_F8]
0x1800a4525  mov     rax, [rax+38h]
0x1800a4529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a452e  cmp     [rsp+148h+var_F8], r15d
0x1800a4533  jnz     short loc_1800A4554
0x1800a4535  lea     rcx, [rsp+148h+var_100]
0x1800a453a  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x1800a453f  nop
0x1800a4540  lea     rcx, [rsp+148h+var_D0]
0x1800a4545  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x1800a454a  mov     eax, 80070057h
0x1800a454f  jmp     loc_1800A4AEA
0x1800a4554  lea     rbx, [r14+68h]
0x1800a4558  mov     rcx, rbx; lpCriticalSection
0x1800a455b  call    cs:__imp_EnterCriticalSection
0x1800a4561  mov     [rsp+148h+var_80], rbx
0x1800a4569  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserPictureFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix> `wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl(void)'::`2'::impl
0x1800a4570  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(void)
0x1800a4575  test    al, al
0x1800a4577  jz      short loc_1800A4586
0x1800a4579  lea     rcx, [rsp+148h+var_80]; this
0x1800a4581  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800a4586  mov     rax, [r14-20h]
0x1800a458a  mov     rsi, [rax+38h]
0x1800a458e  mov     rcx, [rsp+148h+var_100]
0x1800a4593  mov     [rsp+148h+var_100], r15
0x1800a4598  test    rcx, rcx
0x1800a459b  jz      short loc_1800A45AA
0x1800a459d  mov     r8, [rcx]
0x1800a45a0  mov     rax, [r8+10h]
0x1800a45a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45a9  nop
0x1800a45aa  lea     r9, [rsp+148h+var_100]
0x1800a45af  mov     r8d, 3
0x1800a45b5  mov     rdx, rdi
0x1800a45b8  lea     rcx, [r14-20h]
0x1800a45bc  mov     rax, rsi
0x1800a45bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45c4  mov     rcx, [rsp+148h]; this
0x1800a45cc  test    eax, eax
0x1800a45ce  js      loc_1800A4B2B
0x1800a45d4  lea     rdx, [rsp+148h+var_98]
0x1800a45dc  lea     rcx, [rsp+148h+var_D0]
0x1800a45e1  call    ??$query@UIUserInternal@Implementation@Internal@System@Windows@@@?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUserInternal@Implementation@Internal@System@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(void)
0x1800a45e6  nop
0x1800a45e7  mov     [rsp+148h+hToken], r15
0x1800a45ec  mov     rcx, [rsp+148h+var_98]
0x1800a45f4  mov     rax, [rcx]
0x1800a45f7  lea     rdx, [rsp+148h+hToken]
0x1800a45fc  mov     rax, [rax+50h]
0x1800a4600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4605  mov     [rsp+148h+var_118], r15b
0x1800a460a  mov     [rsp+148h+var_70], r15
0x1800a4612  mov     [rsp+148h+var_110], r15
0x1800a4617  lea     rcx, [rsp+148h+var_A0]
0x1800a461f  call    ??$ActivateInstance@UIPropertySet@Collections@Foundation@Windows@@@wil@@YA?AV?$com_ptr_t@UIPropertySet@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Foundation::Collections::IPropertySet>(ushort const *)
0x1800a4624  nop
0x1800a4625  lea     rdx, [rsp+148h+var_88]
0x1800a462d  lea     rcx, [rsp+148h+var_A0]
0x1800a4635  call    ??$query@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$com_ptr_t@UIPropertySet@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IPropertySet,wil::err_exception_policy>::query<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(void)
0x1800a463a  nop
0x1800a463b  mov     [rsp+148h+var_D8], r15
0x1800a4640  mov     rcx, [rsp+148h+var_100]
0x1800a4645  mov     rax, [rcx]
0x1800a4648  mov     [rsp+148h+var_D8], r15
0x1800a464d  lea     rdx, [rsp+148h+var_D8]
0x1800a4652  mov     rax, [rax+30h]
0x1800a4656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a465b  mov     rcx, [rsp+148h]; this
0x1800a4663  test    eax, eax
0x1800a4665  js      loc_1800A4B40
0x1800a466b  mov     [rsp+148h+var_E0], r15
0x1800a4670  lea     rdx, [rsp+148h+var_E0]
0x1800a4675  mov     rcx, [rsp+148h+var_D8]
0x1800a467a  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@23@PEAUIRandomAccessStreamWithContentType@Streams@Storage@3@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@PEAPEAUIRandomAccessStreamWithContentType@Streams@Storage@2@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>,Windows::Storage::Streams::IRandomAccessStreamWithContentType *>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *> *,Windows::Storage::Streams::IRandomAccessStreamWithContentType * *,tagCOWAIT_FLAGS,void *)
0x1800a467f  mov     rcx, [rsp+148h]; this
0x1800a4687  test    eax, eax
0x1800a4689  js      loc_1800A4B55
0x1800a468f  mov     [rsp+148h+var_C8], r15
0x1800a4697  mov     rcx, [rsp+148h+var_E0]
0x1800a469c  mov     [rsp+148h+var_A8], r15
0x1800a46a4  mov     rax, [rcx]
0x1800a46a7  lea     r8, [rsp+148h+var_A8]
0x1800a46af  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800a46b6  mov     rax, [rax]
0x1800a46b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a46be  mov     rcx, [rsp+148h]; this
0x1800a46c6  test    eax, eax
0x1800a46c8  js      loc_1800A4B69
0x1800a46ce  mov     rcx, [rsp+148h+var_A8]
0x1800a46d6  mov     rax, [rcx]
0x1800a46d9  lea     rdx, [rsp+148h+var_C8]
0x1800a46e1  mov     rax, [rax+30h]
0x1800a46e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a46ea  mov     rcx, [rsp+148h]; this
0x1800a46f2  test    eax, eax
0x1800a46f4  js      loc_1800A4B7E
0x1800a46fa  mov     qword ptr [rsp+148h+var_F0], r15
0x1800a46ff  mov     rcx, [rsp+148h+var_E0]
0x1800a4704  mov     [rsp+148h+var_B0], r15
0x1800a470c  mov     rax, [rcx]
0x1800a470f  lea     r8, [rsp+148h+var_B0]
0x1800a4717  lea     rdx, _GUID_905a0fe2_bc53_11df_8c49_001e4fc686da
0x1800a471e  mov     rax, [rax]
0x1800a4721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4726  mov     rcx, [rsp+148h]; this
0x1800a472e  test    eax, eax
0x1800a4730  js      loc_1800A4B93
0x1800a4736  mov     rcx, [rsp+148h+var_110]
0x1800a473b  mov     [rsp+148h+var_110], r15
0x1800a4740  test    rcx, rcx
0x1800a4743  jz      short loc_1800A4752
0x1800a4745  mov     rax, [rcx]
0x1800a4748  mov     rax, [rax+10h]
0x1800a474c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4751  nop
0x1800a4752  mov     ebx, dword ptr [rsp+148h+var_C8]
0x1800a4759  mov     [rsp+148h+var_110], r15
0x1800a475e  mov     ecx, ebx; unsigned __int64
0x1800a4760  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4767  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a476c  test    rax, rax
0x1800a476f  jnz     short loc_1800A4778
0x1800a4771  mov     eax, 8007000Eh
0x1800a4776  jmp     short loc_1800A4791
0x1800a4778  lea     rcx, [rsp+148h+var_110]
0x1800a477d  mov     qword ptr [rsp+148h+var_128], rcx; int
0x1800a4782  mov     r9b, [rsp+148h+var_118]
0x1800a4787  mov     r8, rax
0x1800a478a  mov     ecx, ebx
0x1800a478c  call    ??$MakeCBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@@Streams@Storage@Windows@@YAJIIPEAEVCBuffer_StandardCleanup@012@PEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup>(uint,uint,uchar *,Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::IBuffer * *)
0x1800a4791  mov     rcx, [rsp+148h]; this
0x1800a4799  test    eax, eax
0x1800a479b  js      loc_1800A4BA8
0x1800a47a1  mov     rbx, [rsp+148h+var_B0]
0x1800a47a9  mov     rax, [rbx]
0x1800a47ac  mov     rdi, [rax+30h]
0x1800a47b0  mov     rcx, qword ptr [rsp+148h+var_F0]
0x1800a47b5  mov     qword ptr [rsp+148h+var_F0], r15
0x1800a47ba  test    rcx, rcx
0x1800a47bd  jz      short loc_1800A47CC
0x1800a47bf  mov     rax, [rcx]
0x1800a47c2  mov     rax, [rax+10h]
0x1800a47c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47cb  nop
0x1800a47cc  lea     rax, [rsp+148h+var_F0]
0x1800a47d1  mov     qword ptr [rsp+148h+var_128], rax; int
0x1800a47d6  xor     r9d, r9d
0x1800a47d9  mov     r8d, dword ptr [rsp+148h+var_C8]
0x1800a47e1  mov     rdx, [rsp+148h+var_110]
0x1800a47e6  mov     rcx, rbx
0x1800a47e9  mov     rax, rdi
0x1800a47ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47f1  mov     rcx, [rsp+148h]; this
0x1800a47f9  test    eax, eax
0x1800a47fb  js      loc_1800A4BBC
0x1800a4801  mov     rcx, [rsp+148h+var_110]
0x1800a4806  mov     [rsp+148h+var_110], r15
0x1800a480b  test    rcx, rcx
0x1800a480e  jz      short loc_1800A481D
0x1800a4810  mov     rax, [rcx]
0x1800a4813  mov     rax, [rax+10h]
0x1800a4817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a481c  nop
0x1800a481d  mov     rbx, qword ptr [rsp+148h+var_F0]
0x1800a4822  mov     rcx, rbx
0x1800a4825  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)
0x1800a482a  test    eax, eax
0x1800a482c  js      short loc_1800A4842
0x1800a482e  mov     rax, [rbx]
0x1800a4831  lea     rdx, [rsp+148h+var_110]
0x1800a4836  mov     rcx, rbx
0x1800a4839  mov     rax, [rax+50h]
0x1800a483d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4842  mov     rcx, [rsp+148h]; this
0x1800a484a  test    eax, eax
0x1800a484c  js      loc_1800A4BD0
0x1800a4852  mov     [rsp+148h+ppszPath], r15
0x1800a485a  lea     r9, [rsp+148h+ppszPath]; ppszPath
0x1800a4862  mov     r8, [rsp+148h+hToken]; hToken
0x1800a4867  xor     edx, edx; dwFlags
0x1800a4869  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800a4870  call    cs:__imp_SHGetKnownFolderPath
0x1800a4876  test    eax, eax
0x1800a4878  js      loc_1800A4A14
0x1800a487e  lea     rdx, [rsp+148h+ppszPath]
0x1800a4886  lea     rcx, [rsp+148h+lpPathName]
0x1800a488e  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAPEAGAEAY0CC@$$CBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAPEAGAEAY0CC@$$CBG@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort * &,ushort const (&)[34]>(ushort * &,ushort const (&)[34])
0x1800a4893  nop
0x1800a4894  lea     rdx, [rsp+148h+lpPathName]
0x1800a489c  lea     rcx, [rsp+148h+var_C0]
0x1800a48a4  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV12@AEAY0P@$$CBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAV10@AEAY0P@$$CBG@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[15]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[15])
0x1800a48a9  nop
0x1800a48aa  mov     rax, [rsp+148h+var_C0]
0x1800a48b2  mov     [rsp+148h+var_78], rax
0x1800a48ba  lea     rdx, [rsp+148h+var_78]
0x1800a48c2  lea     rcx, [rsp+148h+var_48]
0x1800a48ca  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800a48cf  nop
0x1800a48d0  mov     rbx, [rax+18h]
0x1800a48d4  mov     [rsp+148h+var_50], r15
0x1800a48dc  mov     r9d, 0Bh; unsigned int
0x1800a48e2  lea     r8d, [r9+1]; unsigned int
0x1800a48e6  lea     rdx, aUserpicture_0; "UserPicture"
0x1800a48ed  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x1800a48f5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a48fa  nop
0x1800a48fb  lea     r9, [rsp+148h+var_118]
0x1800a4900  mov     r8, rbx
0x1800a4903  mov     rdx, [rsp+148h+var_50]
0x1800a490b  mov     rcx, [rsp+148h+var_88]
0x1800a4913  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800a4918  nop
0x1800a4919  mov     rcx, [rsp+148h+hToken]; hToken
0x1800a491e  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a4924  mov     rcx, [rsp+148h]; this
0x1800a492c  test    eax, eax
0x1800a492e  jz      loc_1800A4BE5
0x1800a4934  mov     [rsp+148h+var_107], 1
0x1800a4939  xor     edx, edx; lpSecurityAttributes
0x1800a493b  mov     rcx, [rsp+148h+lpPathName]; lpPathName
0x1800a4943  call    cs:__imp_CreateDirectoryW
0x1800a4949  test    eax, eax
0x1800a494b  jnz     short loc_1800A495E
0x1800a494d  call    cs:__imp_GetLastError
0x1800a4953  cmp     eax, 0B7h
0x1800a4958  jnz     loc_1800A4BF7
0x1800a495e  call    cs:__imp_RevertToSelf
0x1800a4964  mov     rcx, [rsp+148h+hToken]; hToken
0x1800a4969  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a496f  mov     rcx, [rsp+148h]; this
0x1800a4977  test    eax, eax
0x1800a4979  jz      loc_1800A4C27
0x1800a497f  mov     [rsp+148h+var_107], 1
0x1800a4984  mov     rdx, [rsp+148h+var_110]; unsigned __int16 *
0x1800a4989  mov     rcx, [rsp+148h+var_C0]; this
0x1800a4991  call    ?StoreBuffer@Internal@System@Windows@@YAJPEBGPEAUIBuffer@Streams@Storage@3@@Z; Windows::System::Internal::StoreBuffer(ushort const *,Windows::Storage::Streams::IBuffer *)
0x1800a4996  mov     rcx, [rsp+148h]; this
0x1800a499e  test    eax, eax
0x1800a49a0  js      loc_1800A4C39
0x1800a49a6  call    cs:__imp_RevertToSelf
0x1800a49ac  mov     [rsp+148h+var_114], r15d
0x1800a49b1  mov     rcx, [rsp+148h+var_98]
0x1800a49b9  mov     rax, [rcx]
0x1800a49bc  lea     rdx, [rsp+148h+var_114]
0x1800a49c1  mov     rax, [rax+30h]
0x1800a49c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a49ca  mov     rcx, [r14+1A8h]
0x1800a49d1  mov     rax, [rcx]
0x1800a49d4  mov     r8, [rsp+148h+var_A0]
0x1800a49dc  mov     edx, [rsp+148h+var_114]
0x1800a49e0  mov     rax, [rax+70h]
0x1800a49e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a49e9  mov     rcx, [rsp+148h]; this
0x1800a49f1  test    eax, eax
0x1800a49f3  js      loc_1800A4C4E
0x1800a49f9  lea     rcx, [rsp+148h+var_C0]
0x1800a4a01  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a4a06  nop
0x1800a4a07  lea     rcx, [rsp+148h+lpPathName]
0x1800a4a0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a4a14  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800a4a19  mov     ecx, [rax]
0x1800a4a1b  cmp     ecx, 5
0x1800a4a1e  jbe     short loc_1800A4A3F
0x1800a4a20  mov     [rsp+148h+var_114], r15d
0x1800a4a25  lea     rcx, [rsp+148h+var_114]
0x1800a4a2a  mov     qword ptr [rsp+148h+var_128], rcx
0x1800a4a2f  lea     rdx, unk_180125930
  ... truncated ...
```
