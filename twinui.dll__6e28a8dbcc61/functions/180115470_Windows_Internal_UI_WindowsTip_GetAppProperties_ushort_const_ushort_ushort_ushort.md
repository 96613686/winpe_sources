# Windows::Internal::UI::WindowsTip::GetAppProperties(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180115470`
- end: `0x180115c30`
- name: `?GetAppProperties@WindowsTip@UI@Internal@Windows@@YAJPEBGPEAPEAG11@Z`
- size: `1984`
- prototype: `__int64 __fastcall(Windows::Internal::UI::WindowsTip *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180320bc8`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000c350`
- `0x180027cc8`
- `0x180027ee4`
- `0x180036250`
- `0x18003c5e4`
- `0x180052980`
- `0x1800542a8`
- `0x180115470`
- `0x180115c38`
- `0x18013d330`
- `0x180246f40`
- `0x18031b318`
- `0x18031b390`
- `0x18031b648`
- `0x180320a78`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801157ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011580b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801159b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801159f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115a17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115b70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801157ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011580b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801159b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801159f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115a17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115b70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180115bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011582b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180115a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180115ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011582b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180115a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180115ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180115b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180115b22`

## string_xrefs

- `0x180115ab7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::UI::WindowsTip::GetAppProperties(
        Windows::Internal::UI::WindowsTip *this,
        unsigned __int16 *a2,
        LPVOID *a3,
        unsigned __int16 **a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, __int64 *); // rbx
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, __int64 *); // rdi
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  int v33; // eax
  PCWSTR StringRawBuffer; // rax
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HSTRING *); // rbx
  int v46; // eax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, HSTRING *); // rbx
  int v49; // eax
  PCWSTR v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rax
  int v53; // eax
  __int64 v54; // rax
  unsigned __int16 *Reserved1; // rax
  int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+20h] [rbp-E0h]
  __int64 v59; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v61; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v62; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v65; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+68h] [rbp-98h] BYREF
  int v67; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v68; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v69; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-58h]
  __int64 v75; // [rsp+B0h] [rbp-50h]
  __int64 v76; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v77; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-30h]
  __int128 v79; // [rsp+D8h] [rbp-28h]
  __int64 v80; // [rsp+E8h] [rbp-18h]
  _OWORD v81[3]; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+120h] [rbp+20h] BYREF
  __int64 v83; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  pv = this;
  *(_QWORD *)a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v76 = 0;
  v83 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"WindowsInternal.Shell.UnifiedTile.UnifiedTileManager",
    0x35u,
    0x34u);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(
         v83,
         &v76);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v59 = 0;
    v9 = v76;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v76 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    v11 = v10(v9, 3, 1, &v59);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 827;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v11,
        v57);
LABEL_6:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
      goto LABEL_63;
    }
    v11 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>>(v59);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 828;
      goto LABEL_5;
    }
    v61 = 0;
    v13 = v59;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    v15 = v14(v13, &v61);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33F,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v15,
        v57);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      goto LABEL_6;
    }
    v62 = 0;
    v16 = v61;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 80LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
    v18 = v17(v16, &v62);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 834;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v18,
        v57);
LABEL_15:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
      goto LABEL_11;
    }
    v18 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
            v62,
            0xFFFFFFFFLL);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 835;
      goto LABEL_14;
    }
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v83 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"WindowsInternal.Shell.UnifiedTile.PackagedUnifiedTileIdentifier",
      0x40u,
      0x3Fu);
    v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>(
            v83,
            &v65);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = 841;
LABEL_20:
      v22 = (unsigned int)v20;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)v22,
        v57);
LABEL_22:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      goto LABEL_15;
    }
    v23 = v65;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &pv);
    v20 = v24(v23, *(_QWORD *)(v25 + 24), &v64);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = 843;
      goto LABEL_20;
    }
    v26 = v61;
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v61 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v20 = v27(v26, v64, &v63);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = 844;
      goto LABEL_20;
    }
    v28 = v63;
    if ( !v63 )
    {
      v8 = -2147023728;
      v22 = 2147943568LL;
      v21 = 845;
      goto LABEL_21;
    }
    v66 = 0;
    v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v30 = v29(v28, &v66);
    v8 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x350,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v30,
        v57);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      goto LABEL_22;
    }
    string = 0;
    v31 = v66;
    v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v66 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v33 = v32(v31, &string);
    v8 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x353,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v33,
        v57);
LABEL_34:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_31;
    }
    v73 = 0;
    v74 = 0;
    v75 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v35 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &v73,
            StringRawBuffer,
            -1);
    v8 = v35;
    if ( v35 >= 0 )
    {
      v67 = 0;
      v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v66 + 72LL))(v66, &v67);
      v8 = v35;
      if ( v35 >= 0 )
      {
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        v58 = BYTE2(v67);
        v37 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                &hstringHeader,
                L"#%02x%02x%02x%02x",
                (unsigned __int8)v67,
                BYTE1(v67));
        v8 = v37;
        if ( v37 >= 0 )
        {
          v70 = 0;
          v38 = v63;
          v39 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 104LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
          v40 = v39(v38, &v70);
          v8 = v40;
          if ( v40 >= 0 )
          {
            v71 = 0;
            v41 = v66;
            v42 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
            v43 = v42(v41, &v71);
            v8 = v43;
            if ( v43 >= 0 )
            {
              v68 = 0;
              v44 = v71;
              v45 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v71 + 64LL);
              WindowsDeleteString(0);
              v68 = 0;
              v46 = v45(v44, &v68);
              v8 = v46;
              if ( v46 >= 0 )
              {
                v69 = 0;
                v47 = v70;
                v48 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v70 + 56LL);
                WindowsDeleteString(0);
                v69 = 0;
                v49 = v48(v47, &v69);
                v8 = v49;
                if ( v49 >= 0 )
                {
                  v77 = 0;
                  v78 = 0;
                  v79 = 0;
                  v80 = 0;
                  memset(v81, 0, sizeof(v81));
                  v50 = WindowsGetStringRawBuffer(v69, 0);
                  *(_WORD *)((char *)&v80 + 5) = 1;
                  v51 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                          v81,
                          v50,
                          -1);
                  if ( v51 < 0 )
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x30,
                      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
                      (const char *)(unsigned int)v51,
                      v58);
                  HIBYTE(v80) = 1;
                  pv = 0;
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &pv,
                    0);
                  v52 = WindowsGetStringRawBuffer(v68, 0);
                  v53 = ShellMRTHelper::MRTHelperBase::ResolvePath(
                          (ShellMRTHelper::MRTHelperBase *)&v77,
                          v52,
                          (unsigned __int16 **)&pv);
                  v8 = v53;
                  if ( v53 >= 0 )
                  {
                    v54 = v73;
                    v73 = 0;
                    v75 = 0;
                    v74 = 0;
                    *(_QWORD *)a2 = v54;
                    Reserved1 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
                    memset(&hstringHeader, 0, sizeof(hstringHeader));
                    *a4 = Reserved1;
                    *a3 = pv;
                    ShellMRTHelper::MRTHelperBase::~MRTHelperBase((ShellMRTHelper::MRTHelperBase *)&v77);
                    WindowsDeleteString(v69);
                    v69 = 0;
                    WindowsDeleteString(v68);
                    v68 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
                    v8 = 0;
                    goto LABEL_63;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x370,
                    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                    (const char *)(unsigned int)v53,
                    v58);
                  if ( pv )
                    CoTaskMemFree(pv);
                  ShellMRTHelper::MRTHelperBase::~MRTHelperBase((ShellMRTHelper::MRTHelperBase *)&v77);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x369,
                    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                    (const char *)(unsigned int)v49,
                    v58);
                }
                WindowsDeleteString(v69);
                v69 = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x366,
                  (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                  (const char *)(unsigned int)v46,
                  v58);
              }
              WindowsDeleteString(v68);
              v68 = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x363,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v43,
                v58);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x35F,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v40,
              v58);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35C,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v37,
            v58);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        goto LABEL_38;
      }
      v36 = 857;
    }
    else
    {
      v36 = 854;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
      (const char *)(unsigned int)v35,
      v57);
LABEL_38:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x338,
    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
    (const char *)(unsigned int)v7,
    v57);
LABEL_63:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  return v8;
}

```

## disassembly

```asm
0x180115470  push    rbp
0x180115472  push    rbx
0x180115473  push    rsi
0x180115474  push    rdi
0x180115475  push    r12
0x180115477  push    r14
0x180115479  push    r15
0x18011547b  lea     rbp, [rsp-50h]
0x180115480  sub     rsp, 150h
0x180115487  mov     rax, cs:__security_cookie
0x18011548e  xor     rax, rsp
0x180115491  mov     [rbp+80h+var_40], rax
0x180115495  mov     r15, r9
0x180115498  mov     r14, r8
0x18011549b  mov     rsi, rdx
0x18011549e  mov     [rbp+80h+pv], rcx
0x1801154a2  xor     r12d, r12d
0x1801154a5  mov     [rdx], r12
0x1801154a8  mov     [r8], r12
0x1801154ab  mov     [r9], r12
0x1801154ae  mov     [rbp+80h+var_C8], r12
0x1801154b2  mov     [rbp+80h+var_48], r12
0x1801154b6  lea     r9d, [r12+34h]; unsigned int
0x1801154bb  lea     r8d, [r12+35h]; unsigned int
0x1801154c0  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_UnifiedTileManager@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Unifi"...
0x1801154c7  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x1801154cb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801154d0  lea     rdx, [rbp+80h+var_C8]
0x1801154d4  mov     rcx, [rbp+80h+var_48]
0x1801154d8  call    ??$GetActivationFactory@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>)
0x1801154dd  mov     ebx, eax
0x1801154df  test    eax, eax
0x1801154e1  jns     short loc_180115503
0x1801154e3  mov     rcx, [rbp+88h]; this
0x1801154ea  mov     r9d, eax; char *
0x1801154ed  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1801154f4  mov     edx, 338h; void *
0x1801154f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801154fe  jmp     loc_180115C07
0x180115503  mov     [rsp+180h+var_150], r12
0x180115508  mov     rdi, [rbp+80h+var_C8]
0x18011550c  mov     rax, [rdi]
0x18011550f  mov     rbx, [rax+30h]
0x180115513  lea     rcx, [rsp+180h+var_150]
0x180115518  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011551d  lea     r9, [rsp+180h+var_150]
0x180115522  mov     edx, 3
0x180115527  lea     r8d, [rdx-2]
0x18011552b  mov     rcx, rdi
0x18011552e  mov     rax, rbx
0x180115531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115536  mov     ebx, eax
0x180115538  test    eax, eax
0x18011553a  jns     short loc_180115566
0x18011553c  mov     edx, 33Bh; void *
0x180115541  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180115548  mov     r9d, eax; char *
0x18011554b  mov     rcx, [rbp+88h]; this
0x180115552  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115557  lea     rcx, [rsp+180h+var_150]
0x18011555c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180115561  jmp     loc_180115C07
0x180115566  mov     rcx, [rsp+180h+var_150]
0x18011556b  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>>(Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *> *,tagCOWAIT_FLAGS,void *)
0x180115570  mov     ebx, eax
0x180115572  test    eax, eax
0x180115574  jns     short loc_18011557D
0x180115576  mov     edx, 33Ch
0x18011557b  jmp     short loc_180115541
0x18011557d  mov     [rsp+180h+var_140], r12
0x180115582  mov     rdi, [rsp+180h+var_150]
0x180115587  mov     rax, [rdi]
0x18011558a  mov     rbx, [rax+40h]
0x18011558e  lea     rcx, [rsp+180h+var_140]
0x180115593  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180115598  lea     rdx, [rsp+180h+var_140]
0x18011559d  mov     rcx, rdi
0x1801155a0  mov     rax, rbx
0x1801155a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801155a8  mov     ebx, eax
0x1801155aa  test    eax, eax
0x1801155ac  jns     short loc_1801155D5
0x1801155ae  mov     rcx, [rbp+88h]; this
0x1801155b5  mov     r9d, eax; char *
0x1801155b8  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1801155bf  mov     edx, 33Fh; void *
0x1801155c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801155c9  lea     rcx, [rsp+180h+var_140]
0x1801155ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801155d3  jmp     short loc_180115557
0x1801155d5  mov     [rsp+180h+var_138], r12
0x1801155da  mov     rdi, [rsp+180h+var_140]
0x1801155df  mov     rax, [rdi]
0x1801155e2  mov     rbx, [rax+50h]
0x1801155e6  lea     rcx, [rsp+180h+var_138]
0x1801155eb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801155f0  lea     rdx, [rsp+180h+var_138]
0x1801155f5  mov     rcx, rdi
0x1801155f8  mov     rax, rbx
0x1801155fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115600  mov     ebx, eax
0x180115602  test    eax, eax
0x180115604  jns     short loc_18011562D
0x180115606  mov     edx, 342h; void *
0x18011560b  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180115612  mov     r9d, eax; char *
0x180115615  mov     rcx, [rbp+88h]; this
0x18011561c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115621  lea     rcx, [rsp+180h+var_138]
0x180115626  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011562b  jmp     short loc_1801155C9
0x18011562d  or      edx, 0FFFFFFFFh
0x180115630  mov     rcx, [rsp+180h+var_138]
0x180115635  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x18011563a  mov     ebx, eax
0x18011563c  test    eax, eax
0x18011563e  jns     short loc_180115647
0x180115640  mov     edx, 343h
0x180115645  jmp     short loc_18011560B
0x180115647  mov     [rsp+180h+var_130], r12
0x18011564c  mov     [rsp+180h+var_128], r12
0x180115651  mov     [rsp+180h+var_120], r12
0x180115656  mov     [rbp+80h+var_48], r12
0x18011565a  mov     r9d, 3Fh ; '?'; unsigned int
0x180115660  lea     r8d, [r9+1]; unsigned int
0x180115664  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_PackagedUnifiedTileIdentifier@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Packa"...
0x18011566b  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x18011566f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180115674  lea     rdx, [rsp+180h+var_120]
0x180115679  mov     rcx, [rbp+80h+var_48]
0x18011567d  call    ??$GetActivationFactory@V?$ComPtr@UIPackagedUnifiedTileIdentifierFactory@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifierFactory@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>)
0x180115682  mov     ebx, eax
0x180115684  test    eax, eax
0x180115686  jns     short loc_1801156C6
0x180115688  mov     edx, 349h; void *
0x18011568d  mov     r9d, eax; char *
0x180115690  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180115697  mov     rcx, [rbp+88h]; this
0x18011569e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801156a3  lea     rcx, [rsp+180h+var_120]
0x1801156a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801156ad  lea     rcx, [rsp+180h+var_128]
0x1801156b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801156b7  lea     rcx, [rsp+180h+var_130]
0x1801156bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801156c1  jmp     loc_180115621
0x1801156c6  mov     rdi, [rsp+180h+var_120]
0x1801156cb  mov     rax, [rdi]
0x1801156ce  mov     rbx, [rax+30h]
0x1801156d2  lea     rcx, [rsp+180h+var_128]
0x1801156d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801156dc  lea     rdx, [rbp+80h+pv]
0x1801156e0  lea     rcx, [rbp+80h+hstringHeader]
0x1801156e4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801156e9  lea     r8, [rsp+180h+var_128]
0x1801156ee  mov     rdx, [rax+18h]
0x1801156f2  mov     rcx, rdi
0x1801156f5  mov     rax, rbx
0x1801156f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801156fd  mov     ebx, eax
0x1801156ff  test    eax, eax
0x180115701  jns     short loc_18011570A
0x180115703  mov     edx, 34Bh
0x180115708  jmp     short loc_18011568D
0x18011570a  mov     rdi, [rsp+180h+var_140]
0x18011570f  mov     rax, [rdi]
0x180115712  mov     rbx, [rax+48h]
0x180115716  lea     rcx, [rsp+180h+var_130]
0x18011571b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180115720  lea     r8, [rsp+180h+var_130]
0x180115725  mov     rdx, [rsp+180h+var_128]
0x18011572a  mov     rcx, rdi
0x18011572d  mov     rax, rbx
0x180115730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115735  mov     ebx, eax
0x180115737  test    eax, eax
0x180115739  jns     short loc_180115745
0x18011573b  mov     edx, 34Ch
0x180115740  jmp     loc_18011568D
0x180115745  mov     rbx, [rsp+180h+var_130]
0x18011574a  test    rbx, rbx
0x18011574d  jnz     short loc_180115761
0x18011574f  mov     ebx, 80070490h
0x180115754  mov     r9d, ebx
0x180115757  mov     edx, 34Dh
0x18011575c  jmp     loc_180115690
0x180115761  mov     [rsp+180h+var_118], r12
0x180115766  mov     rax, [rbx]
0x180115769  mov     rdi, [rax+38h]
0x18011576d  lea     rcx, [rsp+180h+var_118]
0x180115772  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180115777  lea     rdx, [rsp+180h+var_118]
0x18011577c  mov     rcx, rbx
0x18011577f  mov     rax, rdi
0x180115782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115787  mov     ebx, eax
0x180115789  test    eax, eax
0x18011578b  jns     short loc_1801157B7
0x18011578d  mov     rcx, [rbp+88h]; this
0x180115794  mov     r9d, eax; char *
0x180115797  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18011579e  mov     edx, 350h; void *
0x1801157a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801157a8  lea     rcx, [rsp+180h+var_118]
0x1801157ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801157b2  jmp     loc_1801156A3
0x1801157b7  mov     [rsp+180h+string], r12
0x1801157bc  mov     rdi, [rsp+180h+var_118]
0x1801157c1  mov     rax, [rdi]
0x1801157c4  mov     rbx, [rax+30h]
0x1801157c8  xor     ecx, ecx; string
0x1801157ca  call    cs:__imp_WindowsDeleteString
0x1801157d0  mov     [rsp+180h+string], r12
0x1801157d5  lea     rdx, [rsp+180h+string]
0x1801157da  mov     rcx, rdi
0x1801157dd  mov     rax, rbx
0x1801157e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801157e5  mov     ebx, eax
0x1801157e7  test    eax, eax
0x1801157e9  jns     short loc_180115818
0x1801157eb  mov     rcx, [rbp+88h]; this
0x1801157f2  mov     r9d, eax; char *
0x1801157f5  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1801157fc  mov     edx, 353h; void *
0x180115801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115806  mov     rcx, [rsp+180h+string]; string
0x18011580b  call    cs:__imp_WindowsDeleteString
0x180115811  mov     [rsp+180h+string], r12
0x180115816  jmp     short loc_1801157A8
0x180115818  mov     [rbp+80h+var_E0], r12
0x18011581c  mov     [rbp+80h+var_D8], r12
0x180115820  mov     [rbp+80h+var_D0], r12
0x180115824  xor     edx, edx; length
0x180115826  mov     rcx, [rsp+180h+string]; string
0x18011582b  call    cs:__imp_WindowsGetStringRawBuffer
0x180115831  or      r8, 0FFFFFFFFFFFFFFFFh
0x180115835  mov     rdx, rax
0x180115838  lea     rcx, [rbp+80h+var_E0]
0x18011583c  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180115841  mov     ebx, eax
0x180115843  test    eax, eax
0x180115845  jns     short loc_18011586D
0x180115847  mov     edx, 356h; void *
0x18011584c  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180115853  mov     r9d, eax; char *
0x180115856  mov     rcx, [rbp+88h]; this
0x18011585d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115862  lea     rcx, [rbp+80h+var_E0]
0x180115866  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18011586b  jmp     short loc_180115806
0x18011586d  mov     [rsp+180h+var_110], r12d
0x180115872  mov     rcx, [rsp+180h+var_118]
0x180115877  mov     rax, [rcx]
0x18011587a  lea     rdx, [rsp+180h+var_110]
0x18011587f  mov     rax, [rax+48h]
0x180115883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115888  mov     ebx, eax
0x18011588a  test    eax, eax
0x18011588c  jns     short loc_180115895
0x18011588e  mov     edx, 359h
0x180115893  jmp     short loc_18011584C
0x180115895  mov     qword ptr [rbp+80h+hstringHeader.Reserved], r12
0x180115899  mov     qword ptr [rbp+80h+hstringHeader.Reserved+8], r12
0x18011589d  mov     qword ptr [rbp+80h+hstringHeader.Reserved+10h], r12
0x1801158a1  movzx   eax, byte ptr [rsp+180h+var_110+3]
0x1801158a6  movzx   ecx, byte ptr [rsp+180h+var_110+2]
0x1801158ab  movzx   r9d, byte ptr [rsp+180h+var_110+1]
0x1801158b1  movzx   r8d, byte ptr [rsp+180h+var_110]
0x1801158b7  mov     [rsp+180h+var_158], eax
0x1801158bb  mov     [rsp+180h+var_160], ecx; int
0x1801158bf  lea     rdx, a02x02x02x02x; "#%02x%02x%02x%02x"
0x1801158c6  lea     rcx, [rbp+80h+hstringHeader]
0x1801158ca  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801158cf  mov     ebx, eax
0x1801158d1  test    eax, eax
0x1801158d3  jns     short loc_1801158FE
0x1801158d5  mov     rcx, [rbp+88h]; this
0x1801158dc  mov     r9d, eax; char *
0x1801158df  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1801158e6  mov     edx, 35Ch; void *
0x1801158eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801158f0  lea     rcx, [rbp+80h+hstringHeader]
0x1801158f4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801158f9  jmp     loc_180115862
0x1801158fe  mov     [rbp+80h+var_F8], r12
0x180115902  mov     rdi, [rsp+180h+var_130]
0x180115907  mov     rax, [rdi]
0x18011590a  mov     rbx, [rax+68h]
0x18011590e  lea     rcx, [rbp+80h+var_F8]
0x180115912  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180115917  lea     rdx, [rbp+80h+var_F8]
0x18011591b  mov     rcx, rdi
0x18011591e  mov     rax, rbx
0x180115921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115926  mov     ebx, eax
0x180115928  test    eax, eax
0x18011592a  jns     short loc_180115952
0x18011592c  mov     rcx, [rbp+88h]; this
0x180115933  mov     r9d, eax; char *
0x180115936  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
  ... truncated ...
```
