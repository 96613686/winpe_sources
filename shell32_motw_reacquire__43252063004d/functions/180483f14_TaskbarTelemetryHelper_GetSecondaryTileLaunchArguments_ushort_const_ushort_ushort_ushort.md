# TaskbarTelemetryHelper::GetSecondaryTileLaunchArguments(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180483f14`
- end: `0x18048482e`
- name: `?GetSecondaryTileLaunchArguments@TaskbarTelemetryHelper@@YAJPEBGPEAPEAG11@Z`
- size: `2330`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801b46c8`
- `0x180486038`
- `0x1804876e4`

## callees

- `0x18000f6cc`
- `0x180026890`
- `0x180038608`
- `0x180043ac0`
- `0x18007b944`
- `0x18009d460`
- `0x1800b83a8`
- `0x1800f2a30`
- `0x180249490`
- `0x18048161c`
- `0x180482ba4`
- `0x180483f14`
- `0x180484eb8`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180484478`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804844ac`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180484478`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804844ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804844fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180484539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804845b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180484658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18048469a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180484772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804844fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180484539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804845b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180484658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18048469a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180484772`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1804843bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1804843bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180484330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180484371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804845e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804846c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18048479f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180484330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180484371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804845e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804846c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18048479f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180483ffd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180483ffd`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x1804843ce`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x1804843ce`

## string_xrefs

- `0x180483fa9`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180484016`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x18048406b`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x1804840d0`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180484165`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180484221`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x1804842aa`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180484303`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x18048435c`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x1804844e6`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180484525`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x1804845a2`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180484643`: `shell\inc\TaskbarTelemetryHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskbarTelemetryHelper::GetSecondaryTileLaunchArguments(
        wchar_t *Str,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v8; // rsi
  unsigned __int16 **v9; // r9
  int AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier; // eax
  unsigned int v11; // ebx
  __int64 v12; // rbx
  int ActivationFactory; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD); // rbx
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, _QWORD); // rbx
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64, __int64 *); // rbx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, _QWORD); // rbx
  int v37; // eax
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v39)(_QWORD, GUID *, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, HSTRING *); // rbx
  int v43; // eax
  PVOID Reserved1; // r14
  unsigned __int16 *v45; // rdi
  const WCHAR *StringRawBuffer; // rax
  LPWSTR *v47; // rbx
  LPWSTR v48; // rax
  LPWSTR v49; // rcx
  int v50; // edx
  int v51; // r8d
  int v52; // eax
  unsigned int v53; // esi
  const wchar_t *v54; // rcx
  unsigned __int64 v55; // rax
  wchar_t *v56; // rax
  __int64 v57; // rcx
  const wchar_t *v58; // rsi
  wchar_t *v59; // rax
  int v60; // eax
  int v61; // eax
  char *v62; // r9
  int v63; // ecx
  int v64; // r8d
  int v65; // eax
  int v67; // [rsp+20h] [rbp-B9h]
  unsigned __int16 *v68; // [rsp+30h] [rbp-A9h] BYREF
  unsigned __int16 v69[4]; // [rsp+38h] [rbp-A1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-99h] BYREF
  __int64 v71; // [rsp+58h] [rbp-81h]
  unsigned __int16 *v72; // [rsp+60h] [rbp-79h] BYREF
  __int64 v73; // [rsp+68h] [rbp-71h]
  __int64 v74; // [rsp+70h] [rbp-69h]
  unsigned __int16 *v75; // [rsp+78h] [rbp-61h] BYREF
  __int64 v76; // [rsp+80h] [rbp-59h]
  __int64 v77; // [rsp+88h] [rbp-51h]
  unsigned __int16 *v78; // [rsp+90h] [rbp-49h] BYREF
  __int64 v79; // [rsp+98h] [rbp-41h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v82; // [rsp+B0h] [rbp-29h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-19h] BYREF
  __int64 (__fastcall ***v85)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp-11h] BYREF
  __int64 v86; // [rsp+D0h] [rbp-9h] BYREF
  int pNumArgs; // [rsp+D8h] [rbp-1h] BYREF
  int v88; // [rsp+DCh] [rbp+3h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v8 = 0;
  *(_QWORD *)a2 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( !Str || !SecondaryTileIdentifierHelpers::IsFullyQualifiedTileIdentifier(Str, a2) )
    return 2147943569LL;
  *(_QWORD *)v69 = 0;
  v68 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v68,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v69,
    0);
  AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier = SecondaryTileIdentifierHelpers::GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier(
                                                                 Str,
                                                                 v69,
                                                                 &v68,
                                                                 v9);
  v11 = AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier;
  if ( AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier,
      v67);
LABEL_77:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v68);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v69);
    return v11;
  }
  v80 = 0;
  v71 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Tiles.TileStore",
    0x21u,
    0x20u);
  v12 = v71;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40, &v80);
  v11 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)ActivationFactory,
      v67);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    goto LABEL_77;
  }
  v81 = 0;
  v14 = v80;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  v16 = v15(v14, 0, &v81);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v16,
      v67);
LABEL_10:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    goto LABEL_7;
  }
  v79 = 0;
  v71 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Tiles.TileQueryFilter",
    0x27u,
    0x26u);
  v17 = v71;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  v18 = Windows::Foundation::ActivateInstance<Windows::Internal::Tiles::ITileQueryFilter>(v17, &v79);
  v11 = v18;
  if ( v18 < 0 )
  {
    v19 = 45;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v18,
      v67);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    goto LABEL_10;
  }
  v20 = v79;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v79 + 88LL);
  v78 = *(unsigned __int16 **)v69;
  v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v78);
  v18 = v21(v20, *(_QWORD *)(v22 + 24));
  v11 = v18;
  if ( v18 < 0 )
  {
    v19 = 47;
    goto LABEL_13;
  }
  v82 = 0;
  v23 = v79;
  v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
  v25 = v24(v23, &v82);
  v11 = v25;
  if ( v25 < 0 )
  {
    v26 = 50;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v25,
      v67);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    goto LABEL_14;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 104LL))(v82, 1);
  v11 = v25;
  if ( v25 < 0 )
  {
    v26 = 52;
    goto LABEL_19;
  }
  v27 = v79;
  v28 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v79 + 104LL);
  v78 = v68;
  v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v78);
  v25 = v28(v27, *(_QWORD *)(v29 + 24));
  v11 = v25;
  if ( v25 < 0 )
  {
    v26 = 53;
    goto LABEL_19;
  }
  v84 = 0;
  v30 = v81;
  v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v81 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  v32 = v31(v30, 0, v79, &v84);
  v11 = v32;
  if ( v32 < 0 )
  {
    v33 = 56;
LABEL_27:
    v34 = (unsigned int)v32;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)v34,
      v67);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    goto LABEL_20;
  }
  v88 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v84 + 56LL))(v84, &v88);
  v11 = v32;
  if ( v32 < 0 )
  {
    v33 = 59;
    goto LABEL_27;
  }
  if ( v88 != 1 )
  {
    v11 = -2147024883;
    v34 = 2147942413LL;
    v33 = 60;
    goto LABEL_28;
  }
  v85 = 0;
  v35 = v84;
  v36 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v84 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  v37 = v36(v35, 0, &v85);
  v11 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v37,
      v67);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    goto LABEL_29;
  }
  v86 = 0;
  v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v85;
  v39 = **v85;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  v40 = v39(v38, &GUID_f10ff47a_c551_404d_9a7f_379d7d40b973, &v86);
  v11 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v40,
      v67);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    goto LABEL_36;
  }
  string = 0;
  v41 = v86;
  v42 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v86 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v43 = v42(v41, &string);
  v11 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v43,
      v67);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_39;
  }
  Reserved1 = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  v45 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  pNumArgs = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v47 = CommandLineToArgvW(StringRawBuffer, &pNumArgs);
  if ( !v47 )
    goto LABEL_73;
  while ( (int)v45 < pNumArgs )
  {
    v48 = v47[(int)v45];
    v49 = v48;
    do
    {
      v50 = *(LPWSTR)((char *)v49 + (char *)L"-url" - (char *)v48);
      v51 = *v49 - v50;
      if ( v51 )
        break;
      ++v49;
    }
    while ( v50 );
    if ( v51 )
    {
      v62 = (char *)((char *)L"-tbPinSource" - (char *)v48);
      do
      {
        v63 = *(unsigned __int16 *)&v62[(_QWORD)v48];
        v64 = *v48 - v63;
        if ( v64 )
          break;
        ++v48;
      }
      while ( v63 );
      if ( !v64 && (int)v45 + 1 < pNumArgs )
      {
        v65 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v75,
                v47[(int)v45 + 1],
                -1);
        v53 = v65;
        if ( v65 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
            (const char *)(unsigned int)v65,
            v67);
          LocalFree(v47);
          goto LABEL_69;
        }
      }
    }
    else if ( (int)v45 + 2 < pNumArgs )
    {
      v52 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &hstringHeader,
              v47[(int)v45 + 2],
              -1);
      v53 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
          (const char *)(unsigned int)v52,
          v67);
        LocalFree(v47);
        goto LABEL_69;
      }
      v54 = v47[(int)v45 + 2];
      v55 = -1;
      do
        ++v55;
      while ( v54[v55] );
      if ( v55 > 1 )
      {
        v56 = wcsstr(v54, L"msSrc=");
        if ( v56 )
        {
          v57 = -1;
          do
            ++v57;
          while ( aMssrc[v57] );
          v58 = &v56[v57];
          v59 = wcsstr(v58, L"&");
          if ( v59 )
          {
            v60 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    &v72,
                    v58,
                    v59 - v58);
            v53 = v60;
            if ( v60 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6C,
                (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
                (const char *)(unsigned int)v60,
                v67);
              LocalFree(v47);
LABEL_69:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v72);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
              v11 = v53;
              goto LABEL_77;
            }
          }
          else
          {
            v61 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    &v72,
                    v58,
                    -1);
            v53 = v61;
            if ( v61 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x70,
                (unsigned int)"shell\\inc\\TaskbarTelemetryHelper.h",
                (const char *)(unsigned int)v61,
                v67);
              LocalFree(v47);
              goto LABEL_69;
            }
          }
        }
      }
    }
    LODWORD(v45) = (_DWORD)v45 + 1;
  }
  Reserved1 = hstringHeader.Reserved.Reserved1;
  v45 = v72;
  v8 = v75;
  if ( !hstringHeader.Reserved.Reserved1 )
  {
LABEL_73:
    if ( !v45 && !v8 )
    {
      if ( v47 )
        LocalFree(v47);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v72);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
      v11 = -2147023727;
      goto LABEL_77;
    }
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  *(_QWORD *)a2 = Reserved1;
  v72 = 0;
  v74 = 0;
  v73 = 0;
  *a3 = v45;
  v75 = 0;
  v77 = 0;
  v76 = 0;
  *a4 = v8;
  if ( v47 )
    LocalFree(v47);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v72);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v68);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v69);
  return 0;
}

```

## disassembly

```asm
0x180483f14  push    rbp
0x180483f16  push    rbx
0x180483f17  push    rsi
0x180483f18  push    rdi
0x180483f19  push    r12
0x180483f1b  push    r13
0x180483f1d  push    r14
0x180483f1f  push    r15
0x180483f21  lea     rbp, [rsp-1Fh]
0x180483f26  sub     rsp, 0F8h
0x180483f2d  mov     rax, cs:__security_cookie
0x180483f34  xor     rax, rsp
0x180483f37  mov     [rbp+57h+var_50], rax
0x180483f3b  mov     r13, r9
0x180483f3e  mov     r12, r8
0x180483f41  mov     r15, rdx
0x180483f44  mov     rbx, rcx
0x180483f47  xor     esi, esi
0x180483f49  mov     [rdx], rsi
0x180483f4c  mov     [r8], rsi
0x180483f4f  mov     [r9], rsi
0x180483f52  test    rcx, rcx
0x180483f55  jz      loc_180484808
0x180483f5b  call    ?IsFullyQualifiedTileIdentifier@SecondaryTileIdentifierHelpers@@YA_NPEBG@Z; SecondaryTileIdentifierHelpers::IsFullyQualifiedTileIdentifier(ushort const *)
0x180483f60  test    al, al
0x180483f62  jz      loc_180484808
0x180483f68  mov     qword ptr [rsp+130h+var_F8], rsi
0x180483f6d  mov     [rsp+130h+var_100], rsi
0x180483f72  xor     edx, edx
0x180483f74  lea     rcx, [rsp+130h+var_100]
0x180483f79  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180483f7e  xor     edx, edx
0x180483f80  lea     rcx, [rsp+130h+var_F8]
0x180483f85  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180483f8a  lea     r8, [rsp+130h+var_100]; unsigned __int16 **
0x180483f8f  lea     rdx, [rsp+130h+var_F8]; unsigned __int16 *
0x180483f94  mov     rcx, rbx; Str
0x180483f97  call    ?GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier@SecondaryTileIdentifierHelpers@@YAJPEBGPEAPEAG1@Z; SecondaryTileIdentifierHelpers::GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier(ushort const *,ushort * *,ushort * *)
0x180483f9c  mov     ebx, eax
0x180483f9e  test    eax, eax
0x180483fa0  jns     short loc_180483FBD
0x180483fa2  mov     rcx, [rbp+5Fh]; this
0x180483fa6  mov     r9d, eax; char *
0x180483fa9  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180483fb0  lea     edx, [rsi+20h]; void *
0x180483fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180483fb8  jmp     loc_18048471D
0x180483fbd  mov     [rbp+57h+var_90], rsi
0x180483fc1  mov     [rsp+130h+var_D8], rsi
0x180483fc6  mov     r9d, 20h ; ' '; unsigned int
0x180483fcc  lea     r8d, [r9+1]; unsigned int
0x180483fd0  lea     rdx, ?RuntimeClass_Windows_Internal_Tiles_TileStore@@3QBGB; "Windows.Internal.Tiles.TileStore"
0x180483fd7  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x180483fdc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180483fe1  mov     rbx, [rsp+130h+var_D8]
0x180483fe6  lea     rcx, [rbp+57h+var_90]
0x180483fea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180483fef  lea     r8, [rbp+57h+var_90]
0x180483ff3  lea     rdx, _GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40
0x180483ffa  mov     rcx, rbx
0x180483ffd  call    cs:__imp_RoGetActivationFactory
0x180484004  nop     dword ptr [rax+rax+00h]
0x180484009  mov     ebx, eax
0x18048400b  test    eax, eax
0x18048400d  jns     short loc_180484035
0x18048400f  mov     rcx, [rbp+5Fh]; this
0x180484013  mov     r9d, eax; char *
0x180484016  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x18048401d  mov     edx, 25h ; '%'; void *
0x180484022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180484027  lea     rcx, [rbp+57h+var_90]
0x18048402b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180484030  jmp     loc_18048471D
0x180484035  mov     [rbp+57h+var_88], rsi
0x180484039  mov     rdi, [rbp+57h+var_90]
0x18048403d  mov     rax, [rdi]
0x180484040  mov     rbx, [rax+30h]
0x180484044  lea     rcx, [rbp+57h+var_88]
0x180484048  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18048404d  lea     r8, [rbp+57h+var_88]
0x180484051  xor     edx, edx
0x180484053  mov     rcx, rdi
0x180484056  mov     rax, rbx
0x180484059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18048405e  mov     ebx, eax
0x180484060  test    eax, eax
0x180484062  jns     short loc_180484087
0x180484064  mov     rcx, [rbp+5Fh]; this
0x180484068  mov     r9d, eax; char *
0x18048406b  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180484072  mov     edx, 28h ; '('; void *
0x180484077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18048407c  lea     rcx, [rbp+57h+var_88]
0x180484080  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180484085  jmp     short loc_180484027
0x180484087  mov     [rbp+57h+var_98], rsi
0x18048408b  mov     [rsp+130h+var_D8], rsi
0x180484090  mov     r9d, 26h ; '&'; unsigned int
0x180484096  lea     r8d, [r9+1]; unsigned int
0x18048409a  lea     rdx, ?RuntimeClass_Windows_Internal_Tiles_TileQueryFilter@@3QBGB; "Windows.Internal.Tiles.TileQueryFilter"
0x1804840a1  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x1804840a6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1804840ab  mov     rbx, [rsp+130h+var_D8]
0x1804840b0  lea     rcx, [rbp+57h+var_98]
0x1804840b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804840b9  lea     rdx, [rbp+57h+var_98]
0x1804840bd  mov     rcx, rbx
0x1804840c0  call    ??$ActivateInstance@UITileQueryFilter@Tiles@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUITileQueryFilter@Tiles@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Tiles::ITileQueryFilter>(HSTRING__ *,Windows::Internal::Tiles::ITileQueryFilter * *)
0x1804840c5  mov     ebx, eax
0x1804840c7  test    eax, eax
0x1804840c9  jns     short loc_1804840EE
0x1804840cb  mov     edx, 2Dh ; '-'; void *
0x1804840d0  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x1804840d7  mov     r9d, eax; char *
0x1804840da  mov     rcx, [rbp+5Fh]; this
0x1804840de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804840e3  lea     rcx, [rbp+57h+var_98]
0x1804840e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804840ec  jmp     short loc_18048407C
0x1804840ee  mov     rdi, [rbp+57h+var_98]
0x1804840f2  mov     rax, [rdi]
0x1804840f5  mov     rbx, [rax+58h]
0x1804840f9  mov     rdx, qword ptr [rsp+130h+var_F8]
0x1804840fe  mov     [rbp+57h+var_A0], rdx
0x180484102  lea     rdx, [rbp+57h+var_A0]
0x180484106  lea     rcx, [rsp+130h+hstringHeader]
0x18048410b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180484110  mov     rdx, [rax+18h]
0x180484114  mov     rcx, rdi
0x180484117  mov     rax, rbx
0x18048411a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18048411f  mov     ebx, eax
0x180484121  test    eax, eax
0x180484123  jns     short loc_18048412C
0x180484125  mov     edx, 2Fh ; '/'
0x18048412a  jmp     short loc_1804840D0
0x18048412c  mov     [rbp+57h+var_80], rsi
0x180484130  mov     rdi, [rbp+57h+var_98]
0x180484134  mov     rax, [rdi]
0x180484137  mov     rbx, [rax+30h]
0x18048413b  lea     rcx, [rbp+57h+var_80]
0x18048413f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180484144  lea     rdx, [rbp+57h+var_80]
0x180484148  mov     rcx, rdi
0x18048414b  mov     rax, rbx
0x18048414e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180484153  mov     ebx, eax
0x180484155  test    eax, eax
0x180484157  jns     short loc_18048417F
0x180484159  mov     edx, 32h ; '2'; void *
0x18048415e  mov     rcx, [rbp+5Fh]; this
0x180484162  mov     r9d, eax; char *
0x180484165  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x18048416c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180484171  lea     rcx, [rbp+57h+var_80]
0x180484175  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18048417a  jmp     loc_1804840E3
0x18048417f  mov     rcx, [rbp+57h+var_80]
0x180484183  mov     rax, [rcx]
0x180484186  mov     edx, 1
0x18048418b  mov     rax, [rax+68h]
0x18048418f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180484194  mov     ebx, eax
0x180484196  test    eax, eax
0x180484198  jns     short loc_1804841A1
0x18048419a  mov     edx, 34h ; '4'
0x18048419f  jmp     short loc_18048415E
0x1804841a1  mov     rdi, [rbp+57h+var_98]
0x1804841a5  mov     rax, [rdi]
0x1804841a8  mov     rbx, [rax+68h]
0x1804841ac  mov     rdx, [rsp+130h+var_100]
0x1804841b1  mov     [rbp+57h+var_A0], rdx
0x1804841b5  lea     rdx, [rbp+57h+var_A0]
0x1804841b9  lea     rcx, [rsp+130h+hstringHeader]
0x1804841be  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1804841c3  mov     rdx, [rax+18h]
0x1804841c7  mov     rcx, rdi
0x1804841ca  mov     rax, rbx
0x1804841cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804841d2  mov     ebx, eax
0x1804841d4  test    eax, eax
0x1804841d6  jns     short loc_1804841E2
0x1804841d8  mov     edx, 35h ; '5'
0x1804841dd  jmp     loc_18048415E
0x1804841e2  mov     [rbp+57h+var_70], rsi
0x1804841e6  mov     rdi, [rbp+57h+var_88]
0x1804841ea  mov     rax, [rdi]
0x1804841ed  mov     rbx, [rax+38h]
0x1804841f1  lea     rcx, [rbp+57h+var_70]
0x1804841f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804841fa  lea     r9, [rbp+57h+var_70]
0x1804841fe  mov     r8, [rbp+57h+var_98]
0x180484202  xor     edx, edx
0x180484204  mov     rcx, rdi
0x180484207  mov     rax, rbx
0x18048420a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18048420f  mov     ebx, eax
0x180484211  test    eax, eax
0x180484213  jns     short loc_18048423B
0x180484215  mov     edx, 38h ; '8'; void *
0x18048421a  mov     r9d, eax; char *
0x18048421d  mov     rcx, [rbp+5Fh]; this
0x180484221  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180484228  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18048422d  lea     rcx, [rbp+57h+var_70]
0x180484231  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180484236  jmp     loc_180484171
0x18048423b  mov     [rbp+57h+var_54], esi
0x18048423e  mov     rcx, [rbp+57h+var_70]
0x180484242  mov     rax, [rcx]
0x180484245  lea     rdx, [rbp+57h+var_54]
0x180484249  mov     rax, [rax+38h]
0x18048424d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180484252  mov     ebx, eax
0x180484254  test    eax, eax
0x180484256  jns     short loc_18048425F
0x180484258  mov     edx, 3Bh ; ';'
0x18048425d  jmp     short loc_18048421A
0x18048425f  cmp     [rbp+57h+var_54], 1
0x180484263  jz      short loc_180484274
0x180484265  mov     ebx, 8007000Dh
0x18048426a  mov     r9d, ebx
0x18048426d  mov     edx, 3Ch ; '<'
0x180484272  jmp     short loc_18048421D
0x180484274  mov     [rbp+57h+var_68], rsi
0x180484278  mov     rdi, [rbp+57h+var_70]
0x18048427c  mov     rax, [rdi]
0x18048427f  mov     rbx, [rax+30h]
0x180484283  lea     rcx, [rbp+57h+var_68]
0x180484287  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18048428c  lea     r8, [rbp+57h+var_68]
0x180484290  xor     edx, edx
0x180484292  mov     rcx, rdi
0x180484295  mov     rax, rbx
0x180484298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18048429d  mov     ebx, eax
0x18048429f  test    eax, eax
0x1804842a1  jns     short loc_1804842C9
0x1804842a3  mov     rcx, [rbp+5Fh]; this
0x1804842a7  mov     r9d, eax; char *
0x1804842aa  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x1804842b1  mov     edx, 3Fh ; '?'; void *
0x1804842b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804842bb  lea     rcx, [rbp+57h+var_68]
0x1804842bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804842c4  jmp     loc_18048422D
0x1804842c9  mov     [rbp+57h+var_60], rsi
0x1804842cd  mov     rdi, [rbp+57h+var_68]
0x1804842d1  mov     rax, [rdi]
0x1804842d4  mov     rbx, [rax]
0x1804842d7  lea     rcx, [rbp+57h+var_60]
0x1804842db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804842e0  lea     r8, [rbp+57h+var_60]
0x1804842e4  lea     rdx, _GUID_f10ff47a_c551_404d_9a7f_379d7d40b973
0x1804842eb  mov     rcx, rdi
0x1804842ee  mov     rax, rbx
0x1804842f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804842f6  mov     ebx, eax
0x1804842f8  test    eax, eax
0x1804842fa  jns     short loc_18048431F
0x1804842fc  mov     rcx, [rbp+5Fh]; this
0x180484300  mov     r9d, eax; char *
0x180484303  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x18048430a  mov     edx, 42h ; 'B'; void *
0x18048430f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180484314  lea     rcx, [rbp+57h+var_60]
0x180484318  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18048431d  jmp     short loc_1804842BB
0x18048431f  mov     [rbp+57h+string], rsi
0x180484323  mov     rdi, [rbp+57h+var_60]
0x180484327  mov     rax, [rdi]
0x18048432a  mov     rbx, [rax+40h]
0x18048432e  xor     ecx, ecx; string
0x180484330  call    cs:__imp_WindowsDeleteString
0x180484337  nop     dword ptr [rax+rax+00h]
0x18048433c  mov     [rbp+57h+string], rsi
0x180484340  lea     rdx, [rbp+57h+string]
0x180484344  mov     rcx, rdi
0x180484347  mov     rax, rbx
0x18048434a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18048434f  mov     ebx, eax
0x180484351  test    eax, eax
0x180484353  jns     short loc_180484383
0x180484355  mov     rcx, [rbp+5Fh]; this
0x180484359  mov     r9d, eax; char *
0x18048435c  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180484363  mov     edx, 45h ; 'E'; void *
0x180484368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18048436d  mov     rcx, [rbp+57h+string]; string
0x180484371  call    cs:__imp_WindowsDeleteString
0x180484378  nop     dword ptr [rax+rax+00h]
0x18048437d  mov     [rbp+57h+string], rsi
0x180484381  jmp     short loc_180484314
0x180484383  mov     r14, rsi
0x180484386  mov     qword ptr [rsp+130h+hstringHeader.Reserved], rsi
0x18048438b  mov     qword ptr [rsp+130h+hstringHeader.Reserved+8], rsi
0x180484390  mov     qword ptr [rsp+130h+hstringHeader.Reserved+10h], rsi
0x180484395  mov     rdi, rsi
0x180484398  mov     [rbp+57h+var_D0], rsi
0x18048439c  mov     [rbp+57h+var_C8], rsi
  ... truncated ...
```
