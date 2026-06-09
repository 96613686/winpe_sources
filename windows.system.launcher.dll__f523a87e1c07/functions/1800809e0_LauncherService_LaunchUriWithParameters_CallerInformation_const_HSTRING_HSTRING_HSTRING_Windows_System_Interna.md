# LauncherService::LaunchUriWithParameters(CallerInformation const &,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::System::Internal::Launch::InternalLauncherOptions,Windows::System::ILauncherUIOptions *,LAUNCH_PARAMETERS const *,ILauncherTarget *,int,HSTRING__ *)

- ea: `0x1800809e0`
- end: `0x1800814d7`
- name: `?LaunchUriWithParameters@LauncherService@@SAJAEBVCallerInformation@@PEAUHSTRING__@@11W4InternalLauncherOptions@Launch@Internal@System@Windows@@PEAUILauncherUIOptions@78@PEBULAUNCH_PARAMETERS@@PEAUILauncherTarget@@H1@Z`
- size: `2807`
- prototype: `__int64 __fastcall(__int64, HSTRING, HSTRING, __int64, int, __int64, unsigned int *, __int64, int, HSTRING string)`
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800808f0`
- `0x1800b2504`
- `0x1800b2bec`
- `0x1800b79f0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x18002cec0`
- `0x1800398c8`
- `0x1800486d8`
- `0x180075ce4`
- `0x180079650`
- `0x1800809e0`
- `0x1800814e0`
- `0x180081548`
- `0x1800815b8`
- `0x180081610`
- `0x180081684`
- `0x18008173c`
- `0x18008a030`
- `0x1800aa850`
- `0x1800ae6b0`
- `0x1800ae78c`
- `0x1800aed9c`
- `0x1800af2bc`
- `0x1800b4158`
- `0x1800b73a4`
- `0x1800b7668`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180081294`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180081294`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180081350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180081350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180080aca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180080aca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080a8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081085`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800810df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800810f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800812ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800812df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008133a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008138b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080a8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081085`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800810df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800810f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800812ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800812df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008133a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008138b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080e73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080f9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008105b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008146c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080e73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080f9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008105b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008146c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180080c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180080c13`

## string_xrefs

- `0x180080ae2`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080b63`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080c28`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080cf0`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080d17`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080de1`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080e5c`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080e94`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080f1e`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080ff0`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180081044`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800810a7`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800811ec`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180081221`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180080a93`: `LaunchUri`
- `0x180080ccb`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180081287`: `token`

## pseudocode

```c
__int64 __fastcall LauncherService::LaunchUriWithParameters(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7,
        __int64 a8,
        int a9,
        HSTRING string)
{
  __int64 v12; // r13
  const unsigned __int16 *StringRawBuffer; // rbx
  const WCHAR *v14; // rax
  struct Windows::Foundation::IUriRuntimeClass *v15; // rdi
  __int64 (__fastcall *v16)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v17; // eax
  int v18; // r15d
  bool v19; // r14
  bool v20; // r12
  bool v21; // di
  HSTRING v22; // rcx
  HSTRING *v23; // rbx
  HRESULT v24; // eax
  int v25; // eax
  int v26; // ebx
  int v27; // eax
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, _QWORD, struct IUnknown *); // r15
  struct IUnknown *v30; // rdi
  _QWORD *v31; // rax
  int v32; // eax
  __int64 v33; // rdi
  int v34; // ebx
  unsigned int v35; // edi
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v39; // eax
  unsigned __int64 v40; // rbx
  HSTRING *OriginatingApplicationUserModelId; // rax
  const unsigned __int16 *v42; // rax
  int IsCallerRunningOnLock; // eax
  bool v44; // al
  const unsigned __int16 *v45; // rax
  CLockScreenInterop *v46; // rcx
  int CanTargetRunAboveLock; // eax
  int v48; // eax
  int v49; // eax
  const WCHAR *v50; // rax
  int v51; // ebx
  HSTRING v52; // r14
  int bIgnoreCase; // [rsp+20h] [rbp-2B8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-2B8h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-2B8h]
  bool v56; // [rsp+60h] [rbp-278h] BYREF
  char v57; // [rsp+61h] [rbp-277h] BYREF
  bool v58; // [rsp+62h] [rbp-276h] BYREF
  __int64 v59; // [rsp+68h] [rbp-270h] BYREF
  HSTRING v60; // [rsp+70h] [rbp-268h] BYREF
  unsigned int v61; // [rsp+78h] [rbp-260h] BYREF
  HSTRING newString; // [rsp+80h] [rbp-258h] BYREF
  HSTRING v63; // [rsp+88h] [rbp-250h] BYREF
  int v64[2]; // [rsp+90h] [rbp-248h] BYREF
  struct IUnknown *v65; // [rsp+98h] [rbp-240h] BYREF
  HSTRING v66; // [rsp+A0h] [rbp-238h] BYREF
  void *v67; // [rsp+A8h] [rbp-230h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v68; // [rsp+B0h] [rbp-228h] BYREF
  HSTRING v69; // [rsp+B8h] [rbp-220h] BYREF
  HSTRING v70; // [rsp+C0h] [rbp-218h] BYREF
  __int64 v71; // [rsp+C8h] [rbp-210h] BYREF
  unsigned int *v72; // [rsp+D0h] [rbp-208h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-200h] BYREF
  HSTRING v74; // [rsp+E0h] [rbp-1F8h] BYREF
  HSTRING v75; // [rsp+E8h] [rbp-1F0h] BYREF
  unsigned int *v76; // [rsp+F0h] [rbp-1E8h]
  HSTRING v77; // [rsp+F8h] [rbp-1E0h]
  __int64 v78; // [rsp+100h] [rbp-1D8h]
  __int64 v79; // [rsp+108h] [rbp-1D0h]
  HSTRING v80; // [rsp+110h] [rbp-1C8h]
  HSTRING_HEADER hstringHeader; // [rsp+118h] [rbp-1C0h] BYREF
  __int64 v82; // [rsp+130h] [rbp-1A8h]
  _QWORD v83[42]; // [rsp+140h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v79 = a4;
  v69 = a3;
  v80 = a2;
  v75 = a2;
  v74 = a3;
  v73 = a4;
  v78 = a6;
  v76 = a7;
  v72 = a7;
  v12 = a8;
  v71 = a8;
  v77 = string;
  v70 = string;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v83);
  v83[0] = &LauncherServiceProvider::LaunchUri::`vftable';
  LauncherServiceProvider::LaunchUri::StartActivity((LauncherServiceProvider::LaunchUri *)v83, StringRawBuffer);
  if ( WindowsIsStringEmpty(a2) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
  v14 = WindowsGetStringRawBuffer(a2, 0);
  CreateRuntimeUri(&v68, v14);
  v63 = 0;
  v15 = v68;
  v16 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v68 + 136LL);
  WindowsDeleteString(0);
  v63 = 0;
  v17 = v16(v15, &v63);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v17,
      bIgnoreCase);
  v18 = a9;
  v19 = a9 == 0;
  CallerInformation::GetOriginatingApplicationUserModelId(a1, &v66);
  v20 = 0;
  v58 = 0;
  v21 = v76 && (unsigned __int8)IsUriWithResultsLaunchType(*v76);
  v57 = v21;
  v22 = 0;
  newString = 0;
  if ( v12 )
  {
    v23 = (HSTRING *)(v12 - 8);
    v60 = (HSTRING)(v12 - 8);
    if ( v12 != 8 )
    {
      (*((void (__fastcall **)(__int64))*v23 + 1))(v12 - 8);
      v22 = newString;
    }
    WindowsDeleteString(v22);
    newString = 0;
    v24 = WindowsDuplicateString(v23[10], &newString);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v24,
        bIgnoreCase);
    (*((void (__fastcall **)(__int64))*v23 + 2))(v12 - 8);
  }
  v61 = 0;
  if ( v18 )
    goto LABEL_56;
  if ( !IsComposableShellEnabled() )
  {
    *(_QWORD *)v64 = 0;
    v39 = CLockScreenInterop::Initialize((CLockScreenInterop *)v64);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v39,
        bIgnoreCase);
    v40 = *(_QWORD *)a1;
    OriginatingApplicationUserModelId = (HSTRING *)CallerInformation::GetOriginatingApplicationUserModelId(a1, &v60);
    v42 = WindowsGetStringRawBuffer(*OriginatingApplicationUserModelId, 0);
    IsCallerRunningOnLock = CLockScreenInterop::IsCallerRunningOnLock((CLockScreenInterop *)v64, v42, v40, &v58);
    if ( IsCallerRunningOnLock < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x376,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)IsCallerRunningOnLock,
        bIgnoreCase);
    WindowsDeleteString(v60);
    v44 = 0;
    v56 = 0;
    v20 = v58;
    if ( !v58 )
      goto LABEL_54;
    if ( v12 )
    {
      v45 = WindowsGetStringRawBuffer(newString, 0);
      CanTargetRunAboveLock = CLockScreenInterop::CanTargetRunAboveLock(v46, v45, &v56);
      if ( CanTargetRunAboveLock < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37C,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)CanTargetRunAboveLock,
          bIgnoreCase);
      v44 = v56;
    }
    if ( v21 || v44 )
    {
LABEL_54:
      v19 = 0;
    }
    else
    {
      LODWORD(v59) = 1;
      v60 = (HSTRING)WindowsGetStringRawBuffer(v63, 0);
      v67 = (void *)WindowsGetStringRawBuffer(v66, 0);
      LauncherServiceProvider::LaunchUri::LaunchFromLockScreen<unsigned __int64 const &,unsigned short const *,unsigned short const *,bool const &,int>(
        (unsigned int)v83,
        a1,
        (unsigned int)&v67,
        (unsigned int)&v60,
        (__int64)&v57,
        (__int64)&v59);
      v65 = 0;
      v60 = v66;
      v67 = newString;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      v48 = Microsoft::WRL::Details::MakeAndInitialize<LauncherCachedUriLaunch,Windows::System::Private::IPendingLaunch,CallerInformation const &,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &,enum Windows::System::Internal::Launch::InternalLauncherOptions &,HSTRING__ *,HSTRING__ *,LAUNCH_PARAMETERS const * &,ILauncherTarget * &,HSTRING__ * &>(
              (unsigned int)&v65,
              a1,
              (unsigned int)&v75,
              (unsigned int)&v74,
              (__int64)&v73,
              (__int64)&a5,
              (__int64)&v67,
              (__int64)&v60,
              (__int64)&v72,
              (__int64)&v71,
              (__int64)&v70);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x385,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v48,
          bIgnoreCaseb);
      v49 = CLockScreenInterop::CacheLaunchRequest((CLockScreenInterop *)v64, v65);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x386,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v49,
          bIgnoreCaseb);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v64);
LABEL_56:
    v35 = v61;
    goto LABEL_57;
  }
  if ( v21 )
  {
    v35 = 0;
    goto LABEL_60;
  }
  v59 = 0;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.ActivationPolicy",
    0x22u,
    0x21u);
  v25 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
          v82,
          0,
          &GUID_30b590d9_f894_4572_a394_99378a14d7d8,
          &v59);
  v26 = v25;
  if ( v25 >= 0 )
    v26 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)(unsigned int)v25,
      bIgnoreCase);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v26,
      bIgnoreCase);
  if ( !v59 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x361,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x8000FFFFLL,
      bIgnoreCase);
  v65 = 0;
  v67 = v66;
  v60 = newString;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v27 = Microsoft::WRL::Details::MakeAndInitialize<LauncherCachedUriLaunch,Windows::System::Private::IPendingLaunch,CallerInformation const &,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &,enum Windows::System::Internal::Launch::InternalLauncherOptions &,HSTRING__ *,HSTRING__ *,LAUNCH_PARAMETERS const * &,ILauncherTarget * &,HSTRING__ * &>(
          (unsigned int)&v65,
          a1,
          (unsigned int)&v75,
          (unsigned int)&v74,
          (__int64)&v73,
          (__int64)&a5,
          (__int64)&v60,
          (__int64)&v67,
          (__int64)&v72,
          (__int64)&v71,
          (__int64)&v70);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x365,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v27,
      bIgnoreCasea);
  *(_QWORD *)v64 = 0;
  v28 = v59;
  v29 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IUnknown *))(*(_QWORD *)v59 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v64);
  v30 = v65;
  v31 = (_QWORD *)CallerInformation::GetOriginatingApplicationUserModelId(a1, &v60);
  v32 = v29(v28, *v31, 0, v30);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x368,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v32,
      (int)v64);
  WindowsDeleteString(v60);
  v33 = *(_QWORD *)v64;
  if ( !*(_QWORD *)v64 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x8000FFFFLL,
      (int)v64);
  v61 = 0;
  v34 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<int>,Windows::Foundation::IAsyncOperation<int>>(*(_QWORD *)v64);
  if ( v34 >= 0 )
  {
    v34 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 64LL))(v33, &v61);
    if ( v34 >= 0 )
    {
      v35 = v61;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v64);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      v36 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
LABEL_57:
      if ( v19 )
      {
LABEL_66:
        wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v83,
          0);
        WindowsDeleteString(newString);
        newString = 0;
        WindowsDeleteString(v66);
        v66 = 0;
        WindowsDeleteString(v63);
        v63 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        LauncherServiceProvider::LaunchUri::~LaunchUri((LauncherServiceProvider::LaunchUri *)v83);
        return v35;
      }
LABEL_60:
      v50 = WindowsGetStringRawBuffer(v63, 0);
      if ( CompareStringOrdinal(v50, -1, L"token", 5, 1) == 2 )
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      if ( v20 )
      {
        v51 = a5 | 0x10;
        LODWORD(v59) = 0;
        v60 = (HSTRING)WindowsGetStringRawBuffer(v63, 0);
        v67 = (void *)WindowsGetStringRawBuffer(v66, 0);
        LauncherServiceProvider::LaunchUri::LaunchFromLockScreen<unsigned __int64 const &,unsigned short const *,unsigned short const *,bool const &,int>(
          (unsigned int)v83,
          a1,
          (unsigned int)&v67,
          (unsigned int)&v60,
          (__int64)&v57,
          (__int64)&v59);
        v52 = v69;
      }
      else
      {
        v57 = *(_BYTE *)(a1 + 32);
        v60 = (HSTRING)WindowsGetStringRawBuffer(newString, 0);
        v52 = v69;
        LODWORD(v59) = WindowsGetStringLen(v69);
        v51 = a5;
        v56 = a5 & 1;
        v67 = (void *)WindowsGetStringRawBuffer(v63, 0);
        v69 = (HSTRING)WindowsGetStringRawBuffer(v66, 0);
        LauncherServiceProvider::LaunchUri::LaunchUriRequest<unsigned __int64 const &,unsigned short const *,unsigned short const *,bool,unsigned int,unsigned short const *,unsigned char>(
          (unsigned int)v83,
          a1,
          (unsigned int)&v69,
          (unsigned int)&v67,
          (__int64)&v56,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&v57);
      }
      LaunchTargetApp(a1, v80, v68, 0, v52, v79, v51, v78, v76, v12, v77);
      goto LABEL_66;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x36C,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
    (const char *)(unsigned int)v34,
    (int)v64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v37 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(v66);
  v66 = 0;
  WindowsDeleteString(v63);
  v63 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  LauncherServiceProvider::LaunchUri::~LaunchUri((LauncherServiceProvider::LaunchUri *)v83);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1800809e0  mov     r11, rsp
0x1800809e3  push    rbx
0x1800809e4  push    rsi
0x1800809e5  push    rdi
0x1800809e6  push    r12
0x1800809e8  push    r13
0x1800809ea  push    r14
0x1800809ec  push    r15
0x1800809ee  sub     rsp, 2A0h
0x1800809f5  mov     rax, cs:__security_cookie
0x1800809fc  xor     rax, rsp
0x1800809ff  mov     [rsp+2D8h+var_48], rax
0x180080a07  mov     [r11-1D0h], r9
0x180080a0e  mov     rax, r8
0x180080a11  mov     [r11-220h], rax
0x180080a18  mov     rdi, rdx
0x180080a1b  mov     [r11-1C8h], rdx
0x180080a22  mov     rsi, rcx
0x180080a25  mov     [r11-1F0h], rdx
0x180080a2c  mov     [r11-1F8h], rax
0x180080a33  mov     [r11-200h], r9
0x180080a3a  mov     rax, [rsp+2D8h+arg_28]
0x180080a42  mov     [rsp+2D8h+var_1D8], rax
0x180080a4a  mov     rax, [rsp+2D8h+arg_30]
0x180080a52  mov     [r11-1E8h], rax
0x180080a59  mov     [r11-208h], rax
0x180080a60  mov     r13, [rsp+2D8h+arg_38]
0x180080a68  mov     [r11-210h], r13
0x180080a6f  mov     rax, [rsp+2D8h+string]
0x180080a77  mov     [r11-1E0h], rax
0x180080a7e  mov     [r11-218h], rax
0x180080a85  xor     edx, edx; length
0x180080a87  mov     rcx, rax; string
0x180080a8a  call    cs:__imp_WindowsGetStringRawBuffer
0x180080a90  mov     rbx, rax
0x180080a93  lea     rdx, aLaunchuri_0; "LaunchUri"
0x180080a9a  lea     rcx, [rsp+2D8h+var_198]; struct wil::details::IFailureCallback *
0x180080aa2  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180080aa7  lea     rax, ??_7LaunchUri@LauncherServiceProvider@@6B@; const LauncherServiceProvider::LaunchUri::`vftable'
0x180080aae  mov     [rsp+2D8h+var_198], rax
0x180080ab6  mov     rdx, rbx; unsigned __int16 *
0x180080ab9  lea     rcx, [rsp+2D8h+var_198]; this
0x180080ac1  call    ?StartActivity@LaunchUri@LauncherServiceProvider@@QEAAXPEBG@Z; LauncherServiceProvider::LaunchUri::StartActivity(ushort const *)
0x180080ac6  nop
0x180080ac7  mov     rcx, rdi; string
0x180080aca  call    cs:__imp_WindowsIsStringEmpty
0x180080ad0  mov     rcx, [rsp+2D8h]; this
0x180080ad8  test    eax, eax
0x180080ada  jz      short loc_180080AF3
0x180080adc  mov     r9d, 80070057h; char *
0x180080ae2  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080ae9  mov     edx, 33Bh; void *
0x180080aee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080af3  xor     edx, edx; length
0x180080af5  mov     rcx, rdi; string
0x180080af8  call    cs:__imp_WindowsGetStringRawBuffer
0x180080afe  mov     rdx, rax; sourceString
0x180080b01  lea     rcx, [rsp+2D8h+var_228]; struct Windows::Foundation::IUriRuntimeClass **
0x180080b09  call    ?CreateRuntimeUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEBG@Z; CreateRuntimeUri(ushort const *)
0x180080b0e  nop
0x180080b0f  mov     [rsp+2D8h+var_250], 0
0x180080b1b  mov     rdi, [rsp+2D8h+var_228]
0x180080b23  mov     rax, [rdi]
0x180080b26  mov     rbx, [rax+88h]
0x180080b2d  xor     ecx, ecx; string
0x180080b2f  call    cs:__imp_WindowsDeleteString
0x180080b35  mov     [rsp+2D8h+var_250], 0
0x180080b41  lea     rdx, [rsp+2D8h+var_250]
0x180080b49  mov     rcx, rdi
0x180080b4c  mov     rax, rbx
0x180080b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b54  mov     rcx, [rsp+2D8h]; this
0x180080b5c  test    eax, eax
0x180080b5e  jns     short loc_180080B74
0x180080b60  mov     r9d, eax; char *
0x180080b63  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080b6a  mov     edx, 33Fh; void *
0x180080b6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080b74  mov     r15d, [rsp+2D8h+arg_40]
0x180080b7c  test    r15d, r15d
0x180080b7f  setz    r14b
0x180080b83  lea     rdx, [rsp+2D8h+var_238]
0x180080b8b  mov     rcx, rsi
0x180080b8e  call    ?GetOriginatingApplicationUserModelId@CallerInformation@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; CallerInformation::GetOriginatingApplicationUserModelId(void)
0x180080b93  nop
0x180080b94  xor     r12b, r12b
0x180080b97  mov     [rsp+2D8h+var_276], r12b
0x180080b9c  mov     rax, [rsp+2D8h+var_1E8]
0x180080ba4  test    rax, rax
0x180080ba7  jz      short loc_180080BB9
0x180080ba9  mov     ecx, [rax]
0x180080bab  call    IsUriWithResultsLaunchType
0x180080bb0  test    al, al
0x180080bb2  jz      short loc_180080BB9
0x180080bb4  mov     dil, 1
0x180080bb7  jmp     short loc_180080BBC
0x180080bb9  xor     dil, dil
0x180080bbc  mov     [rsp+2D8h+var_277], dil
0x180080bc1  xor     ecx, ecx
0x180080bc3  mov     [rsp+2D8h+newString], rcx
0x180080bcb  test    r13, r13
0x180080bce  jz      short loc_180080C4A
0x180080bd0  lea     rbx, [r13-8]
0x180080bd4  mov     [rsp+2D8h+var_268], rbx
0x180080bd9  test    rbx, rbx
0x180080bdc  jz      short loc_180080BF5
0x180080bde  mov     rax, [rbx]
0x180080be1  mov     rcx, rbx
0x180080be4  mov     rax, [rax+8]
0x180080be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080bed  mov     rcx, [rsp+2D8h+newString]; string
0x180080bf5  call    cs:__imp_WindowsDeleteString
0x180080bfb  mov     [rsp+2D8h+newString], 0
0x180080c07  lea     rdx, [rsp+2D8h+newString]; newString
0x180080c0f  mov     rcx, [rbx+50h]; string
0x180080c13  call    cs:__imp_WindowsDuplicateString
0x180080c19  mov     rcx, [rsp+2D8h]; this
0x180080c21  test    eax, eax
0x180080c23  jns     short loc_180080C3A
0x180080c25  mov     r9d, eax; char *
0x180080c28  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080c2f  mov     edx, 34Ch; void *
0x180080c34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080c3a  mov     rax, [rbx]
0x180080c3d  mov     rcx, rbx
0x180080c40  mov     rax, [rax+10h]
0x180080c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080c49  nop
0x180080c4a  mov     [rsp+2D8h+var_260], 0
0x180080c52  test    r15d, r15d
0x180080c55  jnz     loc_180081254
0x180080c5b  call    ?IsComposableShellEnabled@@YA_NXZ; IsComposableShellEnabled(void)
0x180080c60  xor     r15d, r15d
0x180080c63  test    al, al
0x180080c65  jz      loc_180080FCC
0x180080c6b  test    dil, dil
0x180080c6e  jnz     loc_180081266
0x180080c74  mov     [rsp+2D8h+var_270], r15
0x180080c79  mov     [rsp+2D8h+var_1A8], r15
0x180080c81  lea     r9d, [r15+21h]; unsigned int
0x180080c85  lea     r8d, [r15+22h]; unsigned int
0x180080c89  lea     rdx, aWindowsInterna_2; "Windows.Internal.ActivationPolicy"
0x180080c90  lea     rcx, [rsp+2D8h+hstringHeader]; hstringHeader
0x180080c98  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180080c9d  nop
0x180080c9e  lea     r9, [rsp+2D8h+var_270]
0x180080ca3  lea     r8, _GUID_30b590d9_f894_4572_a394_99378a14d7d8
0x180080caa  mov     edx, r15d
0x180080cad  mov     rcx, [rsp+2D8h+var_1A8]
0x180080cb5  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180080cba  mov     ebx, eax
0x180080cbc  test    eax, eax
0x180080cbe  jns     short loc_180080CDE
0x180080cc0  mov     rcx, [rsp+2D8h]; this
0x180080cc8  mov     r9d, eax; char *
0x180080ccb  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180080cd2  mov     edx, 299h; void *
0x180080cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080cdc  jmp     short loc_180080CE1
0x180080cde  mov     ebx, r15d
0x180080ce1  mov     rcx, [rsp+2D8h]; this
0x180080ce9  test    ebx, ebx
0x180080ceb  jns     short loc_180080D02
0x180080ced  mov     r9d, ebx; char *
0x180080cf0  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080cf7  mov     edx, 360h; void *
0x180080cfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080d02  mov     rcx, [rsp+2D8h]; this
0x180080d0a  cmp     [rsp+2D8h+var_270], r15
0x180080d0f  jnz     short loc_180080D28
0x180080d11  mov     r9d, 8000FFFFh; char *
0x180080d17  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080d1e  mov     edx, 361h; void *
0x180080d23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080d28  mov     [rsp+2D8h+var_240], r15
0x180080d30  mov     rax, [rsp+2D8h+var_238]
0x180080d38  mov     [rsp+2D8h+var_230], rax
0x180080d40  mov     rax, [rsp+2D8h+newString]
0x180080d48  mov     [rsp+2D8h+var_268], rax
0x180080d4d  lea     rcx, [rsp+2D8h+var_240]
0x180080d55  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180080d5a  lea     rax, [rsp+2D8h+var_218]
0x180080d62  mov     [rsp+2D8h+var_288], rax
0x180080d67  lea     rax, [rsp+2D8h+var_210]
0x180080d6f  mov     [rsp+2D8h+var_290], rax
0x180080d74  lea     rax, [rsp+2D8h+var_208]
0x180080d7c  mov     [rsp+2D8h+var_298], rax
0x180080d81  lea     rax, [rsp+2D8h+var_230]
0x180080d89  mov     [rsp+2D8h+var_2A0], rax
0x180080d8e  lea     rax, [rsp+2D8h+var_268]
0x180080d93  mov     [rsp+2D8h+var_2A8], rax
0x180080d98  lea     rax, [rsp+2D8h+arg_20]
0x180080da0  mov     [rsp+2D8h+var_2B0], rax
0x180080da5  lea     rax, [rsp+2D8h+var_200]
0x180080dad  mov     qword ptr [rsp+2D8h+bIgnoreCase], rax; int
0x180080db2  lea     r9, [rsp+2D8h+var_1F8]
0x180080dba  lea     r8, [rsp+2D8h+var_1F0]
0x180080dc2  mov     rdx, rsi
0x180080dc5  lea     rcx, [rsp+2D8h+var_240]
0x180080dcd  call    ??$MakeAndInitialize@VLauncherCachedUriLaunch@@UIPendingLaunch@Private@System@Windows@@AEBVCallerInformation@@AEAPEAUHSTRING__@@AEAPEAU7@AEAPEAU7@AEAW4InternalLauncherOptions@Launch@Internal@45@PEAU7@PEAU7@AEAPEBULAUNCH_PARAMETERS@@AEAPEAUILauncherTarget@@AEAPEAU7@@Details@WRL@Microsoft@@YAJPEAPEAUIPendingLaunch@Private@System@Windows@@AEBVCallerInformation@@AEAPEAUHSTRING__@@22AEAW4InternalLauncherOptions@Launch@Internal@56@$$QEAPEAU8@4AEAPEBULAUNCH_PARAMETERS@@AEAPEAUILauncherTarget@@2@Z; Microsoft::WRL::Details::MakeAndInitialize<LauncherCachedUriLaunch,Windows::System::Private::IPendingLaunch,CallerInformation const &,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &,Windows::System::Internal::Launch::InternalLauncherOptions &,HSTRING__ *,HSTRING__ *,LAUNCH_PARAMETERS const * &,ILauncherTarget * &,HSTRING__ * &>(Windows::System::Private::IPendingLaunch * *,CallerInformation const &,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &,Windows::System::Internal::Launch::InternalLauncherOptions &,HSTRING__ * &&,HSTRING__ * &&,LAUNCH_PARAMETERS const * &,ILauncherTarget * &,HSTRING__ * &)
0x180080dd2  mov     rcx, [rsp+2D8h]; this
0x180080dda  test    eax, eax
0x180080ddc  jns     short loc_180080DF2
0x180080dde  mov     r9d, eax; char *
0x180080de1  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080de8  mov     edx, 365h; void *
0x180080ded  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080df2  mov     qword ptr [rsp+2D8h+var_248], r15
0x180080dfa  mov     rbx, [rsp+2D8h+var_270]
0x180080dff  mov     rax, [rbx]
0x180080e02  mov     r15, [rax+40h]
0x180080e06  lea     rcx, [rsp+2D8h+var_248]
0x180080e0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180080e13  mov     rdi, [rsp+2D8h+var_240]
0x180080e1b  lea     rdx, [rsp+2D8h+var_268]
0x180080e20  mov     rcx, rsi
0x180080e23  call    ?GetOriginatingApplicationUserModelId@CallerInformation@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; CallerInformation::GetOriginatingApplicationUserModelId(void)
0x180080e28  nop
0x180080e29  lea     rcx, [rsp+2D8h+var_248]
0x180080e31  mov     qword ptr [rsp+2D8h+bIgnoreCase], rcx; int
0x180080e36  mov     r9, rdi
0x180080e39  xor     r8d, r8d
0x180080e3c  mov     rdx, [rax]
0x180080e3f  mov     rcx, rbx
0x180080e42  mov     rax, r15
0x180080e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e4a  mov     rcx, [rsp+2D8h]; this
0x180080e52  xor     r15d, r15d
0x180080e55  test    eax, eax
0x180080e57  jns     short loc_180080E6E
0x180080e59  mov     r9d, eax; char *
0x180080e5c  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080e63  mov     edx, 368h; void *
0x180080e68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080e6e  mov     rcx, [rsp+2D8h+var_268]; string
0x180080e73  call    cs:__imp_WindowsDeleteString
0x180080e79  mov     rcx, [rsp+2D8h]; this
0x180080e81  mov     rdi, qword ptr [rsp+2D8h+var_248]
0x180080e89  test    rdi, rdi
0x180080e8c  jnz     short loc_180080EA5
0x180080e8e  mov     r9d, 8000FFFFh; char *
0x180080e94  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080e9b  mov     edx, 369h; void *
0x180080ea0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080ea5  mov     [rsp+2D8h+var_260], r15d
0x180080eaa  mov     rcx, rdi
0x180080ead  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@U?$IAsyncOperation@H@23@@@YAJPEAU?$IAsyncOperation@H@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<int>,Windows::Foundation::IAsyncOperation<int>>(Windows::Foundation::IAsyncOperation<int> *,tagCOWAIT_FLAGS,void *)
0x180080eb2  mov     ebx, eax
0x180080eb4  test    eax, eax
0x180080eb6  js      short loc_180080F13
0x180080eb8  mov     rax, [rdi]
0x180080ebb  lea     rdx, [rsp+2D8h+var_260]
0x180080ec0  mov     rcx, rdi
0x180080ec3  mov     rax, [rax+40h]
0x180080ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080ecc  mov     ebx, eax
0x180080ece  test    eax, eax
0x180080ed0  js      short loc_180080F13
0x180080ed2  mov     edi, [rsp+2D8h+var_260]
0x180080ed6  lea     rcx, [rsp+2D8h+var_248]
0x180080ede  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180080ee3  nop
0x180080ee4  lea     rcx, [rsp+2D8h+var_240]
0x180080eec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180080ef1  nop
0x180080ef2  mov     rcx, [rsp+2D8h+var_270]
0x180080ef7  test    rcx, rcx
0x180080efa  jz      short loc_180080F0E
0x180080efc  mov     [rsp+2D8h+var_270], r15
0x180080f01  mov     rax, [rcx]
0x180080f04  mov     rax, [rax+10h]
0x180080f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f0d  nop
0x180080f0e  jmp     loc_18008125B
0x180080f13  mov     rcx, [rsp+2D8h]; this
0x180080f1b  mov     r9d, ebx; char *
0x180080f1e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180080f25  mov     edx, 36Ch; void *
0x180080f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080f2f  nop
0x180080f30  lea     rcx, [rsp+2D8h+var_248]
0x180080f38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180080f3d  nop
0x180080f3e  lea     rcx, [rsp+2D8h+var_240]
0x180080f46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180080f4b  nop
0x180080f4c  mov     rcx, [rsp+2D8h+var_270]
0x180080f51  test    rcx, rcx
0x180080f54  jz      short loc_180080F68
0x180080f56  mov     [rsp+2D8h+var_270], r15
0x180080f5b  mov     rax, [rcx]
0x180080f5e  mov     rax, [rax+10h]
0x180080f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f67  nop
0x180080f68  mov     rcx, [rsp+2D8h+newString]; string
0x180080f70  call    cs:__imp_WindowsDeleteString
0x180080f76  mov     [rsp+2D8h+newString], r15
0x180080f7e  mov     rcx, [rsp+2D8h+var_238]; string
0x180080f86  call    cs:__imp_WindowsDeleteString
0x180080f8c  mov     [rsp+2D8h+var_238], r15
  ... truncated ...
```
