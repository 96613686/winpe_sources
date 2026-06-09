# StorageItemHelpers::GetOrTryGetItemFromPathInProcAsync<Windows::Storage::IStorageFolder,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *>>(Windows::Internal::ICapturedCallerContext *,HSTRING__ *,bool,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *)

- ea: `0x180235bcc`
- end: `0x180236446`
- name: `??$GetOrTryGetItemFromPathInProcAsync@UIStorageFolder@Storage@Windows@@U?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@3@@StorageItemHelpers@@YAJPEAUICapturedCallerContext@Internal@Windows@@PEAUHSTRING__@@_NPEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@3@@Z`
- size: `2170`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1803f6e00`

## callees

- `0x18000d354`
- `0x18000d6cc`
- `0x180010110`
- `0x1800432f0`
- `0x180068eec`
- `0x1800c601c`
- `0x1800c6658`
- `0x1800dd190`
- `0x1801c03b4`
- `0x180235bcc`
- `0x180236bfc`
- `0x1802ae56c`
- `0x1803a4cb0`
- `0x1803c32c8`
- `0x1803c3780`
- `0x1803d2c48`
- `0x1803d6cf0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180235cfc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180235f09`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180235cfc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180235f09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180236083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18023608f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180236083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18023608f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180235cdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180235ef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180235cdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180235ef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180236077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18023609f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180236077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18023609f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802363db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180236398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802363db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180235f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180235f20`

## string_xrefs

- `0x180235c69`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180235d23`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180235dc8`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180235e66`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180235f4b`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180235fed`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802360bd`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18023610b`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180236209`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802362c5`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180235cd8`: `Windows.Foundation.Uri`
- `0x180235c0f`: `GetOrTryGetItemFromPathInProcAsync`

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
  INT32 v73; // [rsp+DCh] [rbp-24h] BYREF
  _BYTE v74[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING string1; // [rsp+F8h] [rbp-8h] BYREF
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
  string1 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v75 + 136LL))(v75, &string1);
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
    Windows::Internal::String::~String((Windows::Internal::String *)&string1);
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
  v73 = 0;
  WindowsCompareStringOrdinal(string1, (HSTRING)hstringHeader.Reserved.Reserved1, &v73);
  if ( v73 )
  {
    ApplicationPathAccess = -2147024735;
    v72 = -2147024735;
  }
  else
  {
    ApplicationPathAccess = v72;
  }
  if ( ApplicationPathAccess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E53,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)ApplicationPathAccess,
      v57);
    Windows::Internal::String::~String((Windows::Internal::String *)&string1);
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
    Windows::Internal::String::~String((Windows::Internal::String *)&string1);
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
    if ( string1 )
      WindowsDeleteString(string1);
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
  v43 = (*(__int64 (__fastcall **)(_QWORD, INT32 *, _BYTE *))(**(_QWORD **)v63 + 72LL))(*(_QWORD *)v63, &v73, v74);
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
    if ( string1 )
      WindowsDeleteString(string1);
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
  Windows::Internal::String::~String((Windows::Internal::String *)&string1);
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
0x180235bcc  push    rbp
0x180235bce  push    rbx
0x180235bcf  push    rsi
0x180235bd0  push    rdi
0x180235bd1  push    r12
0x180235bd3  push    r14
0x180235bd5  push    r15
0x180235bd7  lea     rbp, [rsp-0E0h]
0x180235bdf  sub     rsp, 1E0h
0x180235be6  mov     rax, cs:__security_cookie
0x180235bed  xor     rax, rsp
0x180235bf0  mov     [rbp+110h+var_40], rax
0x180235bf7  mov     rsi, rdx
0x180235bfa  mov     r15, rcx
0x180235bfd  mov     [rbp+110h+var_140], r9
0x180235c01  xor     r12d, r12d
0x180235c04  mov     [rsp+210h+var_1D0], r12b
0x180235c09  mov     r9b, 1
0x180235c0c  mov     r8, rcx
0x180235c0f  lea     rdx, aGetortrygetite_1; "GetOrTryGetItemFromPathInProcAsync"
0x180235c16  lea     rcx, [rbp+110h+var_100]
0x180235c1a  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBDPEAUICapturedCallerContext@Internal@Windows@@_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,Windows::Internal::ICapturedCallerContext *,bool)
0x180235c1f  nop
0x180235c20  mov     rax, [rbp+110h+var_140]
0x180235c24  mov     [rax], r12
0x180235c27  mov     dword ptr [rbp+110h+var_138], r12d
0x180235c2b  lea     rax, [rbp+110h+var_138]
0x180235c2f  mov     [rbp+110h+var_188], rax
0x180235c33  lea     rax, [rbp+110h+var_140]
0x180235c37  mov     [rbp+110h+var_180], rax
0x180235c3b  mov     [rbp+110h+var_178], 1
0x180235c3f  mov     [rsp+210h+string], r12
0x180235c44  mov     [rsp+210h+var_1B0], r12b
0x180235c49  lea     rdx, [rsp+210h+string]; this
0x180235c4e  mov     rcx, rsi; string
0x180235c51  call    ?TrimTrailingPathSeparators@StorageItemHelpers@@YAJPEAUHSTRING__@@PEAVString@Internal@Windows@@@Z; StorageItemHelpers::TrimTrailingPathSeparators(HSTRING__ *,Windows::Internal::String *)
0x180235c56  mov     edi, eax
0x180235c58  mov     dword ptr [rbp+110h+var_138], eax
0x180235c5b  test    eax, eax
0x180235c5d  jns     short loc_180235CC1
0x180235c5f  mov     rcx, [rbp+118h]; this
0x180235c66  mov     r9d, eax; char *
0x180235c69  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180235c70  mov     edx, 1E3Fh; void *
0x180235c75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180235c7a  nop
0x180235c7b  lea     rcx, [rsp+210h+string]; this
0x180235c80  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235c85  nop
0x180235c86  mov     eax, dword ptr [rbp+110h+var_138]
0x180235c89  test    eax, eax
0x180235c8b  jns     short loc_180235CBC
0x180235c8d  mov     rbx, [rbp+110h+var_140]
0x180235c91  mov     dword ptr [rbp+110h+var_138+4], eax
0x180235c94  mov     [rsp+210h+var_1E0], 4
0x180235c9d  mov     [rsp+210h+var_1D8], r12d
0x180235ca2  lea     rcx, [rbp+110h+var_138+4]
0x180235ca6  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x180235cab  mov     r9, rax
0x180235cae  mov     rdx, rbx
0x180235cb1  lea     rcx, [rsp+210h+var_1E0]
0x180235cb6  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x180235cbb  nop
0x180235cbc  jmp     loc_18023641A
0x180235cc1  mov     [rbp+110h+var_120], r12
0x180235cc5  mov     [rbp+110h+var_128], r12
0x180235cc9  lea     r9, [rsp+210h+hstringHeader]; string
0x180235cce  lea     r8, [rsp+210h+hstringHeader.Reserved+8]; hstringHeader
0x180235cd3  mov     edx, 16h; length
0x180235cd8  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180235cdf  call    cs:__imp_WindowsCreateStringReference
0x180235ce5  mov     r14d, 0C000000Dh
0x180235ceb  test    eax, eax
0x180235ced  jns     short loc_180235D02
0x180235cef  xor     r9d, r9d; lpArguments
0x180235cf2  xor     r8d, r8d; nNumberOfArguments
0x180235cf5  lea     edx, [r9+1]; dwExceptionFlags
0x180235cf9  mov     ecx, r14d; dwExceptionCode
0x180235cfc  call    cs:__imp_RaiseException
0x180235d02  lea     rdx, [rbp+110h+var_120]
0x180235d06  mov     rcx, qword ptr [rsp+210h+hstringHeader.Reserved]
0x180235d0b  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180235d10  mov     edi, eax
0x180235d12  mov     dword ptr [rbp+110h+var_138], eax
0x180235d15  test    eax, eax
0x180235d17  jns     short loc_180235D8F
0x180235d19  mov     rcx, [rbp+118h]; this
0x180235d20  mov     r9d, eax; char *
0x180235d23  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180235d2a  mov     edx, 1E45h; void *
0x180235d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180235d34  nop
0x180235d35  lea     rcx, [rbp+110h+var_128]
0x180235d39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235d3e  nop
0x180235d3f  lea     rcx, [rbp+110h+var_120]
0x180235d43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235d48  nop
0x180235d49  lea     rcx, [rsp+210h+string]; this
0x180235d4e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235d53  nop
0x180235d54  mov     eax, dword ptr [rbp+110h+var_138]
0x180235d57  test    eax, eax
0x180235d59  jns     short loc_180235D8A
0x180235d5b  mov     rbx, [rbp+110h+var_140]
0x180235d5f  mov     dword ptr [rbp+110h+var_138+4], eax
0x180235d62  mov     [rsp+210h+var_1E0], 4
0x180235d6b  mov     [rsp+210h+var_1D8], r12d
0x180235d70  lea     rcx, [rbp+110h+var_138+4]
0x180235d74  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x180235d79  mov     r9, rax
0x180235d7c  mov     rdx, rbx
0x180235d7f  lea     rcx, [rsp+210h+var_1E0]
0x180235d84  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x180235d89  nop
0x180235d8a  jmp     loc_18023641A
0x180235d8f  mov     rdi, [rbp+110h+var_120]
0x180235d93  mov     rax, [rdi]
0x180235d96  mov     rbx, [rax+30h]
0x180235d9a  lea     rcx, [rbp+110h+var_128]
0x180235d9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235da3  lea     r8, [rbp+110h+var_128]
0x180235da7  mov     rdx, rsi
0x180235daa  mov     rcx, rdi
0x180235dad  mov     rax, rbx
0x180235db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235db5  mov     edi, eax
0x180235db7  mov     dword ptr [rbp+110h+var_138], eax
0x180235dba  test    eax, eax
0x180235dbc  jns     short loc_180235E34
0x180235dbe  mov     rcx, [rbp+118h]; this
0x180235dc5  mov     r9d, eax; char *
0x180235dc8  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180235dcf  mov     edx, 1E48h; void *
0x180235dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180235dd9  nop
0x180235dda  lea     rcx, [rbp+110h+var_128]
0x180235dde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235de3  nop
0x180235de4  lea     rcx, [rbp+110h+var_120]
0x180235de8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235ded  nop
0x180235dee  lea     rcx, [rsp+210h+string]; this
0x180235df3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235df8  nop
0x180235df9  mov     eax, dword ptr [rbp+110h+var_138]
0x180235dfc  test    eax, eax
0x180235dfe  jns     short loc_180235E2F
0x180235e00  mov     rbx, [rbp+110h+var_140]
0x180235e04  mov     dword ptr [rbp+110h+var_138+4], eax
0x180235e07  mov     [rsp+210h+var_1E0], 4
0x180235e10  mov     [rsp+210h+var_1D8], r12d
0x180235e15  lea     rcx, [rbp+110h+var_138+4]
0x180235e19  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x180235e1e  mov     r9, rax
0x180235e21  mov     rdx, rbx
0x180235e24  lea     rcx, [rsp+210h+var_1E0]
0x180235e29  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x180235e2e  nop
0x180235e2f  jmp     loc_18023641A
0x180235e34  mov     [rbp+110h+string1], r12
0x180235e38  mov     rcx, [rbp+110h+var_128]
0x180235e3c  mov     rax, [rcx]
0x180235e3f  lea     rdx, [rbp+110h+string1]
0x180235e43  mov     rax, [rax+88h]
0x180235e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235e4f  mov     edi, eax
0x180235e51  mov     dword ptr [rbp+110h+var_138], eax
0x180235e54  test    eax, eax
0x180235e56  jns     loc_180235EDC
0x180235e5c  mov     rcx, [rbp+118h]; this
0x180235e63  mov     r9d, eax; char *
0x180235e66  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180235e6d  mov     edx, 1E4Ch; void *
0x180235e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180235e77  nop
0x180235e78  lea     rcx, [rbp+110h+string1]; this
0x180235e7c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235e81  nop
0x180235e82  lea     rcx, [rbp+110h+var_128]
0x180235e86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235e8b  nop
0x180235e8c  lea     rcx, [rbp+110h+var_120]
0x180235e90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235e95  nop
0x180235e96  lea     rcx, [rsp+210h+string]; this
0x180235e9b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235ea0  nop
0x180235ea1  mov     eax, dword ptr [rbp+110h+var_138]
0x180235ea4  test    eax, eax
0x180235ea6  jns     short loc_180235ED7
0x180235ea8  mov     rbx, [rbp+110h+var_140]
0x180235eac  mov     dword ptr [rbp+110h+var_138+4], eax
0x180235eaf  mov     [rsp+210h+var_1E0], 4
0x180235eb8  mov     [rsp+210h+var_1D8], r12d
0x180235ebd  lea     rcx, [rbp+110h+var_138+4]
0x180235ec1  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x180235ec6  mov     r9, rax
0x180235ec9  mov     rdx, rbx
0x180235ecc  lea     rcx, [rsp+210h+var_1E0]
0x180235ed1  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x180235ed6  nop
0x180235ed7  jmp     loc_18023641A
0x180235edc  lea     r9, [rsp+210h+hstringHeader]; string
0x180235ee1  lea     r8, [rsp+210h+hstringHeader.Reserved+8]; hstringHeader
0x180235ee6  mov     edx, 4; length
0x180235eeb  lea     rcx, aFile; "file"
0x180235ef2  call    cs:__imp_WindowsCreateStringReference
0x180235ef8  test    eax, eax
0x180235efa  jns     short loc_180235F0F
0x180235efc  xor     r9d, r9d; lpArguments
0x180235eff  xor     r8d, r8d; nNumberOfArguments
0x180235f02  lea     edx, [r9+1]; dwExceptionFlags
0x180235f06  mov     ecx, r14d; dwExceptionCode
0x180235f09  call    cs:__imp_RaiseException
0x180235f0f  mov     dword ptr [rbp+110h+var_138+4], r12d
0x180235f13  lea     r8, [rbp+110h+var_138+4]; result
0x180235f17  mov     rdx, qword ptr [rsp+210h+hstringHeader.Reserved]; string2
0x180235f1c  mov     rcx, [rbp+110h+string1]; string1
0x180235f20  call    cs:__imp_WindowsCompareStringOrdinal
0x180235f26  cmp     dword ptr [rbp+110h+var_138+4], r12d
0x180235f2a  jz      short loc_180235F36
0x180235f2c  mov     edi, 800700A1h
0x180235f31  mov     dword ptr [rbp+110h+var_138], edi
0x180235f34  jmp     short loc_180235F39
0x180235f36  mov     edi, dword ptr [rbp+110h+var_138]
0x180235f39  test    edi, edi
0x180235f3b  jns     loc_180235FC1
0x180235f41  mov     rcx, [rbp+118h]; this
0x180235f48  mov     r9d, edi; char *
0x180235f4b  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180235f52  mov     edx, 1E53h; void *
0x180235f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180235f5c  nop
0x180235f5d  lea     rcx, [rbp+110h+string1]; this
0x180235f61  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235f66  nop
0x180235f67  lea     rcx, [rbp+110h+var_128]
0x180235f6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235f70  nop
0x180235f71  lea     rcx, [rbp+110h+var_120]
0x180235f75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180235f7a  nop
0x180235f7b  lea     rcx, [rsp+210h+string]; this
0x180235f80  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180235f85  nop
0x180235f86  mov     eax, dword ptr [rbp+110h+var_138]
0x180235f89  test    eax, eax
0x180235f8b  jns     short loc_180235FBC
0x180235f8d  mov     rbx, [rbp+110h+var_140]
0x180235f91  mov     dword ptr [rbp+110h+var_138+4], eax
0x180235f94  mov     [rsp+210h+var_1E0], 4
0x180235f9d  mov     [rsp+210h+var_1D8], r12d
0x180235fa2  lea     rcx, [rbp+110h+var_138+4]
0x180235fa6  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
0x180235fab  mov     r9, rax
0x180235fae  mov     rdx, rbx
0x180235fb1  lea     rcx, [rsp+210h+var_1E0]
0x180235fb6  call    ??$MakeAsyncOperationHelper@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@PEAVStorageFolder@Storage@Windows@@VComTaskPoolHandler@Internal@4@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<CInProcStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<CInProcStorageItemResult<Windows::Storage::IStorageFolder>> *)
0x180235fbb  nop
0x180235fbc  jmp     loc_18023641A
0x180235fc1  mov     [rbp+110h+var_110], r12
0x180235fc5  mov     rcx, [rbp+110h+var_128]
0x180235fc9  mov     rax, [rcx]
0x180235fcc  lea     rdx, [rbp+110h+var_110]
0x180235fd0  mov     rax, [rax+68h]
0x180235fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235fd9  mov     edi, eax
0x180235fdb  test    eax, eax
0x180235fdd  jns     loc_18023606D
0x180235fe3  mov     rcx, [rbp+118h]; this
0x180235fea  mov     r9d, eax; char *
0x180235fed  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180235ff4  mov     edx, 1E56h; void *
0x180235ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180235ffe  nop
0x180235fff  lea     rcx, [rbp+110h+var_110]; this
0x180236003  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180236008  nop
0x180236009  lea     rcx, [rbp+110h+string1]; this
0x18023600d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180236012  nop
0x180236013  lea     rcx, [rbp+110h+var_128]
0x180236017  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18023601c  nop
0x18023601d  lea     rcx, [rbp+110h+var_120]
0x180236021  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180236026  nop
0x180236027  lea     rcx, [rsp+210h+string]; this
0x18023602c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180236031  nop
0x180236032  mov     eax, dword ptr [rbp+110h+var_138]
0x180236035  test    eax, eax
0x180236037  jns     short loc_180236068
0x180236039  mov     rbx, [rbp+110h+var_140]
0x18023603d  mov     dword ptr [rbp+110h+var_138+4], eax
0x180236040  mov     [rsp+210h+var_1E0], 4
0x180236049  mov     [rsp+210h+var_1D8], r12d
0x18023604e  lea     rcx, [rbp+110h+var_138+4]
0x180236052  call    ??$MakeOpLambda@$0A@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@V_lambda_cb5c69fd8282838e29b246066efeb553_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@@01@$$QEAV_lambda_cb5c69fd8282838e29b246066efeb553_@@@Z; Windows::Internal::MakeOpLambda<0,CInProcStorageItemResult<Windows::Storage::IStorageFolder>,_lambda_cb5c69fd8282838e29b246066efeb553_,>(_lambda_cb5c69fd8282838e29b246066efeb553_ &&)
  ... truncated ...
```
