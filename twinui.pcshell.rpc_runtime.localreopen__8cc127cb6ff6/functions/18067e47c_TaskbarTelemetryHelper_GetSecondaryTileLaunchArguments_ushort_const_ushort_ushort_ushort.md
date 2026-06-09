# TaskbarTelemetryHelper::GetSecondaryTileLaunchArguments(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x18067e47c`
- end: `0x18067ecc7`
- name: `?GetSecondaryTileLaunchArguments@TaskbarTelemetryHelper@@YAJPEBGPEAPEAG11@Z`
- size: `2123`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180354cb4`
- `0x180680ee0`
- `0x18068337c`

## callees

- `0x1800134f8`
- `0x18001d664`
- `0x1800237c8`
- `0x18007b3e0`
- `0x180086ac0`
- `0x18008a6f0`
- `0x1800e1a60`
- `0x18014b060`
- `0x1802e4598`
- `0x180356360`
- `0x18067c254`
- `0x18067e47c`
- `0x18067f98c`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18067e9b6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18067e9e4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18067e9b6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18067e9e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067e884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067e8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067eac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067eb75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067ec41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067e884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067e8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067eac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067eb75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18067ec41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18067e905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18067e905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067ea9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067eb4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067ec1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067ea9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067eb4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067ec1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18067e55c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18067e55c`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x18067e912`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x18067e912`

## string_xrefs

- `0x18067e508`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e56f`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e5c4`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e629`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e6bd`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e775`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e7fe`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e857`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067e8aa`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`
- `0x18067ea84`: `Desktop\Internal\Shell\Inc\private\TaskbarTelemetryHelper.h`

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
  unsigned __int16 **v9; // rbx
  const unsigned __int16 *v10; // rax
  unsigned __int16 **v11; // r9
  int AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier; // eax
  unsigned int v13; // ebx
  __int64 v14; // rbx
  int ActivationFactory; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD); // rbx
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD); // rbx
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, _QWORD, __int64, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, _QWORD); // rbx
  int v39; // eax
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v41)(_QWORD, GUID *, __int64 *); // rbx
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, HSTRING *); // rbx
  int v45; // eax
  PVOID Reserved1; // r14
  unsigned __int16 *v47; // rdi
  const WCHAR *StringRawBuffer; // rax
  LPWSTR *v49; // rbx
  LPWSTR v50; // rax
  LPWSTR v51; // rcx
  int v52; // edx
  int v53; // r8d
  int v54; // esi
  const wchar_t *v55; // rcx
  unsigned __int64 v56; // rax
  wchar_t *v57; // rax
  __int64 v58; // rcx
  const wchar_t *v59; // rsi
  wchar_t *v60; // rax
  __int64 v61; // rdx
  char *v62; // r9
  int v63; // ecx
  int v64; // r8d
  int v66; // [rsp+20h] [rbp-B9h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v68; // [rsp+48h] [rbp-91h]
  unsigned __int16 *v69; // [rsp+50h] [rbp-89h] BYREF
  __int64 v70; // [rsp+58h] [rbp-81h]
  __int64 v71; // [rsp+60h] [rbp-79h]
  __int64 v72; // [rsp+68h] [rbp-71h] BYREF
  __int64 v73; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int16 *v74; // [rsp+78h] [rbp-61h] BYREF
  __int64 v75; // [rsp+80h] [rbp-59h]
  __int64 v76; // [rsp+88h] [rbp-51h]
  __int64 v77; // [rsp+90h] [rbp-49h] BYREF
  __int64 v78; // [rsp+98h] [rbp-41h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v80; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v81; // [rsp+B0h] [rbp-29h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-19h] BYREF
  __int64 (__fastcall ***v84)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp-11h] BYREF
  __int64 v85; // [rsp+D0h] [rbp-9h] BYREF
  int pNumArgs; // [rsp+D8h] [rbp-1h] BYREF
  int v87; // [rsp+DCh] [rbp+3h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v8 = 0;
  *(_QWORD *)a2 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( !Str || !SecondaryTileIdentifierHelpers::IsFullyQualifiedTileIdentifier(Str, a2) )
    return 2147943569LL;
  v73 = 0;
  v72 = 0;
  v9 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v72);
  v10 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v73);
  AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier = SecondaryTileIdentifierHelpers::GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier(
                                                                 Str,
                                                                 v10,
                                                                 v9,
                                                                 v11);
  v13 = AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier;
  if ( AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier,
      v66);
LABEL_77:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v72);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v73);
    return v13;
  }
  v79 = 0;
  v68 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Tiles.TileStore",
    0x21u,
    0x20u);
  v14 = v68;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40, &v79);
  v13 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)ActivationFactory,
      v66);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    goto LABEL_77;
  }
  v80 = 0;
  v16 = v79;
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v79 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  v18 = v17(v16, 0, &v80);
  v13 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v18,
      v66);
LABEL_10:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    goto LABEL_7;
  }
  v78 = 0;
  v68 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Tiles.TileQueryFilter",
    0x27u,
    0x26u);
  v19 = v68;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  v20 = Windows::Foundation::ActivateInstance<Windows::Internal::Tiles::ITileQueryFilter>(v19, &v78);
  v13 = v20;
  if ( v20 < 0 )
  {
    v21 = 45;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v20,
      v66);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    goto LABEL_10;
  }
  v22 = v78;
  v23 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v78 + 88LL);
  v77 = v73;
  v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v77);
  v20 = v23(v22, *(_QWORD *)(v24 + 24));
  v13 = v20;
  if ( v20 < 0 )
  {
    v21 = 47;
    goto LABEL_13;
  }
  v81 = 0;
  v25 = v78;
  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  v27 = v26(v25, &v81);
  v13 = v27;
  if ( v27 < 0 )
  {
    v28 = 50;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v27,
      v66);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    goto LABEL_14;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 104LL))(v81, 1);
  v13 = v27;
  if ( v27 < 0 )
  {
    v28 = 52;
    goto LABEL_19;
  }
  v29 = v78;
  v30 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v78 + 104LL);
  v77 = v72;
  v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v77);
  v27 = v30(v29, *(_QWORD *)(v31 + 24));
  v13 = v27;
  if ( v27 < 0 )
  {
    v28 = 53;
    goto LABEL_19;
  }
  v83 = 0;
  v32 = v80;
  v33 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v80 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  v34 = v33(v32, 0, v78, &v83);
  v13 = v34;
  if ( v34 < 0 )
  {
    v35 = 56;
LABEL_27:
    v36 = (unsigned int)v34;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)v36,
      v66);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    goto LABEL_20;
  }
  v87 = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v83 + 56LL))(v83, &v87);
  v13 = v34;
  if ( v34 < 0 )
  {
    v35 = 59;
    goto LABEL_27;
  }
  if ( v87 != 1 )
  {
    v13 = -2147024883;
    v36 = 2147942413LL;
    v35 = 60;
    goto LABEL_28;
  }
  v84 = 0;
  v37 = v83;
  v38 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v83 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  v39 = v38(v37, 0, &v84);
  v13 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v39,
      v66);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    goto LABEL_29;
  }
  v85 = 0;
  v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
  v41 = **v84;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  v42 = v41(v40, &GUID_f10ff47a_c551_404d_9a7f_379d7d40b973, &v85);
  v13 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v42,
      v66);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    goto LABEL_36;
  }
  string = 0;
  v43 = v85;
  v44 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v85 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v45 = v44(v43, &string);
  v13 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
      (const char *)(unsigned int)v45,
      v66);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_39;
  }
  Reserved1 = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  v47 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  pNumArgs = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v49 = CommandLineToArgvW(StringRawBuffer, &pNumArgs);
  if ( !v49 )
    goto LABEL_73;
  while ( (int)v47 < pNumArgs )
  {
    v50 = v49[(int)v47];
    v51 = v50;
    do
    {
      v52 = *(LPWSTR)((char *)v51 + (char *)L"-url" - (char *)v50);
      v53 = *v51 - v52;
      if ( v53 )
        break;
      ++v51;
    }
    while ( v52 );
    if ( v53 )
    {
      v62 = (char *)((char *)L"-tbPinSource" - (char *)v50);
      do
      {
        v63 = *(unsigned __int16 *)&v62[(_QWORD)v50];
        v64 = *v50 - v63;
        if ( v64 )
          break;
        ++v50;
      }
      while ( v63 );
      if ( !v64 && (int)v47 + 1 < pNumArgs )
      {
        v54 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v74,
                v49[(int)v47 + 1],
                -1);
        if ( v54 < 0 )
        {
          v61 = 124;
          goto LABEL_69;
        }
      }
    }
    else if ( (int)v47 + 2 < pNumArgs )
    {
      v54 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &hstringHeader,
              v49[(int)v47 + 2],
              -1);
      if ( v54 < 0 )
      {
        v61 = 92;
        goto LABEL_69;
      }
      v55 = v49[(int)v47 + 2];
      v56 = -1;
      do
        ++v56;
      while ( v55[v56] );
      if ( v56 > 1 )
      {
        v57 = wcsstr(v55, L"msSrc=");
        if ( v57 )
        {
          v58 = -1;
          do
            ++v58;
          while ( aMssrc[v58] );
          v59 = &v57[v58];
          v60 = wcsstr(v59, L"&");
          if ( v60 )
          {
            v54 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    &v69,
                    v59,
                    v60 - v59);
            if ( v54 < 0 )
            {
              v61 = 108;
LABEL_69:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v61,
                (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\TaskbarTelemetryHelper.h",
                (const char *)(unsigned int)v54,
                v66);
              LocalFree(v49);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v69);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
              v13 = v54;
              goto LABEL_77;
            }
          }
          else
          {
            v54 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    &v69,
                    v59,
                    -1);
            if ( v54 < 0 )
            {
              v61 = 112;
              goto LABEL_69;
            }
          }
        }
      }
    }
    LODWORD(v47) = (_DWORD)v47 + 1;
  }
  Reserved1 = hstringHeader.Reserved.Reserved1;
  v47 = v69;
  v8 = v74;
  if ( !hstringHeader.Reserved.Reserved1 )
  {
LABEL_73:
    if ( !v47 && !v8 )
    {
      if ( v49 )
        LocalFree(v49);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v69);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
      v13 = -2147023727;
      goto LABEL_77;
    }
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  *(_QWORD *)a2 = Reserved1;
  v69 = 0;
  v71 = 0;
  v70 = 0;
  *a3 = v47;
  v74 = 0;
  v76 = 0;
  v75 = 0;
  *a4 = v8;
  if ( v49 )
    LocalFree(v49);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v69);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v72);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v73);
  return 0;
}

```

## disassembly

```asm
0x18067e47c  push    rbp
0x18067e47e  push    rbx
0x18067e47f  push    rsi
0x18067e480  push    rdi
0x18067e481  push    r12
0x18067e483  push    r13
0x18067e485  push    r14
0x18067e487  push    r15
0x18067e489  lea     rbp, [rsp-1Fh]
0x18067e48e  sub     rsp, 0F8h
0x18067e495  mov     rax, cs:__security_cookie
0x18067e49c  xor     rax, rsp
0x18067e49f  mov     [rbp+57h+var_50], rax
0x18067e4a3  mov     r13, r9
0x18067e4a6  mov     r12, r8
0x18067e4a9  mov     r15, rdx
0x18067e4ac  mov     rdi, rcx
0x18067e4af  xor     esi, esi
0x18067e4b1  mov     [rdx], rsi
0x18067e4b4  mov     [r8], rsi
0x18067e4b7  mov     [r9], rsi
0x18067e4ba  test    rcx, rcx
0x18067e4bd  jz      loc_18067ECA2
0x18067e4c3  call    ?IsFullyQualifiedTileIdentifier@SecondaryTileIdentifierHelpers@@YA_NPEBG@Z; SecondaryTileIdentifierHelpers::IsFullyQualifiedTileIdentifier(ushort const *)
0x18067e4c8  test    al, al
0x18067e4ca  jz      loc_18067ECA2
0x18067e4d0  mov     [rbp+57h+var_C0], rsi
0x18067e4d4  mov     [rbp+57h+var_C8], rsi
0x18067e4d8  lea     rcx, [rbp+57h+var_C8]
0x18067e4dc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18067e4e1  mov     rbx, rax
0x18067e4e4  lea     rcx, [rbp+57h+var_C0]
0x18067e4e8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18067e4ed  mov     r8, rbx; unsigned __int16 **
0x18067e4f0  mov     rdx, rax; unsigned __int16 *
0x18067e4f3  mov     rcx, rdi; Str
0x18067e4f6  call    ?GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier@SecondaryTileIdentifierHelpers@@YAJPEBGPEAPEAG1@Z; SecondaryTileIdentifierHelpers::GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier(ushort const *,ushort * *,ushort * *)
0x18067e4fb  mov     ebx, eax
0x18067e4fd  test    eax, eax
0x18067e4ff  jns     short loc_18067E51C
0x18067e501  mov     rcx, [rbp+5Fh]; this
0x18067e505  mov     r9d, eax; char *
0x18067e508  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e50f  lea     edx, [rsi+20h]; void *
0x18067e512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e517  jmp     loc_18067EBC5
0x18067e51c  mov     [rbp+57h+var_90], rsi
0x18067e520  mov     [rsp+130h+var_E8], rsi
0x18067e525  mov     r9d, 20h ; ' '; unsigned int
0x18067e52b  lea     r8d, [r9+1]; unsigned int
0x18067e52f  lea     rdx, ?RuntimeClass_Windows_Internal_Tiles_TileStore@@3QBGB; "Windows.Internal.Tiles.TileStore"
0x18067e536  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x18067e53b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18067e540  mov     rbx, [rsp+130h+var_E8]
0x18067e545  lea     rcx, [rbp+57h+var_90]
0x18067e549  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e54e  lea     r8, [rbp+57h+var_90]
0x18067e552  lea     rdx, _GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40
0x18067e559  mov     rcx, rbx
0x18067e55c  call    cs:__imp_RoGetActivationFactory
0x18067e562  mov     ebx, eax
0x18067e564  test    eax, eax
0x18067e566  jns     short loc_18067E58E
0x18067e568  mov     rcx, [rbp+5Fh]; this
0x18067e56c  mov     r9d, eax; char *
0x18067e56f  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e576  mov     edx, 25h ; '%'; void *
0x18067e57b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e580  lea     rcx, [rbp+57h+var_90]
0x18067e584  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e589  jmp     loc_18067EBC5
0x18067e58e  mov     [rbp+57h+var_88], rsi
0x18067e592  mov     rdi, [rbp+57h+var_90]
0x18067e596  mov     rax, [rdi]
0x18067e599  mov     rbx, [rax+30h]
0x18067e59d  lea     rcx, [rbp+57h+var_88]
0x18067e5a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e5a6  lea     r8, [rbp+57h+var_88]
0x18067e5aa  xor     edx, edx
0x18067e5ac  mov     rcx, rdi
0x18067e5af  mov     rax, rbx
0x18067e5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e5b7  mov     ebx, eax
0x18067e5b9  test    eax, eax
0x18067e5bb  jns     short loc_18067E5E0
0x18067e5bd  mov     rcx, [rbp+5Fh]; this
0x18067e5c1  mov     r9d, eax; char *
0x18067e5c4  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e5cb  mov     edx, 28h ; '('; void *
0x18067e5d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e5d5  lea     rcx, [rbp+57h+var_88]
0x18067e5d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e5de  jmp     short loc_18067E580
0x18067e5e0  mov     [rbp+57h+var_98], rsi
0x18067e5e4  mov     [rsp+130h+var_E8], rsi
0x18067e5e9  mov     r9d, 26h ; '&'; unsigned int
0x18067e5ef  lea     r8d, [r9+1]; unsigned int
0x18067e5f3  lea     rdx, ?RuntimeClass_Windows_Internal_Tiles_TileQueryFilter@@3QBGB; "Windows.Internal.Tiles.TileQueryFilter"
0x18067e5fa  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x18067e5ff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18067e604  mov     rbx, [rsp+130h+var_E8]
0x18067e609  lea     rcx, [rbp+57h+var_98]
0x18067e60d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e612  lea     rdx, [rbp+57h+var_98]
0x18067e616  mov     rcx, rbx
0x18067e619  call    ??$ActivateInstance@UITileQueryFilter@Tiles@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUITileQueryFilter@Tiles@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Tiles::ITileQueryFilter>(HSTRING__ *,Windows::Internal::Tiles::ITileQueryFilter * *)
0x18067e61e  mov     ebx, eax
0x18067e620  test    eax, eax
0x18067e622  jns     short loc_18067E647
0x18067e624  mov     edx, 2Dh ; '-'; void *
0x18067e629  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e630  mov     r9d, eax; char *
0x18067e633  mov     rcx, [rbp+5Fh]; this
0x18067e637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e63c  lea     rcx, [rbp+57h+var_98]
0x18067e640  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e645  jmp     short loc_18067E5D5
0x18067e647  mov     rdi, [rbp+57h+var_98]
0x18067e64b  mov     rax, [rdi]
0x18067e64e  mov     rbx, [rax+58h]
0x18067e652  mov     rdx, [rbp+57h+var_C0]
0x18067e656  mov     [rbp+57h+var_A0], rdx
0x18067e65a  lea     rdx, [rbp+57h+var_A0]
0x18067e65e  lea     rcx, [rsp+130h+hstringHeader]
0x18067e663  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18067e668  mov     rdx, [rax+18h]
0x18067e66c  mov     rcx, rdi
0x18067e66f  mov     rax, rbx
0x18067e672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e677  mov     ebx, eax
0x18067e679  test    eax, eax
0x18067e67b  jns     short loc_18067E684
0x18067e67d  mov     edx, 2Fh ; '/'
0x18067e682  jmp     short loc_18067E629
0x18067e684  mov     [rbp+57h+var_80], rsi
0x18067e688  mov     rdi, [rbp+57h+var_98]
0x18067e68c  mov     rax, [rdi]
0x18067e68f  mov     rbx, [rax+30h]
0x18067e693  lea     rcx, [rbp+57h+var_80]
0x18067e697  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e69c  lea     rdx, [rbp+57h+var_80]
0x18067e6a0  mov     rcx, rdi
0x18067e6a3  mov     rax, rbx
0x18067e6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e6ab  mov     ebx, eax
0x18067e6ad  test    eax, eax
0x18067e6af  jns     short loc_18067E6D7
0x18067e6b1  mov     edx, 32h ; '2'; void *
0x18067e6b6  mov     rcx, [rbp+5Fh]; this
0x18067e6ba  mov     r9d, eax; char *
0x18067e6bd  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e6c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e6c9  lea     rcx, [rbp+57h+var_80]
0x18067e6cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e6d2  jmp     loc_18067E63C
0x18067e6d7  mov     rcx, [rbp+57h+var_80]
0x18067e6db  mov     rax, [rcx]
0x18067e6de  mov     edx, 1
0x18067e6e3  mov     rax, [rax+68h]
0x18067e6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e6ec  mov     ebx, eax
0x18067e6ee  test    eax, eax
0x18067e6f0  jns     short loc_18067E6F9
0x18067e6f2  mov     edx, 34h ; '4'
0x18067e6f7  jmp     short loc_18067E6B6
0x18067e6f9  mov     rdi, [rbp+57h+var_98]
0x18067e6fd  mov     rax, [rdi]
0x18067e700  mov     rbx, [rax+68h]
0x18067e704  mov     rdx, [rbp+57h+var_C8]
0x18067e708  mov     [rbp+57h+var_A0], rdx
0x18067e70c  lea     rdx, [rbp+57h+var_A0]
0x18067e710  lea     rcx, [rsp+130h+hstringHeader]
0x18067e715  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18067e71a  mov     rdx, [rax+18h]
0x18067e71e  mov     rcx, rdi
0x18067e721  mov     rax, rbx
0x18067e724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e729  mov     ebx, eax
0x18067e72b  test    eax, eax
0x18067e72d  jns     short loc_18067E736
0x18067e72f  mov     edx, 35h ; '5'
0x18067e734  jmp     short loc_18067E6B6
0x18067e736  mov     [rbp+57h+var_70], rsi
0x18067e73a  mov     rdi, [rbp+57h+var_88]
0x18067e73e  mov     rax, [rdi]
0x18067e741  mov     rbx, [rax+38h]
0x18067e745  lea     rcx, [rbp+57h+var_70]
0x18067e749  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e74e  lea     r9, [rbp+57h+var_70]
0x18067e752  mov     r8, [rbp+57h+var_98]
0x18067e756  xor     edx, edx
0x18067e758  mov     rcx, rdi
0x18067e75b  mov     rax, rbx
0x18067e75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e763  mov     ebx, eax
0x18067e765  test    eax, eax
0x18067e767  jns     short loc_18067E78F
0x18067e769  mov     edx, 38h ; '8'; void *
0x18067e76e  mov     r9d, eax; char *
0x18067e771  mov     rcx, [rbp+5Fh]; this
0x18067e775  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e77c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e781  lea     rcx, [rbp+57h+var_70]
0x18067e785  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e78a  jmp     loc_18067E6C9
0x18067e78f  mov     [rbp+57h+var_54], esi
0x18067e792  mov     rcx, [rbp+57h+var_70]
0x18067e796  mov     rax, [rcx]
0x18067e799  lea     rdx, [rbp+57h+var_54]
0x18067e79d  mov     rax, [rax+38h]
0x18067e7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e7a6  mov     ebx, eax
0x18067e7a8  test    eax, eax
0x18067e7aa  jns     short loc_18067E7B3
0x18067e7ac  mov     edx, 3Bh ; ';'
0x18067e7b1  jmp     short loc_18067E76E
0x18067e7b3  cmp     [rbp+57h+var_54], 1
0x18067e7b7  jz      short loc_18067E7C8
0x18067e7b9  mov     ebx, 8007000Dh
0x18067e7be  mov     r9d, ebx
0x18067e7c1  mov     edx, 3Ch ; '<'
0x18067e7c6  jmp     short loc_18067E771
0x18067e7c8  mov     [rbp+57h+var_68], rsi
0x18067e7cc  mov     rdi, [rbp+57h+var_70]
0x18067e7d0  mov     rax, [rdi]
0x18067e7d3  mov     rbx, [rax+30h]
0x18067e7d7  lea     rcx, [rbp+57h+var_68]
0x18067e7db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e7e0  lea     r8, [rbp+57h+var_68]
0x18067e7e4  xor     edx, edx
0x18067e7e6  mov     rcx, rdi
0x18067e7e9  mov     rax, rbx
0x18067e7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e7f1  mov     ebx, eax
0x18067e7f3  test    eax, eax
0x18067e7f5  jns     short loc_18067E81D
0x18067e7f7  mov     rcx, [rbp+5Fh]; this
0x18067e7fb  mov     r9d, eax; char *
0x18067e7fe  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e805  mov     edx, 3Fh ; '?'; void *
0x18067e80a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e80f  lea     rcx, [rbp+57h+var_68]
0x18067e813  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e818  jmp     loc_18067E781
0x18067e81d  mov     [rbp+57h+var_60], rsi
0x18067e821  mov     rdi, [rbp+57h+var_68]
0x18067e825  mov     rax, [rdi]
0x18067e828  mov     rbx, [rax]
0x18067e82b  lea     rcx, [rbp+57h+var_60]
0x18067e82f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e834  lea     r8, [rbp+57h+var_60]
0x18067e838  lea     rdx, _GUID_f10ff47a_c551_404d_9a7f_379d7d40b973
0x18067e83f  mov     rcx, rdi
0x18067e842  mov     rax, rbx
0x18067e845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e84a  mov     ebx, eax
0x18067e84c  test    eax, eax
0x18067e84e  jns     short loc_18067E873
0x18067e850  mov     rcx, [rbp+5Fh]; this
0x18067e854  mov     r9d, eax; char *
0x18067e857  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e85e  mov     edx, 42h ; 'B'; void *
0x18067e863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e868  lea     rcx, [rbp+57h+var_60]
0x18067e86c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067e871  jmp     short loc_18067E80F
0x18067e873  mov     [rbp+57h+string], rsi
0x18067e877  mov     rdi, [rbp+57h+var_60]
0x18067e87b  mov     rax, [rdi]
0x18067e87e  mov     rbx, [rax+40h]
0x18067e882  xor     ecx, ecx; string
0x18067e884  call    cs:__imp_WindowsDeleteString
0x18067e88a  mov     [rbp+57h+string], rsi
0x18067e88e  lea     rdx, [rbp+57h+string]
0x18067e892  mov     rcx, rdi
0x18067e895  mov     rax, rbx
0x18067e898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067e89d  mov     ebx, eax
0x18067e89f  test    eax, eax
0x18067e8a1  jns     short loc_18067E8CB
0x18067e8a3  mov     rcx, [rbp+5Fh]; this
0x18067e8a7  mov     r9d, eax; char *
0x18067e8aa  lea     r8, aDesktopInterna_2; "Desktop\\Internal\\Shell\\Inc\\private"...
0x18067e8b1  mov     edx, 45h ; 'E'; void *
0x18067e8b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067e8bb  mov     rcx, [rbp+57h+string]; string
0x18067e8bf  call    cs:__imp_WindowsDeleteString
0x18067e8c5  mov     [rbp+57h+string], rsi
0x18067e8c9  jmp     short loc_18067E868
0x18067e8cb  mov     r14, rsi
0x18067e8ce  mov     qword ptr [rsp+130h+hstringHeader.Reserved], rsi
0x18067e8d3  mov     qword ptr [rsp+130h+hstringHeader.Reserved+8], rsi
0x18067e8d8  mov     qword ptr [rsp+130h+hstringHeader.Reserved+10h], rsi
0x18067e8dd  mov     rdi, rsi
0x18067e8e0  mov     [rsp+130h+var_E0], rsi
0x18067e8e5  mov     [rsp+130h+var_D8], rsi
0x18067e8ea  mov     [rbp+57h+var_D0], rsi
0x18067e8ee  mov     [rbp+57h+var_B8], rsi
0x18067e8f2  xor     ecx, ecx
0x18067e8f4  mov     [rbp+57h+var_B0], rcx
  ... truncated ...
```
