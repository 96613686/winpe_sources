# CKnownFoldersStaticsInProc::GetPackageInstalledLocation(uint,int,Windows::Storage::IStorageFolder * *)

- ea: `0x1800c5c60`
- end: `0x1800c616d`
- name: `?GetPackageInstalledLocation@CKnownFoldersStaticsInProc@@UEAAJIHPEAPEAUIStorageFolder@Storage@Windows@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(CKnownFoldersStaticsInProc *__hidden this, unsigned int, int, struct Windows::Storage::IStorageFolder **)`
- caller_count: `0`
- callee_count: `25`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009fc0`
- `0x1800118c4`
- `0x180038f50`
- `0x180044320`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007e1d0`
- `0x180080eb8`
- `0x180081c20`
- `0x180081d9c`
- `0x180081df0`
- `0x1800c5c60`
- `0x1800c6174`
- `0x1800c72b0`
- `0x1800c8920`
- `0x1801720d0`
- `0x18017f064`
- `0x18023eda0`
- `0x18023ee10`
- `0x180258370`
- `0x180258e3c`
- `0x18025907c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c5f47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c5f47`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800c5df3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800c5df3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c5dd8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c5dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5d25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5ec7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5d25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5ec7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180664630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180664630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c60fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806645f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180664649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806646d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c60fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806645f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180664649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806646d0`

## string_xrefs

- `0x1800c5ea4`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800c5ee5`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800c5f8a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800c6067`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180664301`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180664374`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18066458d`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800c5cb1`: `GetPackageInstalledLocation`
- `0x1800c5ff8`: `GetPackageInstalledLocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CKnownFoldersStaticsInProc::GetPackageInstalledLocation(
        CKnownFoldersStaticsInProc *this,
        int a2,
        int a3,
        struct Windows::Storage::IStorageFolder **a4)
{
  int PackageFullNameFromProcess; // ebx
  void *v8; // rcx
  WCHAR *v9; // rbx
  void *v10; // rcx
  const WCHAR *FileNameW; // rax
  HRESULT v12; // edi
  __int64 v14; // rdx
  void *v15; // rcx
  __int64 v16; // rdx
  HANDLE CurrentProcess; // rax
  unsigned __int16 **v18; // r8
  const unsigned __int16 *v19; // rbx
  unsigned __int64 v20; // rdx
  unsigned __int8 v21; // cl
  __int64 v22; // rcx
  __int64 v23; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64, _QWORD); // rbx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, __int64 *); // rbx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rdx
  LPVOID v41; // rdi
  __int64 (__fastcall *v42)(LPVOID, __int64, _QWORD **); // rbx
  _QWORD *v43; // rdi
  __int64 v44; // rax
  __int64 (__fastcall *v45)(_QWORD *, HSTRING *); // rbx
  int v46; // eax
  __int64 (__fastcall *v47)(_QWORD *, HSTRING *); // rbx
  int *v48; // [rsp+20h] [rbp-E0h]
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  int v52[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  void *v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  __int64 v58; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v60; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v62; // [rsp+A8h] [rbp-58h] BYREF
  int v63; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v64[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-28h] BYREF
  char v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v70[192]; // [rsp+F0h] [rbp-10h] BYREF
  int v71; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v72[40]; // [rsp+1B4h] [rbp+B4h] BYREF
  WCHAR v73[274]; // [rsp+1DCh] [rbp+DCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  if ( _InterlockedIncrement(&`CKnownFoldersStaticsInProc::GetPackageInstalledLocation'::`4'::__wil_apiCallCounter) == 1 )
  {
    v19 = (const unsigned __int16 *)(**((__int64 (__fastcall ***)(char *))this + 11))((char *)this + 88);
    if ( wil::details::ApiTelemetryLogger::IsEnabled(v21, v20) )
    {
      v23 = wil::details::static_lazy<wil::details::ApiTelemetryLogger>::get(
              v22,
              _lambda_6b26b9d13d28b4db0bc0125880e9ff13_::_lambda_invoker_cdecl_);
      wil::details::ApiTelemetryLogger::ApiDataList::Insert(
        (wil::details::ApiTelemetryLogger::ApiDataList *)(v23 + 32),
        v19,
        L"GetPackageInstalledLocation",
        0,
        &`CKnownFoldersStaticsInProc::GetPackageInstalledLocation'::`4'::__wil_apiCallCounter);
    }
  }
  WinRTStorageTelemetry::WatchCurrentThread(v70, "GetPackageInstalledLocation", 0);
  *a4 = 0;
  pszPath = 0;
  if ( a2 )
  {
    v55 = 0;
    hstringHeader.Reserved.Reserved1 = &v55;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    CurrentProcess = GetCurrentProcess();
    PackageFullNameFromProcess = CallerIdentity::GetPackageFullNameFromProcess(
                                   CurrentProcess,
                                   &hstringHeader.Reserved.Reserved2[8],
                                   v18);
    if ( hstringHeader.Reserved.Reserved2[16] )
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        hstringHeader.Reserved.Reserved1,
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
    if ( PackageFullNameFromProcess < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF40,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)PackageFullNameFromProcess,
        (int)v48);
      v15 = v55;
      goto LABEL_19;
    }
    v54 = 0;
    v53 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Package",
      0x29u,
      0x28u);
    v27 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
            v51,
            &v54);
    PackageFullNameFromProcess = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF44,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v27,
        (int)v48);
      goto LABEL_38;
    }
    v57 = 0;
    v58 = 0;
    v56 = 0;
    *(_QWORD *)v52 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.DependencyGraph",
      0x31u,
      0x30u);
    v28 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDependencyGraphStatics>>(
            v51,
            &v58);
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3915;
LABEL_45:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v28,
        (int)v48);
      goto LABEL_37;
    }
    v30 = v54;
    v31 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v54 + 368LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    v60 = v55;
    v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v60);
    v28 = v31(v30, 0, *(_QWORD *)(v32 + 24), &v57);
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3916;
      goto LABEL_45;
    }
    v33 = v58;
    v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v58 + 216LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
    v48 = v52;
    v28 = v34(v33, 0, v57, (unsigned int)(a2 - 1));
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3919;
      goto LABEL_45;
    }
    v63 = 0;
    v28 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v52 + 56LL))(*(_QWORD *)v52, &v63);
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3921;
      goto LABEL_45;
    }
    if ( v63 != 1 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v55);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
      PackageFullNameFromProcess = -2147024809;
      goto LABEL_16;
    }
    v35 = *(_QWORD *)v52;
    v36 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v52 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    v28 = v36(v35, 0, &v56);
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3926;
      goto LABEL_45;
    }
    v69 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 104LL))(v56, &v69);
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3928;
      goto LABEL_45;
    }
    v37 = v54;
    v38 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v54 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v28 = v38(v37, v69, &v53);
    PackageFullNameFromProcess = v28;
    if ( v28 < 0 )
    {
      v29 = 3929;
      goto LABEL_45;
    }
    pv = 0;
    v62 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.PackageLocation",
      0x31u,
      0x30u);
    v39 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(
            v51,
            &pv);
    PackageFullNameFromProcess = v39;
    if ( v39 < 0 )
    {
      v40 = 3933;
LABEL_62:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v39,
        (int)v52);
      goto LABEL_36;
    }
    v41 = pv;
    v42 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(*(_QWORD *)pv + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v39 = v42(v41, v53, &v62);
    PackageFullNameFromProcess = v39;
    if ( v39 < 0 )
    {
      v40 = 3934;
      goto LABEL_62;
    }
    string = 0;
    v43 = v62;
    v44 = *v62;
    if ( a3 )
    {
      v45 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v44 + 112);
      WindowsDeleteString(0);
      string = 0;
      v46 = v45(v43, &string);
      PackageFullNameFromProcess = v46;
      if ( v46 < 0 )
      {
        v26 = 3939;
LABEL_67:
        v25 = (unsigned int)v46;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
          (const char *)v25,
          (int)v52);
        WindowsDeleteString(string);
        string = 0;
LABEL_36:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
LABEL_37:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
LABEL_38:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v55);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
        goto LABEL_16;
      }
      if ( !WindowsGetStringRawBuffer(string, 0) )
      {
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v55);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
        PackageFullNameFromProcess = 15707;
        goto LABEL_16;
      }
    }
    else
    {
      v47 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v44 + 88);
      WindowsDeleteString(0);
      string = 0;
      v46 = v47(v43, &string);
      PackageFullNameFromProcess = v46;
      if ( v46 < 0 )
      {
        v26 = 3947;
        goto LABEL_67;
      }
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v60,
      StringRawBuffer,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &v60);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v60);
    v9 = (WCHAR *)pszPath;
    if ( pszPath )
    {
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v55);
      goto LABEL_12;
    }
    PackageFullNameFromProcess = -2147024882;
    v25 = 2147942414LL;
    v26 = 3950;
    goto LABEL_35;
  }
  v60 = 0;
  v63 = 0;
  hstringHeader.Reserved.Reserved1 = &v60;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  PackageFullNameFromProcess = GetPackageInfoFromCurrentProcessWithPathType(
                                 16,
                                 a3 != 0,
                                 &v63,
                                 &hstringHeader.Reserved.Reserved2[8]);
  if ( hstringHeader.Reserved.Reserved2[16] )
  {
    v8 = *(void **)hstringHeader.Reserved.Reserved1;
    *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
    if ( v8 )
      CoTaskMemFree(v8);
  }
  if ( PackageFullNameFromProcess < 0 )
  {
    v14 = 3897;
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      *((_QWORD *)v60 + 1),
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v9 = (WCHAR *)pszPath;
    if ( pszPath )
    {
      v10 = v60;
      v60 = 0;
      if ( v10 )
        CoTaskMemFree(v10);
LABEL_12:
      v65 = 1;
      v66 = 0;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef((char *)&v66 + 8);
      v67 = 0;
      v68 = 0;
      memset_0(v72, 0, 0x24Cu);
      v71 = 16;
      FileNameW = PathFindFileNameW(v9);
      v12 = PathCchAppend(v73, 0x104u, FileNameW);
      if ( v12 < 0 )
      {
        v16 = 3956;
      }
      else
      {
        v12 = CInProcStorageItemResult<Windows::Storage::IStorageFolder>::_Initialize(v64, v9, &v71, 0);
        if ( v12 < 0 )
        {
          v16 = 3957;
        }
        else
        {
          v12 = CInProcStorageItemResult<Windows::Storage::IStorageFolder>::Get(v64, a4);
          if ( v12 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v66 + 8);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
            CoTaskMemFree(v9);
            PackageFullNameFromProcess = 0;
            goto LABEL_16;
          }
          v16 = 3958;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v12,
        (int)v48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v66 + 8);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      CoTaskMemFree(v9);
      PackageFullNameFromProcess = v12;
      goto LABEL_16;
    }
    PackageFullNameFromProcess = -2147024882;
    v14 = 3899;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
    (const char *)(unsigned int)PackageFullNameFromProcess,
    (int)v48);
  v15 = v60;
  v60 = 0;
LABEL_19:
  if ( v15 )
    CoTaskMemFree(v15);
LABEL_16:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v70);
  return (unsigned int)PackageFullNameFromProcess;
}

```

## disassembly

```asm
0x1800c5c60  push    rbp
0x1800c5c62  push    rbx
0x1800c5c63  push    rsi
0x1800c5c64  push    rdi
0x1800c5c65  push    r12
0x1800c5c67  push    r14
0x1800c5c69  push    r15
0x1800c5c6b  lea     rbp, [rsp-310h]
0x1800c5c73  sub     rsp, 410h
0x1800c5c7a  mov     rax, cs:__security_cookie
0x1800c5c81  xor     rax, rsp
0x1800c5c84  mov     [rbp+340h+var_40], rax
0x1800c5c8b  mov     r15, r9
0x1800c5c8e  mov     r14d, r8d
0x1800c5c91  mov     esi, edx
0x1800c5c93  mov     eax, 1
0x1800c5c98  lock xadd cs:?__wil_apiCallCounter@?3??GetPackageInstalledLocation@CKnownFoldersStaticsInProc@@UEAAJIHPEAPEAUIStorageFolder@Storage@Windows@@@Z@4JC, eax; long volatile `CKnownFoldersStaticsInProc::GetPackageInstalledLocation(uint,int,Windows::Storage::IStorageFolder * *)'::`4'::__wil_apiCallCounter
0x1800c5ca0  inc     eax
0x1800c5ca2  xor     r12d, r12d
0x1800c5ca5  cmp     eax, 1
0x1800c5ca8  jz      loc_1800C5FBA
0x1800c5cae  xor     r8d, r8d
0x1800c5cb1  lea     rdx, aGetpackageinst_0; "GetPackageInstalledLocation"
0x1800c5cb8  lea     rcx, [rbp+340h+var_350]
0x1800c5cbc  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1800c5cc1  nop
0x1800c5cc2  mov     [r15], r12
0x1800c5cc5  mov     [rsp+440h+pszPath], r12
0x1800c5cca  test    esi, esi
0x1800c5ccc  jnz     loc_1800C5F2E
0x1800c5cd2  mov     [rbp+340h+var_3A8], r12
0x1800c5cd6  mov     [rbp+340h+var_390], r12d
0x1800c5cda  lea     rax, [rbp+340h+var_3A8]
0x1800c5cde  mov     qword ptr [rsp+440h+hstringHeader.Reserved], rax
0x1800c5ce3  mov     qword ptr [rsp+440h+hstringHeader.Reserved+8], r12
0x1800c5ce8  mov     byte ptr [rsp+440h+hstringHeader.Reserved+10h], 1
0x1800c5ced  mov     edx, r12d
0x1800c5cf0  test    r14d, r14d
0x1800c5cf3  setnz   dl
0x1800c5cf6  lea     r9, [rsp+440h+hstringHeader.Reserved+8]
0x1800c5cfb  lea     r8, [rbp+340h+var_390]
0x1800c5cff  lea     ecx, [rsi+10h]
0x1800c5d02  call    ?GetPackageInfoFromCurrentProcessWithPathType@@YAJIW4PackagePathType@@PEAIPEAPEAUPACKAGE_INFO@@@Z; GetPackageInfoFromCurrentProcessWithPathType(uint,PackagePathType,uint *,PACKAGE_INFO * *)
0x1800c5d07  mov     ebx, eax
0x1800c5d09  cmp     byte ptr [rsp+440h+hstringHeader.Reserved+10h], r12b
0x1800c5d0e  jz      short loc_1800C5D31
0x1800c5d10  mov     r8, qword ptr [rsp+440h+hstringHeader.Reserved]
0x1800c5d15  mov     rcx, [r8]; pv
0x1800c5d18  mov     rdx, qword ptr [rsp+440h+hstringHeader.Reserved+8]
0x1800c5d1d  mov     [r8], rdx
0x1800c5d20  test    rcx, rcx
0x1800c5d23  jz      short loc_1800C5D31
0x1800c5d25  call    cs:__imp_CoTaskMemFree
0x1800c5d2c  nop     dword ptr [rax+rax+00h]
0x1800c5d31  test    ebx, ebx
0x1800c5d33  js      loc_1800C5F24
0x1800c5d39  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c5d3d  mov     rdx, [rbp+340h+var_3A8]
0x1800c5d41  mov     rdx, [rdx+8]
0x1800c5d45  lea     rcx, [rbp+340h+pv]
0x1800c5d49  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800c5d4e  lea     rdx, [rbp+340h+pv]
0x1800c5d52  lea     rcx, [rsp+440h+pszPath]
0x1800c5d57  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800c5d5c  mov     rcx, [rbp+340h+pv]; pv
0x1800c5d60  test    rcx, rcx
0x1800c5d63  jz      short loc_1800C5D71
0x1800c5d65  call    cs:__imp_CoTaskMemFree
0x1800c5d6c  nop     dword ptr [rax+rax+00h]
0x1800c5d71  mov     rbx, [rsp+440h+pszPath]
0x1800c5d76  test    rbx, rbx
0x1800c5d79  jz      loc_1800C5E9A
0x1800c5d7f  mov     rcx, [rbp+340h+var_3A8]; pv
0x1800c5d83  mov     [rbp+340h+var_3A8], r12
0x1800c5d87  test    rcx, rcx
0x1800c5d8a  jz      short loc_1800C5D98
0x1800c5d8c  call    cs:__imp_CoTaskMemFree
0x1800c5d93  nop     dword ptr [rax+rax+00h]
0x1800c5d98  mov     [rbp+340h+var_380], 1
0x1800c5d9e  xorps   xmm0, xmm0
0x1800c5da1  movdqu  [rbp+340h+var_378], xmm0
0x1800c5da6  lea     rcx, [rbp+340h+var_378+8]
0x1800c5daa  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800c5daf  mov     [rbp+340h+var_368], r12
0x1800c5db3  mov     [rbp+340h+var_360], r12b
0x1800c5db7  xor     edx, edx; Val
0x1800c5db9  mov     r8d, 24Ch; Size
0x1800c5dbf  lea     rcx, [rbp+340h+var_28C]; void *
0x1800c5dc6  call    memset_0
0x1800c5dcb  mov     [rbp+340h+var_290], 10h
0x1800c5dd5  mov     rcx, rbx; pszPath
0x1800c5dd8  call    cs:__imp_PathFindFileNameW
0x1800c5ddf  nop     dword ptr [rax+rax+00h]
0x1800c5de4  mov     r8, rax; pszMore
0x1800c5de7  mov     edx, 104h; cchPath
0x1800c5dec  lea     rcx, [rbp+340h+var_264]; pszPath
0x1800c5df3  call    cs:__imp_PathCchAppend
0x1800c5dfa  nop     dword ptr [rax+rax+00h]
0x1800c5dff  mov     edi, eax
0x1800c5e01  test    eax, eax
0x1800c5e03  js      loc_1800C5ED6
0x1800c5e09  xor     r9d, r9d
0x1800c5e0c  lea     r8, [rbp+340h+var_290]
0x1800c5e13  mov     rdx, rbx
0x1800c5e16  lea     rcx, [rbp+340h+var_388]
0x1800c5e1a  call    ?_Initialize@?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@AEAAJPEBGPEBU_WIN32_FIND_DATAW@@PEAUIUser@System@Windows@@@Z; CInProcStorageItemResult<Windows::Storage::IStorageFolder>::_Initialize(ushort const *,_WIN32_FIND_DATAW const *,Windows::System::IUser *)
0x1800c5e1f  mov     edi, eax
0x1800c5e21  test    eax, eax
0x1800c5e23  js      loc_1800C5FB0
0x1800c5e29  mov     rdx, r15
0x1800c5e2c  lea     rcx, [rbp+340h+var_388]
0x1800c5e30  call    ?Get@?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@QEAAJPEAPEAUIStorageFolder@Storage@Windows@@@Z; CInProcStorageItemResult<Windows::Storage::IStorageFolder>::Get(Windows::Storage::IStorageFolder * *)
0x1800c5e35  mov     edi, eax
0x1800c5e37  test    eax, eax
0x1800c5e39  js      loc_1800C5FA6
0x1800c5e3f  lea     rcx, [rbp+340h+var_368]
0x1800c5e43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5e48  lea     rcx, [rbp+340h+var_378+8]
0x1800c5e4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5e51  lea     rcx, [rbp+340h+var_378]
0x1800c5e55  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5e5a  nop
0x1800c5e5b  mov     rcx, rbx; pv
0x1800c5e5e  call    cs:__imp_CoTaskMemFree
0x1800c5e65  nop     dword ptr [rax+rax+00h]
0x1800c5e6a  mov     ebx, r12d
0x1800c5e6d  lea     rcx, [rbp+340h+var_350]; this
0x1800c5e71  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1800c5e76  mov     eax, ebx
0x1800c5e78  mov     rcx, [rbp+340h+var_40]
0x1800c5e7f  xor     rcx, rsp; StackCookie
0x1800c5e82  call    __security_check_cookie
0x1800c5e87  add     rsp, 410h
0x1800c5e8e  pop     r15
0x1800c5e90  pop     r14
0x1800c5e92  pop     r12
0x1800c5e94  pop     rdi
0x1800c5e95  pop     rsi
0x1800c5e96  pop     rbx
0x1800c5e97  pop     rbp
0x1800c5e98  retn
0x1800c5e9a  mov     ebx, 8007000Eh
0x1800c5e9f  mov     edx, 0F3Bh; void *
0x1800c5ea4  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800c5eab  mov     r9d, ebx; char *
0x1800c5eae  mov     rcx, [rbp+348h]; this
0x1800c5eb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5eba  mov     rcx, [rbp+340h+var_3A8]; pv
0x1800c5ebe  mov     [rbp+340h+var_3A8], r12
0x1800c5ec2  test    rcx, rcx
0x1800c5ec5  jz      short loc_1800C5ED4
0x1800c5ec7  call    cs:__imp_CoTaskMemFree
0x1800c5ece  nop     dword ptr [rax+rax+00h]
0x1800c5ed3  nop
0x1800c5ed4  jmp     short loc_1800C5E6D
0x1800c5ed6  mov     edx, 0F74h; void *
0x1800c5edb  mov     rcx, [rbp+348h]; this
0x1800c5ee2  mov     r9d, edi; char *
0x1800c5ee5  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800c5eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5ef1  nop
0x1800c5ef2  lea     rcx, [rbp+340h+var_368]
0x1800c5ef6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5efb  lea     rcx, [rbp+340h+var_378+8]
0x1800c5eff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5f04  lea     rcx, [rbp+340h+var_378]
0x1800c5f08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5f0d  nop
0x1800c5f0e  mov     rcx, rbx; pv
0x1800c5f11  call    cs:__imp_CoTaskMemFree
0x1800c5f18  nop     dword ptr [rax+rax+00h]
0x1800c5f1d  mov     ebx, edi
0x1800c5f1f  jmp     loc_1800C5E6D
0x1800c5f24  mov     edx, 0F39h
0x1800c5f29  jmp     loc_1800C5EA4
0x1800c5f2e  mov     [rsp+440h+var_3D0], r12
0x1800c5f33  lea     rax, [rsp+440h+var_3D0]
0x1800c5f38  mov     qword ptr [rsp+440h+hstringHeader.Reserved], rax
0x1800c5f3d  mov     qword ptr [rsp+440h+hstringHeader.Reserved+8], r12
0x1800c5f42  mov     byte ptr [rsp+440h+hstringHeader.Reserved+10h], 1
0x1800c5f47  call    cs:__imp_GetCurrentProcess
0x1800c5f4e  nop     dword ptr [rax+rax+00h]
0x1800c5f53  lea     rdx, [rsp+440h+hstringHeader.Reserved+8]; void *
0x1800c5f58  mov     rcx, rax; hProcess
0x1800c5f5b  call    ?GetPackageFullNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromProcess(void *,ushort * *)
0x1800c5f60  mov     ebx, eax
0x1800c5f62  cmp     byte ptr [rsp+440h+hstringHeader.Reserved+10h], r12b
0x1800c5f67  jz      short loc_1800C5F78
0x1800c5f69  mov     rdx, qword ptr [rsp+440h+hstringHeader.Reserved+8]
0x1800c5f6e  mov     rcx, qword ptr [rsp+440h+hstringHeader.Reserved]
0x1800c5f73  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c5f78  test    ebx, ebx
0x1800c5f7a  jns     loc_1806642B8
0x1800c5f80  mov     rcx, [rbp+348h]; this
0x1800c5f87  mov     r9d, ebx; char *
0x1800c5f8a  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800c5f91  mov     edx, 0F40h; void *
0x1800c5f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5f9b  nop
0x1800c5f9c  mov     rcx, [rsp+440h+var_3D0]
0x1800c5fa1  jmp     loc_1800C5EC2
0x1800c5fa6  mov     edx, 0F76h
0x1800c5fab  jmp     loc_1800C5EDB
0x1800c5fb0  mov     edx, 0F75h
0x1800c5fb5  jmp     loc_1800C5EDB
0x1800c5fba  add     rcx, 58h ; 'X'
0x1800c5fbe  mov     rax, [rcx]
0x1800c5fc1  mov     rax, [rax]
0x1800c5fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5fc9  mov     rbx, rax
0x1800c5fcc  call    ?IsEnabled@ApiTelemetryLogger@details@wil@@SA_NE_K@Z; wil::details::ApiTelemetryLogger::IsEnabled(uchar,unsigned __int64)
0x1800c5fd1  test    al, al
0x1800c5fd3  jz      loc_1800C5CAE
0x1800c5fd9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_6b26b9d13d28b4db0bc0125880e9ff13_@@CA@XZ; _lambda_6b26b9d13d28b4db0bc0125880e9ff13_::_lambda_invoker_cdecl_(void)
0x1800c5fe0  call    ?get@?$static_lazy@VApiTelemetryLogger@details@wil@@@details@wil@@QEAAPEAVApiTelemetryLogger@23@P6AXXZ@Z; wil::details::static_lazy<wil::details::ApiTelemetryLogger>::get(void (*)(void))
0x1800c5fe5  lea     rcx, [rax+20h]; this
0x1800c5fe9  lea     rax, ?__wil_apiCallCounter@?3??GetPackageInstalledLocation@CKnownFoldersStaticsInProc@@UEAAJIHPEAPEAUIStorageFolder@Storage@Windows@@@Z@4JC; long volatile `CKnownFoldersStaticsInProc::GetPackageInstalledLocation(uint,int,Windows::Storage::IStorageFolder * *)'::`4'::__wil_apiCallCounter
0x1800c5ff0  mov     [rsp+440h+var_420], rax; volatile int *
0x1800c5ff5  xor     r9d, r9d; char *
0x1800c5ff8  lea     r8, aGetpackageinst; "GetPackageInstalledLocation"
0x1800c5fff  mov     rdx, rbx; unsigned __int16 *
0x1800c6002  call    ?Insert@ApiDataList@ApiTelemetryLogger@details@wil@@QEAAXPEBG0PEBDPECJ@Z; wil::details::ApiTelemetryLogger::ApiDataList::Insert(ushort const *,ushort const *,char const *,long volatile *)
0x1800c6007  jmp     loc_1800C5CAE
0x1800c600c  xor     edx, edx; length
0x1800c600e  mov     rcx, [rbp+340h+string]; string
0x1800c6012  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c6019  nop     dword ptr [rax+rax+00h]
0x1800c601e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c6022  mov     rdx, rax
0x1800c6025  lea     rcx, [rbp+340h+var_3A8]
0x1800c6029  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800c602e  lea     rdx, [rbp+340h+var_3A8]
0x1800c6032  lea     rcx, [rsp+440h+pszPath]
0x1800c6037  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800c603c  lea     rcx, [rbp+340h+var_3A8]; void *
0x1800c6040  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c6045  mov     rbx, [rsp+440h+pszPath]
0x1800c604a  test    rbx, rbx
0x1800c604d  jnz     loc_1800C60F6
0x1800c6053  mov     ebx, 8007000Eh
0x1800c6058  mov     r9d, ebx; char *
0x1800c605b  mov     edx, 0F6Eh; void *
0x1800c6060  mov     rcx, [rbp+348h]; this
0x1800c6067  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800c606e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6073  nop
0x1800c6074  mov     rcx, [rbp+340h+string]; string
0x1800c6078  call    cs:__imp_WindowsDeleteString
0x1800c607f  nop     dword ptr [rax+rax+00h]
0x1800c6084  mov     [rbp+340h+string], r12
0x1800c6088  lea     rcx, [rbp+340h+var_398]
0x1800c608c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6091  nop
0x1800c6092  lea     rcx, [rbp+340h+pv]
0x1800c6096  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c609b  nop
0x1800c609c  lea     rcx, [rsp+440h+var_3E8]
0x1800c60a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c60a6  nop
0x1800c60a7  lea     rcx, [rsp+440h+var_3C8]
0x1800c60ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c60b1  nop
0x1800c60b2  lea     rcx, [rbp+340h+var_3B8]
0x1800c60b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c60bb  nop
0x1800c60bc  lea     rcx, [rbp+340h+var_3C0]
0x1800c60c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c60c5  nop
0x1800c60c6  lea     rcx, [rsp+440h+var_3E0]
0x1800c60cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c60d0  nop
0x1800c60d1  lea     rcx, [rsp+440h+var_3D8]
0x1800c60d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c60db  nop
0x1800c60dc  lea     rcx, [rsp+440h+var_3D0]; void *
0x1800c60e1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c60e6  nop
0x1800c60e7  lea     rcx, [rsp+440h+pszPath]; void *
0x1800c60ec  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c60f1  jmp     loc_1800C5E6D
0x1800c60f6  mov     rcx, [rbp+340h+string]; string
0x1800c60fa  call    cs:__imp_WindowsDeleteString
0x1800c6101  nop     dword ptr [rax+rax+00h]
0x1800c6106  mov     [rbp+340h+string], r12
0x1800c610a  lea     rcx, [rbp+340h+var_398]
0x1800c610e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6113  nop
0x1800c6114  lea     rcx, [rbp+340h+pv]
0x1800c6118  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c611d  nop
0x1800c611e  lea     rcx, [rsp+440h+var_3E8]
0x1800c6123  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6128  nop
0x1800c6129  lea     rcx, [rsp+440h+var_3C8]
0x1800c612e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6133  nop
0x1800c6134  lea     rcx, [rbp+340h+var_3B8]
0x1800c6138  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c613d  nop
0x1800c613e  lea     rcx, [rbp+340h+var_3C0]
  ... truncated ...
```
