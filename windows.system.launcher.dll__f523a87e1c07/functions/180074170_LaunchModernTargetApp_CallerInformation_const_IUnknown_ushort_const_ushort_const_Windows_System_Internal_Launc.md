# LaunchModernTargetApp(CallerInformation const &,IUnknown *,ushort const *,ushort const *,Windows::System::Internal::Launch::InternalLauncherOptions,LAUNCH_PARAMETERS const *,Windows::System::ILauncherUIOptions *,Windows::Storage::Search::IStorageFileQueryResult *,HSTRING__ *,ushort const *,Windows::System::Private::PendingLaunchType,IInspectable * *)

- ea: `0x180074170`
- end: `0x18007497c`
- name: `?LaunchModernTargetApp@@YAXAEBVCallerInformation@@PEAUIUnknown@@PEBG2W4InternalLauncherOptions@Launch@Internal@System@Windows@@PEBULAUNCH_PARAMETERS@@PEAUILauncherUIOptions@67@PEAUIStorageFileQueryResult@Search@Storage@7@PEAUHSTRING__@@2W4PendingLaunchType@Private@67@PEAPEAUIInspectable@@@Z`
- size: `2060`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180073dc0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x180026ea4`
- `0x180026f74`
- `0x180027108`
- `0x18002cec0`
- `0x180034ba0`
- `0x180041eb4`
- `0x180074170`
- `0x180074984`
- `0x180074e7c`
- `0x180074ec8`
- `0x180075190`
- `0x1800751b8`
- `0x1800752b4`
- `0x1800754f4`
- `0x180075520`
- `0x180075ce4`
- `0x1800891c8`
- `0x18008a030`
- `0x1800aa850`
- `0x1800af18c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800745e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007482f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800745e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007482f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007430a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800748b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800748f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007430a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800748b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800748f5`

## string_xrefs

- `0x18007447c`: `Windows.AppUriHandler`
- `0x180074227`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180074277`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800742a8`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180074337`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18007436d`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800743e2`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180074461`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800744c4`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18007452e`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180074587`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800745c1`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180074672`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800746cf`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800747cd`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180074894`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18007494b`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18007496a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800744e3`: `Windows.Protocol`
- `0x18007464f`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180074618`: `Windows.Internal.PlatformExtensions.UriExperienceLauncher`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall LaunchModernTargetApp(
        const struct CallerInformation *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const WCHAR *a4,
        __int16 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        HSTRING string,
        __int64 a10,
        int a11,
        __int64 a12)
{
  __int64 v14; // r12
  HSTRING *v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int (__fastcall *v19)(const unsigned __int16 *, GUID *, __int64 *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  int v23; // eax
  unsigned __int16 *v24; // r14
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64 *); // rbx
  int v27; // eax
  int (__fastcall *v28)(const unsigned __int16 *, GUID *, __int64 *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING *); // rbx
  int v35; // eax
  __int64 v36; // rsi
  __int64 (__fastcall *v37)(__int64, PVOID, __int64, __int64 *); // rdi
  __int64 v38; // rbx
  HSTRING_HEADER *v39; // rax
  int v40; // eax
  struct Windows::Storage::Streams::IBuffer **v41; // r8
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  int v45; // ebx
  __int64 v46; // rdi
  PCWSTR v47; // rdi
  __int64 (__fastcall *v48)(PCWSTR, GUID *, __int64 *); // rbx
  int v49; // eax
  PVOID Reserved1; // r15
  PVOID v51; // rsi
  HSTRING v52; // r14
  HSTRING_HEADER *v53; // rax
  int v54; // eax
  __int64 v55; // rbx
  unsigned __int16 *v56; // rax
  int v57; // eax
  int v59; // [rsp+28h] [rbp-E0h]
  int v60; // [rsp+28h] [rbp-E0h]
  __int64 v61; // [rsp+78h] [rbp-90h] BYREF
  HSTRING v62; // [rsp+80h] [rbp-88h] BYREF
  int v63[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v64; // [rsp+90h] [rbp-78h] BYREF
  __int64 v65; // [rsp+98h] [rbp-70h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-60h] BYREF
  HSTRING v68; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v70; // [rsp+C0h] [rbp-48h] BYREF
  PCWSTR StringRawBuffer; // [rsp+C8h] [rbp-40h] BYREF
  const WCHAR *v72; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-30h] BYREF
  LauncherMiscHelpers *v74; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int16 *v75; // [rsp+E8h] [rbp-20h]
  const WCHAR *v76; // [rsp+F0h] [rbp-18h] BYREF
  const WCHAR *v77; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v78; // [rsp+108h] [rbp+0h] BYREF
  __int64 v79; // [rsp+118h] [rbp+10h]
  __int64 v80; // [rsp+120h] [rbp+18h]
  const struct CallerInformation *v81; // [rsp+128h] [rbp+20h]
  __int128 v82; // [rsp+138h] [rbp+30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+148h] [rbp+40h] BYREF
  __int64 v84; // [rsp+160h] [rbp+58h]
  HSTRING_HEADER v85; // [rsp+168h] [rbp+60h] BYREF
  HSTRING_HEADER v86; // [rsp+188h] [rbp+80h] BYREF
  HSTRING_HEADER v87; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v88[336]; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+380h] [rbp+278h]

  v75 = a3;
  v81 = a1;
  v76 = a3;
  v77 = a4;
  v79 = a7;
  *(_QWORD *)&v78 = a10;
  v14 = a12;
  *(_QWORD *)&v82 = a12;
  v66 = 0;
  v64 = 0;
  v62 = 0;
  v70 = 0;
  v15 = Windows::Internal::StringReference::StringReference(
          (HSTRING *)&hstringHeader,
          (const unsigned __int16 (*)[33])a2);
  v16 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
          *v15,
          &v70);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x811,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v16,
      v59);
  v74 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.ValueSet",
    0x28u,
    0x27u);
  v17 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
          v84,
          &v74);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x813,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v17,
      v59);
  v69 = 0;
  v18 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v74,
          (__int64)&v69);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x815,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v18,
      v59);
  LOBYTE(v61) = 0;
  v73 = 0;
  *(_QWORD *)v63 = 0;
  v19 = **(int (__fastcall ***)(const unsigned __int16 *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  if ( v19(a2, &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea, &v66) < 0 )
  {
    v28 = **(int (__fastcall ***)(const unsigned __int16 *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    if ( v28(a2, &GUID_9e365e57_48b2_4160_956f_c7385120bbfc, &v64) < 0 || !v64 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x827,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x8000FFFFLL,
        v59);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v63);
    v29 = WriteLaunchProtocolStateToPropertySet(v69, v70, v64, a6, (__int64)v63);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v29,
        v59);
    if ( a11 == 3 )
    {
      v24 = L"Windows.AppUriHandler";
      v72 = L"Windows.AppUriHandler";
      v30 = v64;
      v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 88LL);
      WindowsDeleteString(v62);
      v62 = 0;
      v32 = v31(v30, &v62);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x82F,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v32,
          v59);
    }
    else
    {
      if ( a11 != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x838,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)0x80070057LL,
          v59);
      v24 = L"Windows.Protocol";
      v72 = L"Windows.Protocol";
      v33 = v64;
      v34 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 136LL);
      WindowsDeleteString(v62);
      v62 = 0;
      v35 = v34(v33, &v62);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x834,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v35,
          v59);
    }
  }
  else
  {
    v20 = v66;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v66 + 48LL);
    WindowsDeleteString(v62);
    v62 = 0;
    v22 = v21(v20, &v62);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81E,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v22,
        v59);
    v23 = WriteLaunchFileDataToPropertySet(v69, v70, v66, a8);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v23,
        v59);
    v24 = L"Windows.File";
    v72 = L"Windows.File";
  }
  v68 = 0;
  WindowsDeleteString(0);
  v68 = 0;
  GetCallerPFN(a1, &v68);
  v25 = v70;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v70 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  v27 = v26(v25, v68, &v73);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x840,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v27,
      v59);
  v36 = v69;
  v37 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, __int64 *))(*(_QWORD *)v69 + 80LL);
  v38 = v73;
  v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&off_1801175D8);
  v40 = v37(v36, v39[1].Reserved.Reserved1, v38, &v61);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x841,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v40,
      v59);
  v67 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  v42 = LauncherMiscHelpers::SerializePropertySet(
          v74,
          (struct Windows::Foundation::Collections::IPropertySet *)&v67,
          v41);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x844,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v42,
      v59);
  if ( (a5 & 2) != 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LauncherServiceProvider::ActivateApp::Start<unsigned short const *>((LauncherServiceProvider::ActivateApp *)v88);
    v65 = 0;
    v43 = *(_DWORD *)a1;
    v84 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.PlatformExtensions.UriExperienceLauncher",
      0x3Au,
      0x39u);
    v44 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
            v84,
            v43,
            &GUID_8011190a_441a_4c05_9d4e_f3251f86c61e,
            &v65);
    v45 = v44;
    if ( v44 >= 0 )
      v45 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
        (const char *)(unsigned int)v44,
        v59);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84E,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v45,
        v59);
    v46 = v65;
    if ( !v65 )
    {
      Microsoft::WRL::Details::Make<MinUriExperienceLauncherModalImpl,>(&StringRawBuffer);
      v47 = StringRawBuffer;
      v48 = **(__int64 (__fastcall ***)(PCWSTR, GUID *, __int64 *))StringRawBuffer;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      v49 = v48(v47, &GUID_8011190a_441a_4c05_9d4e_f3251f86c61e, &v65);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x854,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v49,
          v59);
      if ( v47 )
        (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v47 + 16LL))(v47);
      v46 = v65;
    }
    v75 = *(unsigned __int16 **)(*(_QWORD *)v46 + 48LL);
    StringRawBuffer = *(PCWSTR *)v63;
    v80 = v67;
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v77);
    Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v85, (const WCHAR **)&v78)[1].Reserved.Reserved1;
    v51 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, &v76)[1].Reserved.Reserved1;
    v52 = v62;
    v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v87, &v72);
    v78 = ActivationType_LauncherServiceActivation;
    v60 = (int)Reserved1;
    v54 = ((__int64 (__fastcall *)(__int64, PVOID, HSTRING, PVOID))v75)(v46, v53[1].Reserved.Reserved1, v52, v51);
    if ( v54 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x862,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v54,
        (int)Reserved1);
    LauncherServiceProvider::ActivateApp::AppActivation<unsigned short const * &,unsigned short const * &,enum TargetUserContextType const &>(
      (__int64)v88,
      &v76,
      (__int64 *)&v72,
      (char *)v81 + 32);
    wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v88,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    LauncherServiceProvider::ActivateApp::~ActivateApp((LauncherServiceProvider::ActivateApp *)v88);
    v14 = v82;
  }
  else
  {
    v55 = v66;
    v56 = (unsigned __int16 *)WindowsGetStringRawBuffer(v62, 0);
    v82 = ActivationType_LauncherServiceActivation;
    DoLaunch((unsigned int *)a1, (__int64)&v82, v67, *(__int64 *)v63, v24, v56, v75, a5, (char *)string, v55);
  }
  if ( *(_QWORD *)v63 )
  {
    if ( v14 )
    {
      v57 = Microsoft::WRL::ComPtr<Windows::System::IProtocolForResultsOperation>::CopyTo<IInspectable>(v63, v14);
      if ( v57 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x86D,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v57,
          v60);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  WindowsDeleteString(v68);
  v68 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  WindowsDeleteString(v62);
  v62 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
}

```

## disassembly

```asm
0x180074170  mov     rax, rsp
0x180074173  push    rbp
0x180074174  push    rbx
0x180074175  push    rsi
0x180074176  push    rdi
0x180074177  push    r12
0x180074179  push    r13
0x18007417b  push    r14
0x18007417d  push    r15
0x18007417f  lea     rbp, [rax-278h]
0x180074186  sub     rsp, 338h
0x18007418d  movaps  xmmword ptr [rax-58h], xmm6
0x180074191  mov     rax, cs:__security_cookie
0x180074198  xor     rax, rsp
0x18007419b  mov     [rbp+270h+var_60], rax
0x1800741a2  mov     rax, r8
0x1800741a5  mov     [rbp+270h+var_290], rax
0x1800741a9  mov     rdi, rdx
0x1800741ac  mov     r15, rcx
0x1800741af  mov     [rbp+270h+var_250], rcx
0x1800741b3  mov     [rbp+270h+var_288], rax
0x1800741b7  mov     [rbp+270h+var_280], r9
0x1800741bb  mov     r14, [rbp+270h+arg_28]
0x1800741c2  mov     rax, [rbp+270h+arg_30]
0x1800741c9  mov     [rbp+270h+var_260], rax
0x1800741cd  mov     rsi, [rbp+270h+arg_38]
0x1800741d4  mov     r13, [rbp+270h+string]
0x1800741db  mov     rax, [rbp+270h+arg_48]
0x1800741e2  mov     qword ptr [rbp+270h+var_270], rax
0x1800741e6  mov     r12, [rbp+270h+arg_58]
0x1800741ed  mov     qword ptr [rbp+270h+var_240], r12
0x1800741f1  xor     ebx, ebx
0x1800741f3  mov     [rbp+270h+var_2D8], rbx
0x1800741f7  mov     [rbp+270h+var_2E8], rbx
0x1800741fb  mov     [rsp+370h+var_2F8], rbx
0x180074200  mov     [rbp+270h+var_2B8], rbx
0x180074204  lea     rcx, [rbp+270h+hstringHeader]; string
0x180074208  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x18007420d  lea     rdx, [rbp+270h+var_2B8]
0x180074211  mov     rcx, [rax]
0x180074214  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180074219  mov     rcx, [rbp+278h]; this
0x180074220  test    eax, eax
0x180074222  jns     short loc_180074239
0x180074224  mov     r9d, eax; char *
0x180074227  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18007422e  mov     edx, 811h; void *
0x180074233  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074239  mov     [rbp+270h+var_298], rbx
0x18007423d  mov     [rbp+270h+var_218], rbx
0x180074241  mov     r9d, 27h ; '''; unsigned int
0x180074247  lea     r8d, [r9+1]; unsigned int
0x18007424b  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x180074252  lea     rcx, [rbp+270h+hstringHeader]; hstringHeader
0x180074256  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007425b  nop
0x18007425c  lea     rdx, [rbp+270h+var_298]
0x180074260  mov     rcx, [rbp+270h+var_218]
0x180074264  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180074269  mov     rcx, [rbp+278h]; this
0x180074270  test    eax, eax
0x180074272  jns     short loc_180074289
0x180074274  mov     r9d, eax; char *
0x180074277  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18007427e  mov     edx, 813h; void *
0x180074283  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074289  mov     [rbp+270h+var_2C0], rbx
0x18007428d  lea     rdx, [rbp+270h+var_2C0]
0x180074291  lea     rcx, [rbp+270h+var_298]
0x180074295  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18007429a  mov     rcx, [rbp+278h]; this
0x1800742a1  test    eax, eax
0x1800742a3  jns     short loc_1800742BA
0x1800742a5  mov     r9d, eax; char *
0x1800742a8  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800742af  mov     edx, 815h; void *
0x1800742b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800742ba  mov     byte ptr [rsp+370h+var_300], bl
0x1800742be  mov     [rbp+270h+var_2A0], rbx
0x1800742c2  mov     qword ptr [rbp+270h+var_2F0], rbx
0x1800742c6  movups  xmm6, cs:ActivationType_LauncherServiceActivation
0x1800742cd  mov     rax, [rdi]
0x1800742d0  mov     rbx, [rax]
0x1800742d3  lea     rcx, [rbp+270h+var_2D8]
0x1800742d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800742dc  lea     r8, [rbp+270h+var_2D8]
0x1800742e0  lea     rdx, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x1800742e7  mov     rcx, rdi
0x1800742ea  mov     rax, rbx
0x1800742ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742f2  test    eax, eax
0x1800742f4  js      loc_1800743F4
0x1800742fa  mov     rdi, [rbp+270h+var_2D8]
0x1800742fe  mov     rax, [rdi]
0x180074301  mov     rbx, [rax+30h]
0x180074305  mov     rcx, [rsp+370h+var_2F8]; string
0x18007430a  call    cs:__imp_WindowsDeleteString
0x180074310  mov     [rsp+370h+var_2F8], 0
0x180074319  lea     rdx, [rsp+370h+var_2F8]
0x18007431e  mov     rcx, rdi
0x180074321  mov     rax, rbx
0x180074324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074329  mov     rcx, [rbp+278h]; this
0x180074330  test    eax, eax
0x180074332  jns     short loc_180074349
0x180074334  mov     r9d, eax; char *
0x180074337  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18007433e  mov     edx, 81Eh; void *
0x180074343  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074349  mov     r9, rsi
0x18007434c  mov     r8, [rbp+270h+var_2D8]
0x180074350  mov     rdx, [rbp+270h+var_2B8]
0x180074354  mov     rcx, [rbp+270h+var_2C0]
0x180074358  call    ?WriteLaunchFileDataToPropertySet@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUIPropertyValueStatics@34@PEAUIStorageFile@Storage@4@PEAUIStorageFileQueryResult@Search@74@@Z; WriteLaunchFileDataToPropertySet(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::IPropertyValueStatics *,Windows::Storage::IStorageFile *,Windows::Storage::Search::IStorageFileQueryResult *)
0x18007435d  mov     rcx, [rbp+278h]; this
0x180074364  xor     esi, esi
0x180074366  test    eax, eax
0x180074368  jns     short loc_18007437F
0x18007436a  mov     r9d, eax; char *
0x18007436d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180074374  mov     edx, 81Fh; void *
0x180074379  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007437f  lea     r14, aWindowsFile; "Windows.File"
0x180074386  mov     [rbp+270h+var_2A8], r14
0x18007438a  mov     [rbp+270h+var_2C8], rsi
0x18007438e  xor     ecx, ecx; string
0x180074390  call    cs:__imp_WindowsDeleteString
0x180074396  mov     [rbp+270h+var_2C8], rsi
0x18007439a  lea     rdx, [rbp+270h+var_2C8]; HSTRING *
0x18007439e  mov     rcx, r15; struct CallerInformation *
0x1800743a1  call    ?GetCallerPFN@@YAXAEBVCallerInformation@@PEAPEAUHSTRING__@@@Z; GetCallerPFN(CallerInformation const &,HSTRING__ * *)
0x1800743a6  mov     rdi, [rbp+270h+var_2B8]
0x1800743aa  mov     rax, [rdi]
0x1800743ad  mov     rbx, [rax+90h]
0x1800743b4  lea     rcx, [rbp+270h+var_2A0]
0x1800743b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800743bd  lea     r8, [rbp+270h+var_2A0]
0x1800743c1  mov     rdx, [rbp+270h+var_2C8]
0x1800743c5  mov     rcx, rdi
0x1800743c8  mov     rax, rbx
0x1800743cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800743d0  mov     rcx, [rbp+278h]; this
0x1800743d7  test    eax, eax
0x1800743d9  jns     loc_180074540
0x1800743df  mov     r9d, eax; char *
0x1800743e2  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800743e9  mov     edx, 840h; void *
0x1800743ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800743f4  mov     rax, [rdi]
0x1800743f7  mov     rbx, [rax]
0x1800743fa  lea     rcx, [rbp+270h+var_2E8]
0x1800743fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074403  lea     r8, [rbp+270h+var_2E8]
0x180074407  lea     rdx, _GUID_9e365e57_48b2_4160_956f_c7385120bbfc
0x18007440e  mov     rcx, rdi
0x180074411  mov     rax, rbx
0x180074414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074419  xor     esi, esi
0x18007441b  test    eax, eax
0x18007441d  js      loc_18007495D
0x180074423  cmp     [rbp+270h+var_2E8], rsi
0x180074427  jz      loc_18007495D
0x18007442d  lea     rcx, [rbp+270h+var_2F0]
0x180074431  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074436  lea     rax, [rbp+270h+var_2F0]
0x18007443a  mov     qword ptr [rsp+370h+var_350], rax; int
0x18007443f  mov     r9, r14
0x180074442  mov     r8, [rbp+270h+var_2E8]
0x180074446  mov     rdx, [rbp+270h+var_2B8]
0x18007444a  mov     rcx, [rbp+270h+var_2C0]
0x18007444e  call    ?WriteLaunchProtocolStateToPropertySet@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUIPropertyValueStatics@34@PEAUIUriRuntimeClass@34@PEBULAUNCH_PARAMETERS@@PEAPEAUIInspectable@@@Z; WriteLaunchProtocolStateToPropertySet(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::IPropertyValueStatics *,Windows::Foundation::IUriRuntimeClass *,LAUNCH_PARAMETERS const *,IInspectable * *)
0x180074453  mov     rcx, [rbp+278h]; this
0x18007445a  test    eax, eax
0x18007445c  jns     short loc_180074473
0x18007445e  mov     r9d, eax; char *
0x180074461  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180074468  mov     edx, 82Ah; void *
0x18007446d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074473  cmp     [rbp+270h+arg_50], 3
0x18007447a  jnz     short loc_1800744D6
0x18007447c  lea     r14, aWindowsAppurih; "Windows.AppUriHandler"
0x180074483  mov     [rbp+270h+var_2A8], r14
0x180074487  mov     rdi, [rbp+270h+var_2E8]
0x18007448b  mov     rax, [rdi]
0x18007448e  mov     rbx, [rax+58h]
0x180074492  mov     rcx, [rsp+370h+var_2F8]; string
0x180074497  call    cs:__imp_WindowsDeleteString
0x18007449d  mov     [rsp+370h+var_2F8], rsi
0x1800744a2  lea     rdx, [rsp+370h+var_2F8]
0x1800744a7  mov     rcx, rdi
0x1800744aa  mov     rax, rbx
0x1800744ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800744b2  mov     rcx, [rbp+278h]; this
0x1800744b9  test    eax, eax
0x1800744bb  jns     loc_18007438A
0x1800744c1  mov     r9d, eax; char *
0x1800744c4  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800744cb  mov     edx, 82Fh; void *
0x1800744d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800744d6  cmp     [rbp+270h+arg_50], 1
0x1800744dd  jnz     loc_18007493E
0x1800744e3  lea     r14, aWindowsProtoco; "Windows.Protocol"
0x1800744ea  mov     [rbp+270h+var_2A8], r14
0x1800744ee  mov     rdi, [rbp+270h+var_2E8]
0x1800744f2  mov     rax, [rdi]
0x1800744f5  mov     rbx, [rax+88h]
0x1800744fc  mov     rcx, [rsp+370h+var_2F8]; string
0x180074501  call    cs:__imp_WindowsDeleteString
0x180074507  mov     [rsp+370h+var_2F8], rsi
0x18007450c  lea     rdx, [rsp+370h+var_2F8]
0x180074511  mov     rcx, rdi
0x180074514  mov     rax, rbx
0x180074517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007451c  mov     rcx, [rbp+278h]; this
0x180074523  test    eax, eax
0x180074525  jns     loc_18007438A
0x18007452b  mov     r9d, eax; char *
0x18007452e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180074535  mov     edx, 834h; void *
0x18007453a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074540  mov     rsi, [rbp+270h+var_2C0]
0x180074544  mov     rax, [rsi]
0x180074547  mov     rdi, [rax+50h]
0x18007454b  mov     rbx, [rbp+270h+var_2A0]
0x18007454f  lea     rdx, off_1801175D8; "CallerPackageFamilyName"
0x180074556  lea     rcx, [rbp+270h+hstringHeader]
0x18007455a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007455f  nop
0x180074560  lea     r9, [rsp+370h+var_300]
0x180074565  mov     r8, rbx
0x180074568  mov     rdx, [rax+18h]
0x18007456c  mov     rcx, rsi
0x18007456f  mov     rax, rdi
0x180074572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074577  mov     rcx, [rbp+278h]; this
0x18007457e  xor     esi, esi
0x180074580  test    eax, eax
0x180074582  jns     short loc_180074599
0x180074584  mov     r9d, eax; char *
0x180074587  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18007458e  mov     edx, 841h; void *
0x180074593  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074599  mov     [rbp+270h+var_2D0], rsi
0x18007459d  lea     rcx, [rbp+270h+var_2D0]
0x1800745a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800745a6  lea     rdx, [rbp+270h+var_2D0]; struct Windows::Foundation::Collections::IPropertySet *
0x1800745aa  mov     rcx, [rbp+270h+var_298]; this
0x1800745ae  call    ?SerializePropertySet@LauncherMiscHelpers@@YAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAUIBuffer@Streams@Storage@5@@Z; LauncherMiscHelpers::SerializePropertySet(Windows::Foundation::Collections::IPropertySet *,Windows::Storage::Streams::IBuffer * *)
0x1800745b3  mov     rcx, [rbp+278h]; this
0x1800745ba  test    eax, eax
0x1800745bc  jns     short loc_1800745D3
0x1800745be  mov     r9d, eax; char *
0x1800745c1  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800745c8  mov     edx, 844h; void *
0x1800745cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800745d3  mov     edi, dword ptr [rbp+270h+arg_20]
0x1800745d9  xor     edx, edx; length
0x1800745db  test    dil, 2
0x1800745df  jz      loc_180074826
0x1800745e5  mov     rcx, r13; string
0x1800745e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800745ee  mov     [rbp+270h+var_2B0], rax
0x1800745f2  lea     rdx, [rbp+270h+var_2B0]
0x1800745f6  lea     rcx, [rbp+270h+var_1B0]; this
0x1800745fd  call    ??$Start@PEBG@ActivateApp@LauncherServiceProvider@@SA?AV01@$$QEAPEBG@Z; LauncherServiceProvider::ActivateApp::Start<ushort const *>(ushort const * &&)
0x180074602  nop
0x180074603  mov     [rbp+270h+var_2E0], rsi
0x180074607  mov     ebx, [r15]
0x18007460a  mov     [rbp+270h+var_218], rsi
0x18007460e  mov     r9d, 39h ; '9'; unsigned int
0x180074614  lea     r8d, [r9+1]; unsigned int
0x180074618  lea     rdx, aWindowsInterna_1; "Windows.Internal.PlatformExtensions.Uri"...
0x18007461f  lea     rcx, [rbp+270h+hstringHeader]; hstringHeader
0x180074623  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180074628  nop
0x180074629  lea     r9, [rbp+270h+var_2E0]
0x18007462d  lea     r8, _GUID_8011190a_441a_4c05_9d4e_f3251f86c61e
0x180074634  mov     edx, ebx
0x180074636  mov     rcx, [rbp+270h+var_218]
0x18007463a  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x18007463f  mov     ebx, eax
0x180074641  test    eax, eax
0x180074643  jns     short loc_180074662
0x180074645  mov     rcx, [rbp+278h]; this
0x18007464c  mov     r9d, eax; char *
0x18007464f  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180074656  mov     edx, 299h; void *
0x18007465b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074660  jmp     short loc_180074664
0x180074662  mov     ebx, esi
0x180074664  mov     rcx, [rbp+278h]; this
0x18007466b  test    ebx, ebx
0x18007466d  jns     short loc_180074684
0x18007466f  mov     r9d, ebx; char *
0x180074672  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180074679  mov     edx, 84Eh; void *
0x18007467e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074684  mov     rdi, [rbp+270h+var_2E0]
0x180074688  test    rdi, rdi
0x18007468b  jnz     short loc_1800746FA
  ... truncated ...
```
