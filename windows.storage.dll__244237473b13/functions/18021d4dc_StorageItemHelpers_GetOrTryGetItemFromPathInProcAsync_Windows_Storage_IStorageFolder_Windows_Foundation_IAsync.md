# StorageItemHelpers::GetOrTryGetItemFromPathInProcAsync<Windows::Storage::IStorageFolder,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *>>(Windows::Internal::ICapturedCallerContext *,HSTRING__ *,bool,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *)

- ea: `0x18021d4dc`
- end: `0x18021dda0`
- name: `??$GetOrTryGetItemFromPathInProcAsync@UIStorageFolder@Storage@Windows@@U?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@3@@StorageItemHelpers@@YAJPEAUICapturedCallerContext@Internal@Windows@@PEAUHSTRING__@@_NPEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@3@@Z`
- size: `2244`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1804064a0`

## callees

- `0x180009fc0`
- `0x1800118c4`
- `0x180017e60`
- `0x18001cd08`
- `0x18001e670`
- `0x180038f50`
- `0x18007bbf0`
- `0x1800899a4`
- `0x18013c22c`
- `0x18021d4dc`
- `0x18021e588`
- `0x18021eea4`
- `0x1802bb7ac`
- `0x1803b1f60`
- `0x1803d05ec`
- `0x1803d0aa4`
- `0x1803e1178`
- `0x1803e5328`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021d612`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021d82b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021d612`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021d82b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18021d9a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18021d9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18021d9a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18021d9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021d5ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021d80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021d5ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021d80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021d994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021d9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021d994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021d9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021da77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021da8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dd2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021da77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021da8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021dd2e`

## string_xrefs

- `0x18021d579`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d63f`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d6e4`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d782`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d868`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d90a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d9f2`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021da40`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021db50`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021dc0c`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021d5e8`: `Windows.Foundation.Uri`
- `0x18021d51f`: `GetOrTryGetItemFromPathInProcAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall StorageItemHelpers::GetOrTryGetItemFromPathInProcAsync<Windows::Storage::IStorageFolder,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *>>(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _QWORD *a4)
{
  struct Windows::Internal::String *v6; // r8
  int v7; // eax
  int ApplicationPathAccess; // edi
  _QWORD *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // eax
  _QWORD *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING, __int64 *); // rbx
  int v18; // eax
  _QWORD *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // r8
  int v22; // eax
  _QWORD *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // r8
  _QWORD *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // r8
  int v29; // eax
  _QWORD *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r8
  HSTRING v33; // r14
  unsigned int StringRawBuffer; // edi
  UINT32 StringLen; // ebx
  int v36; // r9d
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rbx
  __int64 v41; // rax
  __int64 v42; // r8
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // r8
  char v46; // cl
  _QWORD *v47; // rbx
  __int64 v48; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  _QWORD *v53; // rbx
  __int64 v54; // rax
  __int64 v55; // r8
  int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+30h] [rbp-D0h] BYREF
  int v61; // [rsp+38h] [rbp-C8h]
  char v62; // [rsp+40h] [rbp-C0h] BYREF
  int v63[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  char v65; // [rsp+60h] [rbp-A0h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  int *v67; // [rsp+88h] [rbp-78h]
  _QWORD **v68; // [rsp+90h] [rbp-70h]
  char v69; // [rsp+98h] [rbp-68h]
  _BYTE v70[48]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v71; // [rsp+D0h] [rbp-30h] BYREF
  int v72; // [rsp+D8h] [rbp-28h] BYREF
  int v73; // [rsp+DCh] [rbp-24h] BYREF
  _BYTE v74[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v77; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v78[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v79[104]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v80; // [rsp+178h] [rbp+78h]
  char v81; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v71 = a4;
  v62 = 0;
  LOBYTE(a4) = 1;
  WinRTStorageTelemetry::WatchCurrentThread(v79, "GetOrTryGetItemFromPathInProcAsync", a1, a4);
  *v71 = 0;
  v72 = 0;
  v67 = &v72;
  v68 = &v71;
  v69 = 1;
  string = 0;
  v65 = 0;
  v7 = StorageItemHelpers::TrimTrailingPathSeparators(a2, (HSTRING)&string, v6);
  ApplicationPathAccess = v7;
  v72 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v7,
      v57);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( v72 < 0 )
    {
      v9 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v10 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v9,
        v11,
        v10);
    }
    goto LABEL_78;
  }
  v76 = 0;
  v75 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Uri",
         0x16u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
          hstringHeader.Reserved.Reserved1,
          &v76);
  ApplicationPathAccess = v12;
  v72 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E45,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v12,
      v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( v72 < 0 )
    {
      v13 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v14 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v13,
        v15,
        v14);
    }
    goto LABEL_78;
  }
  v16 = v76;
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v76 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  v18 = v17(v16, a2, &v75);
  ApplicationPathAccess = v18;
  v72 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E48,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v18,
      v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( v72 < 0 )
    {
      v19 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v20 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v19,
        v21,
        v20);
    }
    goto LABEL_78;
  }
  v77 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v75 + 136LL))(v75, &v77);
  ApplicationPathAccess = v22;
  v72 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v22,
      v57);
    Windows::Internal::String::~String((Windows::Internal::String *)&v77);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( v72 < 0 )
    {
      v23 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v24 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v23,
        v25,
        v24);
    }
    goto LABEL_78;
  }
  if ( WindowsCreateStringReference(
         L"file",
         4u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (unsigned __int8)Windows::Internal::operator==(&v77, &hstringHeader) )
  {
    ApplicationPathAccess = v72;
  }
  else
  {
    ApplicationPathAccess = -2147024735;
    v72 = -2147024735;
  }
  if ( ApplicationPathAccess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E53,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)ApplicationPathAccess,
      v57);
    Windows::Internal::String::~String((Windows::Internal::String *)&v77);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( v72 < 0 )
    {
      v26 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v27 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v26,
        v28,
        v27);
    }
    goto LABEL_78;
  }
  v78[0] = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v75 + 104LL))(v75, v78);
  ApplicationPathAccess = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E56,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v29,
      v57);
    Windows::Internal::String::~String((Windows::Internal::String *)v78);
    Windows::Internal::String::~String((Windows::Internal::String *)&v77);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( v72 < 0 )
    {
      v30 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v31 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v30,
        v32,
        v31);
    }
    goto LABEL_78;
  }
  v33 = string;
  StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
  StringLen = WindowsGetStringLen(v33);
  if ( StringLen > WindowsGetStringLen(v78[0]) )
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(v78[0], 0);
  *(_QWORD *)v63 = 0;
  if ( v72 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v63);
    ApplicationPathAccess = CreateApplicationPathAccess(a1, 0, StringRawBuffer, v36, (__int64)v63);
    v72 = ApplicationPathAccess;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1E61,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v72,
      v57);
    ApplicationPathAccess = v72;
  }
  if ( ApplicationPathAccess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E65,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)ApplicationPathAccess,
      v58);
    v37 = *(_QWORD *)v63;
    if ( *(_QWORD *)v63 )
    {
      *(_QWORD *)v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    if ( v78[0] )
      WindowsDeleteString(v78[0]);
    if ( v77 )
      WindowsDeleteString(v77);
    v38 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    if ( v33 )
      WindowsDeleteString(v33);
    if ( v72 < 0 )
    {
      v40 = v71;
      v73 = v72;
      v60 = 4;
      v61 = 0;
      v41 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v73);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &v60,
        v40,
        v42,
        v41);
    }
    goto LABEL_78;
  }
  v73 = 0;
  v74[0] = 0;
  v43 = (*(__int64 (__fastcall **)(_QWORD, int *, _BYTE *))(**(_QWORD **)v63 + 72LL))(*(_QWORD *)v63, &v73, v74);
  v72 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1E6C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v43,
      v58);
LABEL_64:
    ApplicationPathAccess = v72;
    v50 = *(_QWORD *)v63;
    if ( *(_QWORD *)v63 )
    {
      *(_QWORD *)v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    if ( v78[0] )
      WindowsDeleteString(v78[0]);
    if ( v77 )
      WindowsDeleteString(v77);
    v51 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    if ( v33 )
      WindowsDeleteString(v33);
    if ( v72 < 0 )
    {
      v53 = v71;
      LODWORD(v60) = v72;
      hstringHeader.Reserved.Reserved1 = (PVOID)4;
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      v54 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v60);
      Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
        &hstringHeader,
        v53,
        v55,
        v54);
    }
    goto LABEL_78;
  }
  if ( !v74[0] )
  {
    v72 = -2147024891;
    goto LABEL_64;
  }
  v60 = a1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v60);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v80;
  v44 = _lambda_4f1a2db8a1bedd2cd74c32a295a56ea5_::_lambda_4f1a2db8a1bedd2cd74c32a295a56ea5_(
          (unsigned int)v70,
          (unsigned int)&string,
          (unsigned int)&v62,
          (unsigned int)&v60,
          (__int64)&hstringHeader);
  LODWORD(hstringHeader.Reserved.Reserved1) = 3;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[4] = 128;
  v72 = Windows::Internal::MakeAsyncOperation<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler,_lambda_1cd2de15c86421a6f9bdef2ae129e881_>(
          &hstringHeader,
          v71,
          v45,
          v44);
  _lambda_1cd2de15c86421a6f9bdef2ae129e881_::~_lambda_1cd2de15c86421a6f9bdef2ae129e881_((_lambda_1cd2de15c86421a6f9bdef2ae129e881_ *)v70);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  v46 = v81;
  ApplicationPathAccess = v72;
  if ( v72 >= 0 )
    v46 = 0;
  v81 = v46;
  if ( v72 >= 0 )
  {
    v33 = string;
    goto LABEL_64;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E7D,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
    (const char *)(unsigned int)v72,
    v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v63);
  Windows::Internal::String::~String((Windows::Internal::String *)v78);
  Windows::Internal::String::~String((Windows::Internal::String *)&v77);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  if ( v72 < 0 )
  {
    v47 = v71;
    LODWORD(v60) = v72;
    hstringHeader.Reserved.Reserved1 = (PVOID)4;
    *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    v48 = Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(&v60);
    Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
      &hstringHeader,
      v47,
      v49,
      v48);
  }
LABEL_78:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v79);
  return (unsigned int)ApplicationPathAccess;
}

```

## disassembly

```asm
0x18021d4dc  push    rbp
0x18021d4de  push    rbx
0x18021d4df  push    rsi
0x18021d4e0  push    rdi
0x18021d4e1  push    r12
0x18021d4e3  push    r14
0x18021d4e5  push    r15
0x18021d4e7  lea     rbp, [rsp-0E0h]
0x18021d4ef  sub     rsp, 1E0h
0x18021d4f6  mov     rax, cs:__security_cookie
0x18021d4fd  xor     rax, rsp
0x18021d500  mov     [rbp+110h+var_40], rax
0x18021d507  mov     rsi, rdx
0x18021d50a  mov     r15, rcx
0x18021d50d  mov     [rbp+110h+var_140], r9
0x18021d511  xor     r12d, r12d
0x18021d514  mov     [rsp+210h+var_1D0], r12b
0x18021d519  mov     r9b, 1
0x18021d51c  mov     r8, rcx
0x18021d51f  lea     rdx, aGetortrygetite_1; "GetOrTryGetItemFromPathInProcAsync"
0x18021d526  lea     rcx, [rbp+110h+var_100]
0x18021d52a  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBDPEAUICapturedCallerContext@Internal@Windows@@_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,Windows::Internal::ICapturedCallerContext *,bool)
0x18021d52f  nop
0x18021d530  mov     rax, [rbp+110h+var_140]
0x18021d534  mov     [rax], r12
0x18021d537  mov     dword ptr [rbp+110h+var_138], r12d
0x18021d53b  lea     rax, [rbp+110h+var_138]
0x18021d53f  mov     [rbp+110h+var_188], rax
0x18021d543  lea     rax, [rbp+110h+var_140]
0x18021d547  mov     [rbp+110h+var_180], rax
0x18021d54b  mov     [rbp+110h+var_178], 1
0x18021d54f  mov     [rsp+210h+string], r12
0x18021d554  mov     [rsp+210h+var_1B0], r12b
0x18021d559  lea     rdx, [rsp+210h+string]; this
0x18021d55e  mov     rcx, rsi; string
0x18021d561  call    ?TrimTrailingPathSeparators@StorageItemHelpers@@YAJPEAUHSTRING__@@PEAVString@Internal@Windows@@@Z; StorageItemHelpers::TrimTrailingPathSeparators(HSTRING__ *,Windows::Internal::String *)
0x18021d566  mov     edi, eax
0x18021d568  mov     dword ptr [rbp+110h+var_138], eax
0x18021d56b  test    eax, eax
0x18021d56d  jns     short loc_18021D5D1
0x18021d56f  mov     rcx, [rbp+118h]; this
0x18021d576  mov     r9d, eax; char *
0x18021d579  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021d580  mov     edx, 1E3Fh; void *
0x18021d585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021d58a  nop
0x18021d58b  lea     rcx, [rsp+210h+string]; this
0x18021d590  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d595  nop
0x18021d596  mov     eax, dword ptr [rbp+110h+var_138]
0x18021d599  test    eax, eax
0x18021d59b  jns     short loc_18021D5CC
0x18021d59d  mov     rbx, [rbp+110h+var_140]
0x18021d5a1  mov     dword ptr [rbp+110h+var_138+4], eax
0x18021d5a4  mov     [rsp+210h+var_1E0], 4
0x18021d5ad  mov     [rsp+210h+var_1D8], r12d
0x18021d5b2  lea     rcx, [rbp+110h+var_138+4]
0x18021d5b6  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x18021d5bb  mov     r9, rax
0x18021d5be  mov     rdx, rbx
0x18021d5c1  lea     rcx, [rsp+210h+var_1E0]
0x18021d5c6  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x18021d5cb  nop
0x18021d5cc  jmp     loc_18021DD73
0x18021d5d1  mov     [rbp+110h+var_120], r12
0x18021d5d5  mov     [rbp+110h+var_128], r12
0x18021d5d9  lea     r9, [rsp+210h+hstringHeader]; string
0x18021d5de  lea     r8, [rsp+210h+hstringHeader.Reserved+8]; hstringHeader
0x18021d5e3  mov     edx, 16h; length
0x18021d5e8  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18021d5ef  call    cs:__imp_WindowsCreateStringReference
0x18021d5f6  nop     dword ptr [rax+rax+00h]
0x18021d5fb  mov     r14d, 0C000000Dh
0x18021d601  test    eax, eax
0x18021d603  jns     short loc_18021D61E
0x18021d605  xor     r9d, r9d; lpArguments
0x18021d608  xor     r8d, r8d; nNumberOfArguments
0x18021d60b  lea     edx, [r9+1]; dwExceptionFlags
0x18021d60f  mov     ecx, r14d; dwExceptionCode
0x18021d612  call    cs:__imp_RaiseException
0x18021d619  nop     dword ptr [rax+rax+00h]
0x18021d61e  lea     rdx, [rbp+110h+var_120]
0x18021d622  mov     rcx, qword ptr [rsp+210h+hstringHeader.Reserved]
0x18021d627  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18021d62c  mov     edi, eax
0x18021d62e  mov     dword ptr [rbp+110h+var_138], eax
0x18021d631  test    eax, eax
0x18021d633  jns     short loc_18021D6AB
0x18021d635  mov     rcx, [rbp+118h]; this
0x18021d63c  mov     r9d, eax; char *
0x18021d63f  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021d646  mov     edx, 1E45h; void *
0x18021d64b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021d650  nop
0x18021d651  lea     rcx, [rbp+110h+var_128]
0x18021d655  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d65a  nop
0x18021d65b  lea     rcx, [rbp+110h+var_120]
0x18021d65f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d664  nop
0x18021d665  lea     rcx, [rsp+210h+string]; this
0x18021d66a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d66f  nop
0x18021d670  mov     eax, dword ptr [rbp+110h+var_138]
0x18021d673  test    eax, eax
0x18021d675  jns     short loc_18021D6A6
0x18021d677  mov     rbx, [rbp+110h+var_140]
0x18021d67b  mov     dword ptr [rbp+110h+var_138+4], eax
0x18021d67e  mov     [rsp+210h+var_1E0], 4
0x18021d687  mov     [rsp+210h+var_1D8], r12d
0x18021d68c  lea     rcx, [rbp+110h+var_138+4]
0x18021d690  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x18021d695  mov     r9, rax
0x18021d698  mov     rdx, rbx
0x18021d69b  lea     rcx, [rsp+210h+var_1E0]
0x18021d6a0  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x18021d6a5  nop
0x18021d6a6  jmp     loc_18021DD73
0x18021d6ab  mov     rdi, [rbp+110h+var_120]
0x18021d6af  mov     rax, [rdi]
0x18021d6b2  mov     rbx, [rax+30h]
0x18021d6b6  lea     rcx, [rbp+110h+var_128]
0x18021d6ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d6bf  lea     r8, [rbp+110h+var_128]
0x18021d6c3  mov     rdx, rsi
0x18021d6c6  mov     rcx, rdi
0x18021d6c9  mov     rax, rbx
0x18021d6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021d6d1  mov     edi, eax
0x18021d6d3  mov     dword ptr [rbp+110h+var_138], eax
0x18021d6d6  test    eax, eax
0x18021d6d8  jns     short loc_18021D750
0x18021d6da  mov     rcx, [rbp+118h]; this
0x18021d6e1  mov     r9d, eax; char *
0x18021d6e4  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021d6eb  mov     edx, 1E48h; void *
0x18021d6f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021d6f5  nop
0x18021d6f6  lea     rcx, [rbp+110h+var_128]
0x18021d6fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d6ff  nop
0x18021d700  lea     rcx, [rbp+110h+var_120]
0x18021d704  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d709  nop
0x18021d70a  lea     rcx, [rsp+210h+string]; this
0x18021d70f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d714  nop
0x18021d715  mov     eax, dword ptr [rbp+110h+var_138]
0x18021d718  test    eax, eax
0x18021d71a  jns     short loc_18021D74B
0x18021d71c  mov     rbx, [rbp+110h+var_140]
0x18021d720  mov     dword ptr [rbp+110h+var_138+4], eax
0x18021d723  mov     [rsp+210h+var_1E0], 4
0x18021d72c  mov     [rsp+210h+var_1D8], r12d
0x18021d731  lea     rcx, [rbp+110h+var_138+4]
0x18021d735  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x18021d73a  mov     r9, rax
0x18021d73d  mov     rdx, rbx
0x18021d740  lea     rcx, [rsp+210h+var_1E0]
0x18021d745  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x18021d74a  nop
0x18021d74b  jmp     loc_18021DD73
0x18021d750  mov     [rbp+110h+var_118], r12
0x18021d754  mov     rcx, [rbp+110h+var_128]
0x18021d758  mov     rax, [rcx]
0x18021d75b  lea     rdx, [rbp+110h+var_118]
0x18021d75f  mov     rax, [rax+88h]
0x18021d766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021d76b  mov     edi, eax
0x18021d76d  mov     dword ptr [rbp+110h+var_138], eax
0x18021d770  test    eax, eax
0x18021d772  jns     loc_18021D7F8
0x18021d778  mov     rcx, [rbp+118h]; this
0x18021d77f  mov     r9d, eax; char *
0x18021d782  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021d789  mov     edx, 1E4Ch; void *
0x18021d78e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021d793  nop
0x18021d794  lea     rcx, [rbp+110h+var_118]; this
0x18021d798  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d79d  nop
0x18021d79e  lea     rcx, [rbp+110h+var_128]
0x18021d7a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d7a7  nop
0x18021d7a8  lea     rcx, [rbp+110h+var_120]
0x18021d7ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d7b1  nop
0x18021d7b2  lea     rcx, [rsp+210h+string]; this
0x18021d7b7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d7bc  nop
0x18021d7bd  mov     eax, dword ptr [rbp+110h+var_138]
0x18021d7c0  test    eax, eax
0x18021d7c2  jns     short loc_18021D7F3
0x18021d7c4  mov     rbx, [rbp+110h+var_140]
0x18021d7c8  mov     dword ptr [rbp+110h+var_138+4], eax
0x18021d7cb  mov     [rsp+210h+var_1E0], 4
0x18021d7d4  mov     [rsp+210h+var_1D8], r12d
0x18021d7d9  lea     rcx, [rbp+110h+var_138+4]
0x18021d7dd  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x18021d7e2  mov     r9, rax
0x18021d7e5  mov     rdx, rbx
0x18021d7e8  lea     rcx, [rsp+210h+var_1E0]
0x18021d7ed  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x18021d7f2  nop
0x18021d7f3  jmp     loc_18021DD73
0x18021d7f8  lea     r9, [rsp+210h+hstringHeader]; string
0x18021d7fd  lea     r8, [rsp+210h+hstringHeader.Reserved+8]; hstringHeader
0x18021d802  mov     edx, 4; length
0x18021d807  lea     rcx, aFile; "file"
0x18021d80e  call    cs:__imp_WindowsCreateStringReference
0x18021d815  nop     dword ptr [rax+rax+00h]
0x18021d81a  test    eax, eax
0x18021d81c  jns     short loc_18021D837
0x18021d81e  xor     r9d, r9d; lpArguments
0x18021d821  xor     r8d, r8d; nNumberOfArguments
0x18021d824  lea     edx, [r9+1]; dwExceptionFlags
0x18021d828  mov     ecx, r14d; dwExceptionCode
0x18021d82b  call    cs:__imp_RaiseException
0x18021d832  nop     dword ptr [rax+rax+00h]
0x18021d837  lea     rdx, [rsp+210h+hstringHeader]
0x18021d83c  lea     rcx, [rbp+110h+var_118]
0x18021d840  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x18021d845  test    al, al
0x18021d847  jnz     short loc_18021D853
0x18021d849  mov     edi, 800700A1h
0x18021d84e  mov     dword ptr [rbp+110h+var_138], edi
0x18021d851  jmp     short loc_18021D856
0x18021d853  mov     edi, dword ptr [rbp+110h+var_138]
0x18021d856  test    edi, edi
0x18021d858  jns     loc_18021D8DE
0x18021d85e  mov     rcx, [rbp+118h]; this
0x18021d865  mov     r9d, edi; char *
0x18021d868  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021d86f  mov     edx, 1E53h; void *
0x18021d874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021d879  nop
0x18021d87a  lea     rcx, [rbp+110h+var_118]; this
0x18021d87e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d883  nop
0x18021d884  lea     rcx, [rbp+110h+var_128]
0x18021d888  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d88d  nop
0x18021d88e  lea     rcx, [rbp+110h+var_120]
0x18021d892  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d897  nop
0x18021d898  lea     rcx, [rsp+210h+string]; this
0x18021d89d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d8a2  nop
0x18021d8a3  mov     eax, dword ptr [rbp+110h+var_138]
0x18021d8a6  test    eax, eax
0x18021d8a8  jns     short loc_18021D8D9
0x18021d8aa  mov     rbx, [rbp+110h+var_140]
0x18021d8ae  mov     dword ptr [rbp+110h+var_138+4], eax
0x18021d8b1  mov     [rsp+210h+var_1E0], 4
0x18021d8ba  mov     [rsp+210h+var_1D8], r12d
0x18021d8bf  lea     rcx, [rbp+110h+var_138+4]
0x18021d8c3  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x18021d8c8  mov     r9, rax
0x18021d8cb  mov     rdx, rbx
0x18021d8ce  lea     rcx, [rsp+210h+var_1E0]
0x18021d8d3  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x18021d8d8  nop
0x18021d8d9  jmp     loc_18021DD73
0x18021d8de  mov     [rbp+110h+var_110], r12
0x18021d8e2  mov     rcx, [rbp+110h+var_128]
0x18021d8e6  mov     rax, [rcx]
0x18021d8e9  lea     rdx, [rbp+110h+var_110]
0x18021d8ed  mov     rax, [rax+68h]
0x18021d8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021d8f6  mov     edi, eax
0x18021d8f8  test    eax, eax
0x18021d8fa  jns     loc_18021D98A
0x18021d900  mov     rcx, [rbp+118h]; this
0x18021d907  mov     r9d, eax; char *
0x18021d90a  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021d911  mov     edx, 1E56h; void *
0x18021d916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021d91b  nop
0x18021d91c  lea     rcx, [rbp+110h+var_110]; this
0x18021d920  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d925  nop
0x18021d926  lea     rcx, [rbp+110h+var_118]; this
0x18021d92a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d92f  nop
0x18021d930  lea     rcx, [rbp+110h+var_128]
0x18021d934  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d939  nop
0x18021d93a  lea     rcx, [rbp+110h+var_120]
0x18021d93e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021d943  nop
0x18021d944  lea     rcx, [rsp+210h+string]; this
0x18021d949  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021d94e  nop
0x18021d94f  mov     eax, dword ptr [rbp+110h+var_138]
0x18021d952  test    eax, eax
0x18021d954  jns     short loc_18021D985
0x18021d956  mov     rbx, [rbp+110h+var_140]
0x18021d95a  mov     dword ptr [rbp+110h+var_138+4], eax
0x18021d95d  mov     [rsp+210h+var_1E0], 4
0x18021d966  mov     [rsp+210h+var_1D8], r12d
  ... truncated ...
```
