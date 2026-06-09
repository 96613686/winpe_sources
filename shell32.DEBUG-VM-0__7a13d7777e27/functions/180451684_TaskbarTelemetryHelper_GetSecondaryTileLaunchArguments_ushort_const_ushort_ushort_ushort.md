# TaskbarTelemetryHelper::GetSecondaryTileLaunchArguments(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180451684`
- end: `0x180451f3d`
- name: `?GetSecondaryTileLaunchArguments@TaskbarTelemetryHelper@@YAJPEBGPEAPEAG11@Z`
- size: `2233`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801a0164`
- `0x180453668`
- `0x180454c7c`

## callees

- `0x18000f05c`
- `0x1800181e0`
- `0x18003cd64`
- `0x180047d00`
- `0x180054320`
- `0x18007fd24`
- `0x1800b4154`
- `0x1800ed908`
- `0x1801e17d4`
- `0x180233280`
- `0x1804503dc`
- `0x180451684`
- `0x180452558`
- `0x180571010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180451bca`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180451bf8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180451bca`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180451bf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451c40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451c79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451d86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451dc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451c40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451c79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451d86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451dc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180451e8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180451b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180451b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451eb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180451eb5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18045176d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18045176d`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180451b26`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180451b26`

## string_xrefs

- `0x180451719`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451780`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x1804517d5`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x18045183a`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x1804518cf`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x18045198b`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451a14`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451a6d`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451ac0`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451c2c`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451c65`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451cdc`: `shell\inc\TaskbarTelemetryHelper.h`
- `0x180451d71`: `shell\inc\TaskbarTelemetryHelper.h`

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
          v59 = wcsstr(v58, asc_18060EADC);
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
0x180451684  push    rbp
0x180451686  push    rbx
0x180451687  push    rsi
0x180451688  push    rdi
0x180451689  push    r12
0x18045168b  push    r13
0x18045168d  push    r14
0x18045168f  push    r15
0x180451691  lea     rbp, [rsp-1Fh]
0x180451696  sub     rsp, 0F8h
0x18045169d  mov     rax, cs:__security_cookie
0x1804516a4  xor     rax, rsp
0x1804516a7  mov     [rbp+57h+var_50], rax
0x1804516ab  mov     r13, r9
0x1804516ae  mov     r12, r8
0x1804516b1  mov     r15, rdx
0x1804516b4  mov     rbx, rcx
0x1804516b7  xor     esi, esi
0x1804516b9  mov     [rdx], rsi
0x1804516bc  mov     [r8], rsi
0x1804516bf  mov     [r9], rsi
0x1804516c2  test    rcx, rcx
0x1804516c5  jz      loc_180451F18
0x1804516cb  call    ?IsFullyQualifiedTileIdentifier@SecondaryTileIdentifierHelpers@@YA_NPEBG@Z; SecondaryTileIdentifierHelpers::IsFullyQualifiedTileIdentifier(ushort const *)
0x1804516d0  test    al, al
0x1804516d2  jz      loc_180451F18
0x1804516d8  mov     qword ptr [rsp+130h+var_F8], rsi
0x1804516dd  mov     [rsp+130h+var_100], rsi
0x1804516e2  xor     edx, edx
0x1804516e4  lea     rcx, [rsp+130h+var_100]
0x1804516e9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1804516ee  xor     edx, edx
0x1804516f0  lea     rcx, [rsp+130h+var_F8]
0x1804516f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1804516fa  lea     r8, [rsp+130h+var_100]; unsigned __int16 **
0x1804516ff  lea     rdx, [rsp+130h+var_F8]; unsigned __int16 *
0x180451704  mov     rcx, rbx; Str
0x180451707  call    ?GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier@SecondaryTileIdentifierHelpers@@YAJPEBGPEAPEAG1@Z; SecondaryTileIdentifierHelpers::GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier(ushort const *,ushort * *,ushort * *)
0x18045170c  mov     ebx, eax
0x18045170e  test    eax, eax
0x180451710  jns     short loc_18045172D
0x180451712  mov     rcx, [rbp+5Fh]; this
0x180451716  mov     r9d, eax; char *
0x180451719  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451720  lea     edx, [rsi+20h]; void *
0x180451723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180451728  jmp     loc_180451E39
0x18045172d  mov     [rbp+57h+var_90], rsi
0x180451731  mov     [rsp+130h+var_D8], rsi
0x180451736  mov     r9d, 20h ; ' '; unsigned int
0x18045173c  lea     r8d, [r9+1]; unsigned int
0x180451740  lea     rdx, ?RuntimeClass_Windows_Internal_Tiles_TileStore@@3QBGB; "Windows.Internal.Tiles.TileStore"
0x180451747  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x18045174c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180451751  mov     rbx, [rsp+130h+var_D8]
0x180451756  lea     rcx, [rbp+57h+var_90]
0x18045175a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18045175f  lea     r8, [rbp+57h+var_90]
0x180451763  lea     rdx, _GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40
0x18045176a  mov     rcx, rbx
0x18045176d  call    cs:__imp_RoGetActivationFactory
0x180451773  mov     ebx, eax
0x180451775  test    eax, eax
0x180451777  jns     short loc_18045179F
0x180451779  mov     rcx, [rbp+5Fh]; this
0x18045177d  mov     r9d, eax; char *
0x180451780  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451787  mov     edx, 25h ; '%'; void *
0x18045178c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180451791  lea     rcx, [rbp+57h+var_90]
0x180451795  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18045179a  jmp     loc_180451E39
0x18045179f  mov     [rbp+57h+var_88], rsi
0x1804517a3  mov     rdi, [rbp+57h+var_90]
0x1804517a7  mov     rax, [rdi]
0x1804517aa  mov     rbx, [rax+30h]
0x1804517ae  lea     rcx, [rbp+57h+var_88]
0x1804517b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804517b7  lea     r8, [rbp+57h+var_88]
0x1804517bb  xor     edx, edx
0x1804517bd  mov     rcx, rdi
0x1804517c0  mov     rax, rbx
0x1804517c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804517c8  mov     ebx, eax
0x1804517ca  test    eax, eax
0x1804517cc  jns     short loc_1804517F1
0x1804517ce  mov     rcx, [rbp+5Fh]; this
0x1804517d2  mov     r9d, eax; char *
0x1804517d5  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x1804517dc  mov     edx, 28h ; '('; void *
0x1804517e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804517e6  lea     rcx, [rbp+57h+var_88]
0x1804517ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804517ef  jmp     short loc_180451791
0x1804517f1  mov     [rbp+57h+var_98], rsi
0x1804517f5  mov     [rsp+130h+var_D8], rsi
0x1804517fa  mov     r9d, 26h ; '&'; unsigned int
0x180451800  lea     r8d, [r9+1]; unsigned int
0x180451804  lea     rdx, ?RuntimeClass_Windows_Internal_Tiles_TileQueryFilter@@3QBGB; "Windows.Internal.Tiles.TileQueryFilter"
0x18045180b  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x180451810  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180451815  mov     rbx, [rsp+130h+var_D8]
0x18045181a  lea     rcx, [rbp+57h+var_98]
0x18045181e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180451823  lea     rdx, [rbp+57h+var_98]
0x180451827  mov     rcx, rbx
0x18045182a  call    ??$ActivateInstance@UITileQueryFilter@Tiles@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUITileQueryFilter@Tiles@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Tiles::ITileQueryFilter>(HSTRING__ *,Windows::Internal::Tiles::ITileQueryFilter * *)
0x18045182f  mov     ebx, eax
0x180451831  test    eax, eax
0x180451833  jns     short loc_180451858
0x180451835  mov     edx, 2Dh ; '-'; void *
0x18045183a  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451841  mov     r9d, eax; char *
0x180451844  mov     rcx, [rbp+5Fh]; this
0x180451848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18045184d  lea     rcx, [rbp+57h+var_98]
0x180451851  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180451856  jmp     short loc_1804517E6
0x180451858  mov     rdi, [rbp+57h+var_98]
0x18045185c  mov     rax, [rdi]
0x18045185f  mov     rbx, [rax+58h]
0x180451863  mov     rdx, qword ptr [rsp+130h+var_F8]
0x180451868  mov     [rbp+57h+var_A0], rdx
0x18045186c  lea     rdx, [rbp+57h+var_A0]
0x180451870  lea     rcx, [rsp+130h+hstringHeader]
0x180451875  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18045187a  mov     rdx, [rax+18h]
0x18045187e  mov     rcx, rdi
0x180451881  mov     rax, rbx
0x180451884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180451889  mov     ebx, eax
0x18045188b  test    eax, eax
0x18045188d  jns     short loc_180451896
0x18045188f  mov     edx, 2Fh ; '/'
0x180451894  jmp     short loc_18045183A
0x180451896  mov     [rbp+57h+var_80], rsi
0x18045189a  mov     rdi, [rbp+57h+var_98]
0x18045189e  mov     rax, [rdi]
0x1804518a1  mov     rbx, [rax+30h]
0x1804518a5  lea     rcx, [rbp+57h+var_80]
0x1804518a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804518ae  lea     rdx, [rbp+57h+var_80]
0x1804518b2  mov     rcx, rdi
0x1804518b5  mov     rax, rbx
0x1804518b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804518bd  mov     ebx, eax
0x1804518bf  test    eax, eax
0x1804518c1  jns     short loc_1804518E9
0x1804518c3  mov     edx, 32h ; '2'; void *
0x1804518c8  mov     rcx, [rbp+5Fh]; this
0x1804518cc  mov     r9d, eax; char *
0x1804518cf  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x1804518d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804518db  lea     rcx, [rbp+57h+var_80]
0x1804518df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804518e4  jmp     loc_18045184D
0x1804518e9  mov     rcx, [rbp+57h+var_80]
0x1804518ed  mov     rax, [rcx]
0x1804518f0  mov     edx, 1
0x1804518f5  mov     rax, [rax+68h]
0x1804518f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804518fe  mov     ebx, eax
0x180451900  test    eax, eax
0x180451902  jns     short loc_18045190B
0x180451904  mov     edx, 34h ; '4'
0x180451909  jmp     short loc_1804518C8
0x18045190b  mov     rdi, [rbp+57h+var_98]
0x18045190f  mov     rax, [rdi]
0x180451912  mov     rbx, [rax+68h]
0x180451916  mov     rdx, [rsp+130h+var_100]
0x18045191b  mov     [rbp+57h+var_A0], rdx
0x18045191f  lea     rdx, [rbp+57h+var_A0]
0x180451923  lea     rcx, [rsp+130h+hstringHeader]
0x180451928  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18045192d  mov     rdx, [rax+18h]
0x180451931  mov     rcx, rdi
0x180451934  mov     rax, rbx
0x180451937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045193c  mov     ebx, eax
0x18045193e  test    eax, eax
0x180451940  jns     short loc_18045194C
0x180451942  mov     edx, 35h ; '5'
0x180451947  jmp     loc_1804518C8
0x18045194c  mov     [rbp+57h+var_70], rsi
0x180451950  mov     rdi, [rbp+57h+var_88]
0x180451954  mov     rax, [rdi]
0x180451957  mov     rbx, [rax+38h]
0x18045195b  lea     rcx, [rbp+57h+var_70]
0x18045195f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180451964  lea     r9, [rbp+57h+var_70]
0x180451968  mov     r8, [rbp+57h+var_98]
0x18045196c  xor     edx, edx
0x18045196e  mov     rcx, rdi
0x180451971  mov     rax, rbx
0x180451974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180451979  mov     ebx, eax
0x18045197b  test    eax, eax
0x18045197d  jns     short loc_1804519A5
0x18045197f  mov     edx, 38h ; '8'; void *
0x180451984  mov     r9d, eax; char *
0x180451987  mov     rcx, [rbp+5Fh]; this
0x18045198b  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180451997  lea     rcx, [rbp+57h+var_70]
0x18045199b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804519a0  jmp     loc_1804518DB
0x1804519a5  mov     [rbp+57h+var_54], esi
0x1804519a8  mov     rcx, [rbp+57h+var_70]
0x1804519ac  mov     rax, [rcx]
0x1804519af  lea     rdx, [rbp+57h+var_54]
0x1804519b3  mov     rax, [rax+38h]
0x1804519b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804519bc  mov     ebx, eax
0x1804519be  test    eax, eax
0x1804519c0  jns     short loc_1804519C9
0x1804519c2  mov     edx, 3Bh ; ';'
0x1804519c7  jmp     short loc_180451984
0x1804519c9  cmp     [rbp+57h+var_54], 1
0x1804519cd  jz      short loc_1804519DE
0x1804519cf  mov     ebx, 8007000Dh
0x1804519d4  mov     r9d, ebx
0x1804519d7  mov     edx, 3Ch ; '<'
0x1804519dc  jmp     short loc_180451987
0x1804519de  mov     [rbp+57h+var_68], rsi
0x1804519e2  mov     rdi, [rbp+57h+var_70]
0x1804519e6  mov     rax, [rdi]
0x1804519e9  mov     rbx, [rax+30h]
0x1804519ed  lea     rcx, [rbp+57h+var_68]
0x1804519f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804519f6  lea     r8, [rbp+57h+var_68]
0x1804519fa  xor     edx, edx
0x1804519fc  mov     rcx, rdi
0x1804519ff  mov     rax, rbx
0x180451a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180451a07  mov     ebx, eax
0x180451a09  test    eax, eax
0x180451a0b  jns     short loc_180451A33
0x180451a0d  mov     rcx, [rbp+5Fh]; this
0x180451a11  mov     r9d, eax; char *
0x180451a14  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451a1b  mov     edx, 3Fh ; '?'; void *
0x180451a20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180451a25  lea     rcx, [rbp+57h+var_68]
0x180451a29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180451a2e  jmp     loc_180451997
0x180451a33  mov     [rbp+57h+var_60], rsi
0x180451a37  mov     rdi, [rbp+57h+var_68]
0x180451a3b  mov     rax, [rdi]
0x180451a3e  mov     rbx, [rax]
0x180451a41  lea     rcx, [rbp+57h+var_60]
0x180451a45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180451a4a  lea     r8, [rbp+57h+var_60]
0x180451a4e  lea     rdx, _GUID_f10ff47a_c551_404d_9a7f_379d7d40b973
0x180451a55  mov     rcx, rdi
0x180451a58  mov     rax, rbx
0x180451a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180451a60  mov     ebx, eax
0x180451a62  test    eax, eax
0x180451a64  jns     short loc_180451A89
0x180451a66  mov     rcx, [rbp+5Fh]; this
0x180451a6a  mov     r9d, eax; char *
0x180451a6d  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451a74  mov     edx, 42h ; 'B'; void *
0x180451a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180451a7e  lea     rcx, [rbp+57h+var_60]
0x180451a82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180451a87  jmp     short loc_180451A25
0x180451a89  mov     [rbp+57h+string], rsi
0x180451a8d  mov     rdi, [rbp+57h+var_60]
0x180451a91  mov     rax, [rdi]
0x180451a94  mov     rbx, [rax+40h]
0x180451a98  xor     ecx, ecx; string
0x180451a9a  call    cs:__imp_WindowsDeleteString
0x180451aa0  mov     [rbp+57h+string], rsi
0x180451aa4  lea     rdx, [rbp+57h+string]
0x180451aa8  mov     rcx, rdi
0x180451aab  mov     rax, rbx
0x180451aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180451ab3  mov     ebx, eax
0x180451ab5  test    eax, eax
0x180451ab7  jns     short loc_180451AE1
0x180451ab9  mov     rcx, [rbp+5Fh]; this
0x180451abd  mov     r9d, eax; char *
0x180451ac0  lea     r8, aShellIncTaskba_0; "shell\\inc\\TaskbarTelemetryHelper.h"
0x180451ac7  mov     edx, 45h ; 'E'; void *
0x180451acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180451ad1  mov     rcx, [rbp+57h+string]; string
0x180451ad5  call    cs:__imp_WindowsDeleteString
0x180451adb  mov     [rbp+57h+string], rsi
0x180451adf  jmp     short loc_180451A7E
0x180451ae1  mov     r14, rsi
0x180451ae4  mov     qword ptr [rsp+130h+hstringHeader.Reserved], rsi
0x180451ae9  mov     qword ptr [rsp+130h+hstringHeader.Reserved+8], rsi
0x180451aee  mov     qword ptr [rsp+130h+hstringHeader.Reserved+10h], rsi
0x180451af3  mov     rdi, rsi
0x180451af6  mov     [rbp+57h+var_D0], rsi
0x180451afa  mov     [rbp+57h+var_C8], rsi
0x180451afe  mov     [rbp+57h+var_C0], rsi
0x180451b02  mov     [rbp+57h+var_B8], rsi
0x180451b06  xor     ecx, ecx
  ... truncated ...
```
