# DoLaunch(CallerInformation const &,_GUID,Windows::Storage::Streams::IBuffer *,Windows::System::IProtocolForResultsOperation *,ushort const *,ushort const *,ushort const *,Windows::System::Internal::Launch::InternalLauncherOptions,HSTRING__ *,Windows::Storage::IStorageFile *)

- ea: `0x1800891c8`
- end: `0x180089b3a`
- name: `?DoLaunch@@YAXAEBVCallerInformation@@U_GUID@@PEAUIBuffer@Streams@Storage@Windows@@PEAUIProtocolForResultsOperation@System@6@PEBG44W4InternalLauncherOptions@Launch@Internal@86@PEAUHSTRING__@@PEAUIStorageFile@56@@Z`
- size: `2418`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180074170`
- `0x180087fb0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180026ea4`
- `0x180026f74`
- `0x180027108`
- `0x180027a10`
- `0x18002cec0`
- `0x180034ba0`
- `0x18003ab7c`
- `0x180041eb4`
- `0x180042254`
- `0x180042440`
- `0x180042590`
- `0x1800426a0`
- `0x180074e7c`
- `0x1800759b0`
- `0x1800891c8`
- `0x18008a030`
- `0x18008df9c`
- `0x1800a0ee8`
- `0x1800a5b48`
- `0x1800ad104`
- `0x1800b1d68`
- `0x1800b6fe0`
- `0x1800b74d0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800898a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800898a7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800898d7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800898d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008986f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008986f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089741`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089741`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800896b3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800896b3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180089717`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180089717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800895e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008990b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800895e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008990b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089923`

## string_xrefs

- `0x180089975`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18008998a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18008999f`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800899b4`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800899c9`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800899de`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800899f3`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a08`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a1d`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a32`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a47`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a5c`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a71`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a86`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089a9b`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089ab0`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089ac5`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089ada`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089aec`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089afe`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089b16`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180089b28`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall DoLaunch(
        unsigned int *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        __int16 a8,
        char *a9,
        __int64 a10)
{
  const unsigned __int16 *v11; // rsi
  const unsigned __int16 *v12; // rdi
  _QWORD *v13; // r14
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  HSTRING *v16; // rax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  HSTRING v20; // rdi
  __int64 (__fastcall *v21)(HSTRING, __int64, LauncherMiscHelpers **); // rbx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, HSTRING, LauncherMiscHelpers *, char *); // rdi
  LauncherMiscHelpers *v26; // rbx
  int v27; // eax
  int v28; // eax
  void *v29; // rsi
  __int64 (__fastcall *v30)(void *, HSTRING, __int64, char *); // rdi
  __int64 v31; // rbx
  int v32; // eax
  int v33; // eax
  HSTRING_HEADER *v34; // rax
  int v35; // eax
  HSTRING_HEADER *v36; // rax
  int v37; // eax
  struct Windows::Storage::Streams::IBuffer **v38; // r8
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  unsigned __int16 *v43; // rbx
  __int64 v44; // rdx
  int v45; // eax
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v47; // rax
  int v48; // eax
  char *v49; // rbx
  const char *v50; // r9
  DWORD v51; // eax
  const char *v52; // r9
  const char *v53; // r9
  HSTRING *dwCreationFlags; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-E0h]
  char v58[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ExitCode[2]; // [rsp+68h] [rbp-98h] BYREF
  LauncherMiscHelpers *v60; // [rsp+70h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v63; // [rsp+88h] [rbp-78h] BYREF
  LauncherMiscHelpers *v64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v66; // [rsp+A0h] [rbp-60h] BYREF
  DWORD ThreadId; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v69; // [rsp+B8h] [rbp-48h] BYREF
  char *v70; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v71; // [rsp+C8h] [rbp-38h]
  const WCHAR *v72; // [rsp+D0h] [rbp-30h] BYREF
  const WCHAR *v73; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v74; // [rsp+E0h] [rbp-20h]
  __int64 v75; // [rsp+F0h] [rbp-10h]
  __int64 v76; // [rsp+F8h] [rbp-8h]
  __int64 v77; // [rsp+100h] [rbp+0h]
  __int64 v78; // [rsp+108h] [rbp+8h] BYREF
  DWORD dwProcessId; // [rsp+110h] [rbp+10h]
  HSTRING string; // [rsp+130h] [rbp+30h]
  char v81[48]; // [rsp+138h] [rbp+38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+168h] [rbp+68h] BYREF
  HSTRING v83; // [rsp+180h] [rbp+80h]
  HSTRING_HEADER v84; // [rsp+188h] [rbp+88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v76 = a4;
  v77 = a3;
  *(_QWORD *)&v74 = a2;
  v73 = a5;
  v11 = a6;
  v66 = a6;
  v12 = a7;
  v71 = a7;
  v72 = a7;
  v70 = a9;
  v75 = a10;
  v13 = operator new(0x60u);
  *v13 = 0;
  v13[1] = 0;
  v13[2] = 0;
  v13[3] = 0;
  v13[4] = 0;
  v13[7] = 0;
  v13[8] = 0;
  v13[9] = 0;
  *((_DWORD *)v13 + 20) = 0;
  v13[11] = 0;
  v69 = v13;
  v65 = 0;
  v64 = 0;
  v83 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.ValueSet",
    0x28u,
    0x27u);
  v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
          (__int64)v83,
          &v64);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6AE,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v14,
      (int)dwCreationFlags);
  if ( (a8 & 0x400) != 0 )
  {
    v63 = 0;
    v16 = Windows::Internal::StringReference::StringReference(
            (HSTRING *)&hstringHeader,
            (const unsigned __int16 (*)[33])v15);
    v17 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
            *v16,
            &v63);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B3,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v17,
        (int)dwCreationFlags);
    *(_QWORD *)ExitCode = 0;
    v83 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.ValueSet",
      0x28u,
      0x27u);
    v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
            (__int64)v83,
            ExitCode);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B6,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v18,
        (int)dwCreationFlags);
    v68 = 0;
    v19 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))ExitCode,
            (__int64)&v68);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B8,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v19,
        (int)dwCreationFlags);
    v58[0] = 0;
    v60 = 0;
    v20 = v63;
    v21 = *(__int64 (__fastcall **)(HSTRING, __int64, LauncherMiscHelpers **))(*(_QWORD *)v63 + 136LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    LOBYTE(v22) = 1;
    v23 = v21(v20, v22, &v60);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BC,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v23,
        (int)dwCreationFlags);
    v24 = v68;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING, LauncherMiscHelpers *, char *))(*(_QWORD *)v68 + 80LL);
    v26 = v60;
    v83 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsMaximized", 0xCu, 0xBu);
    v27 = v25(v24, v83, v26, v58);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BE,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v27,
        (int)dwCreationFlags);
    TokenHandle = 0;
    v28 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v64,
            (__int64)&TokenHandle);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C3,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v28,
        (int)dwCreationFlags);
    v29 = TokenHandle;
    v30 = *(__int64 (__fastcall **)(void *, HSTRING, __int64, char *))(*(_QWORD *)TokenHandle + 80LL);
    v31 = *(_QWORD *)ExitCode;
    v83 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"CustomAppLaunch_Context",
      0x18u,
      0x17u);
    v32 = v30(v29, v83, v31, v58);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C4,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v32,
        (int)dwCreationFlags);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&TokenHandle);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ExitCode);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v12 = v71;
    v11 = v66;
  }
  v60 = v64;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v60);
  v83 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ViewSizePreferences.DesiredRemainingView",
    0x29u,
    0x28u);
  v33 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v60,
          v83);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D9,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v33,
      (int)dwCreationFlags);
  v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123050);
  v35 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v60,
          (HSTRING)v34[1].Reserved.Reserved1);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6DC,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v35,
      (int)dwCreationFlags);
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123048);
  v37 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v60,
          (HSTRING)v36[1].Reserved.Reserved1);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6DE,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v37,
      (int)dwCreationFlags);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v39 = LauncherMiscHelpers::SerializePropertySet(
          v64,
          (struct Windows::Foundation::Collections::IPropertySet *)&v65,
          v38);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E0,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v39,
      (int)dwCreationFlags);
  WindowsDeleteString(0);
  v63 = 0;
  GetActivationInfo(a5, v11, v12, (a8 & 8) != 0, dwCreationFlags, &v63);
  v62 = 0;
  v83 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Activation.Private.ApplicationActivationProperties",
    0x4Cu,
    0x4Bu);
  v40 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationProperties>>(
          (__int64)v83,
          &v62);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E8,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v40,
      dwCreationFlagsa);
  v41 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 72LL))(v62, a1[2]);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E9,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v41,
      dwCreationFlagsa);
  v42 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 104LL))(v62, v65);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6EA,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v42,
      dwCreationFlagsa);
  ExitCode[0] = -1;
  RtlGetDeviceFamilyInfoEnum(0, ExitCode, 0);
  if ( ExitCode[0] == 3 && !(unsigned __int8)IsRuntimeBehaviorUniversal(v12) )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 56LL))(v62, 0x1000000);
  CallerInformation::CallerInformation((CallerInformation *)&v78, (const struct CallerInformation *)a1);
  if ( v78 )
  {
    if ( dwProcessId )
    {
      TokenHandle = 0;
      v43 = (unsigned __int16 *)OpenProcess(0x1000u, 0, dwProcessId);
      v66 = v43;
      if ( v43 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandle,
          0);
        if ( OpenProcessToken(v43, 8u, &TokenHandle) )
        {
          ExitCode[0] = 0;
          if ( (int)AppModelPolicy_GetPolicy(TokenHandle, v44, ExitCode) < 0 || ExitCode[0] != 196609 )
            v78 = 0;
        }
      }
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v66);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    else
    {
      v78 = 0;
    }
  }
  v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 88LL))(v62);
  if ( v45 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v45,
      dwCreationFlagsa);
  CallerInformation::CallerInformation((CallerInformation *)v81, (const struct CallerInformation *)&v78);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v72)[1].Reserved.Reserved1;
  v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v84, &v73);
  v74 = *(_OWORD *)v74;
  v48 = ActivateAppParams::Initialize(v13, v70, v63, v47[1].Reserved.Reserved1);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x725,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v48,
      (int)Reserved1);
  ThreadId = 0;
  v49 = (char *)CreateThread(0, 0, ActivateApp, v13, 0, &ThreadId);
  v70 = v49;
  if ( (unsigned __int64)(v49 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x729,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      v50);
  v69 = 0;
  if ( (a8 & 4) == 0 )
  {
    v51 = WaitForSingleObject(v49, 0xFFFFFFFF);
    ExitCode[0] = v51;
    if ( v51 == -1 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x730,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        v52);
    if ( v51 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x731,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80004005LL,
        dwCreationFlagsb);
    if ( !GetExitCodeThread(v49, ExitCode) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x733,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        v53);
    if ( (ExitCode[0] & 0x80000000) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x734,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)ExitCode[0],
        dwCreationFlagsb);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v70);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  WindowsDeleteString(v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  return std::unique_ptr<ActivateAppParams>::~unique_ptr<ActivateAppParams>(&v69);
}

```

## disassembly

```asm
0x1800891c8  push    rbp
0x1800891ca  push    rbx
0x1800891cb  push    rsi
0x1800891cc  push    rdi
0x1800891cd  push    r12
0x1800891cf  push    r13
0x1800891d1  push    r14
0x1800891d3  push    r15
0x1800891d5  lea     rbp, [rsp-0B8h]
0x1800891dd  sub     rsp, 1B8h
0x1800891e4  mov     rax, cs:__security_cookie
0x1800891eb  xor     rax, rsp
0x1800891ee  mov     [rbp+0F0h+var_48], rax
0x1800891f5  mov     [rbp+0F0h+var_F8], r9
0x1800891f9  mov     [rbp+0F0h+var_F0], r8
0x1800891fd  mov     qword ptr [rbp+0F0h+var_110], rdx
0x180089201  mov     r13, rcx
0x180089204  mov     r12, [rbp+0F0h+arg_20]
0x18008920b  mov     [rbp+0F0h+var_118], r12
0x18008920f  mov     rsi, [rbp+0F0h+arg_28]
0x180089216  mov     [rbp+0F0h+var_150], rsi
0x18008921a  mov     rdi, [rbp+0F0h+arg_30]
0x180089221  mov     [rbp+0F0h+var_128], rdi
0x180089225  mov     [rbp+0F0h+var_120], rdi
0x180089229  mov     rax, [rbp+0F0h+arg_40]
0x180089230  mov     [rbp+0F0h+var_130], rax
0x180089234  mov     rax, [rbp+0F0h+arg_48]
0x18008923b  mov     [rbp+0F0h+var_100], rax
0x18008923f  mov     ecx, 60h ; '`'; Size
0x180089244  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180089249  mov     r14, rax
0x18008924c  mov     [rbp+0F0h+var_138], rax
0x180089250  xor     ebx, ebx
0x180089252  mov     [rax], rbx
0x180089255  mov     [rax+8], rbx
0x180089259  mov     [rax+10h], rbx
0x18008925d  mov     [rax+18h], rbx
0x180089261  mov     [rax+20h], rbx
0x180089265  mov     [rax+38h], rbx
0x180089269  mov     [rax+40h], rbx
0x18008926d  mov     [rax+48h], rbx
0x180089271  mov     [rax+50h], ebx
0x180089274  mov     [rax+58h], rbx
0x180089278  mov     [rbp+0F0h+var_138], rax
0x18008927c  mov     [rbp+0F0h+var_158], rbx
0x180089280  mov     [rbp+0F0h+var_160], rbx
0x180089284  mov     [rbp+0F0h+var_70], rbx
0x18008928b  lea     r9d, [rbx+27h]; unsigned int
0x18008928f  lea     r8d, [rbx+28h]; unsigned int
0x180089293  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18008929a  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x18008929e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800892a3  nop
0x1800892a4  lea     rdx, [rbp+0F0h+var_160]
0x1800892a8  mov     rcx, [rbp+0F0h+var_70]
0x1800892af  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x1800892b4  mov     rcx, [rbp+0F8h]; this
0x1800892bb  test    eax, eax
0x1800892bd  js      loc_180089987
0x1800892c3  mov     r15d, dword ptr [rbp+0F0h+arg_38]
0x1800892ca  bt      r15d, 0Ah
0x1800892cf  jnb     loc_1800894C6
0x1800892d5  mov     [rbp+0F0h+var_168], rbx
0x1800892d9  lea     rcx, [rbp+0F0h+hstringHeader]; string
0x1800892dd  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x1800892e2  lea     rdx, [rbp+0F0h+var_168]
0x1800892e6  mov     rcx, [rax]
0x1800892e9  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1800892ee  mov     rcx, [rbp+0F8h]; this
0x1800892f5  test    eax, eax
0x1800892f7  js      loc_18008999C
0x1800892fd  mov     qword ptr [rsp+1F0h+ExitCode], rbx
0x180089302  mov     [rbp+0F0h+var_70], rbx
0x180089309  lea     r9d, [rbx+27h]; unsigned int
0x18008930d  lea     r8d, [rbx+28h]; unsigned int
0x180089311  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x180089318  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x18008931c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180089321  nop
0x180089322  lea     rdx, [rsp+1F0h+ExitCode]
0x180089327  mov     rcx, [rbp+0F0h+var_70]
0x18008932e  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180089333  mov     rcx, [rbp+0F8h]; this
0x18008933a  test    eax, eax
0x18008933c  js      loc_1800899B1
0x180089342  mov     [rbp+0F0h+var_140], rbx
0x180089346  lea     rdx, [rbp+0F0h+var_140]
0x18008934a  lea     rcx, [rsp+1F0h+ExitCode]
0x18008934f  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180089354  mov     rcx, [rbp+0F8h]; this
0x18008935b  test    eax, eax
0x18008935d  js      loc_1800899C6
0x180089363  mov     [rsp+1F0h+var_190], bl
0x180089367  mov     [rsp+1F0h+var_180], rbx
0x18008936c  mov     rdi, [rbp+0F0h+var_168]
0x180089370  mov     rax, [rdi]
0x180089373  mov     rbx, [rax+88h]
0x18008937a  lea     rcx, [rsp+1F0h+var_180]
0x18008937f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089384  lea     r8, [rsp+1F0h+var_180]
0x180089389  mov     dl, 1
0x18008938b  mov     rcx, rdi
0x18008938e  mov     rax, rbx
0x180089391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089396  mov     rcx, [rbp+0F8h]; this
0x18008939d  test    eax, eax
0x18008939f  js      loc_1800899DB
0x1800893a5  mov     rsi, [rbp+0F0h+var_140]
0x1800893a9  mov     rax, [rsi]
0x1800893ac  mov     rdi, [rax+50h]
0x1800893b0  mov     rbx, [rsp+1F0h+var_180]
0x1800893b5  mov     [rbp+0F0h+var_70], 0
0x1800893c0  mov     r9d, 0Bh; unsigned int
0x1800893c6  lea     r8d, [r9+1]; unsigned int
0x1800893ca  lea     rdx, aIsmaximized; "IsMaximized"
0x1800893d1  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x1800893d5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800893da  nop
0x1800893db  lea     r9, [rsp+1F0h+var_190]
0x1800893e0  mov     r8, rbx
0x1800893e3  mov     rdx, [rbp+0F0h+var_70]
0x1800893ea  mov     rcx, rsi
0x1800893ed  mov     rax, rdi
0x1800893f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893f5  mov     rcx, [rbp+0F8h]; this
0x1800893fc  test    eax, eax
0x1800893fe  js      loc_1800899F0
0x180089404  mov     [rsp+1F0h+TokenHandle], 0
0x18008940d  lea     rdx, [rsp+1F0h+TokenHandle]
0x180089412  lea     rcx, [rbp+0F0h+var_160]
0x180089416  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18008941b  mov     rcx, [rbp+0F8h]; this
0x180089422  test    eax, eax
0x180089424  js      loc_180089A05
0x18008942a  mov     rsi, [rsp+1F0h+TokenHandle]
0x18008942f  mov     rax, [rsi]
0x180089432  mov     rdi, [rax+50h]
0x180089436  mov     rbx, qword ptr [rsp+1F0h+ExitCode]
0x18008943b  mov     [rbp+0F0h+var_70], 0
0x180089446  mov     r9d, 17h; unsigned int
0x18008944c  lea     r8d, [r9+1]; unsigned int
0x180089450  lea     rdx, aCustomapplaunc; "CustomAppLaunch_Context"
0x180089457  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x18008945b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180089460  nop
0x180089461  lea     r9, [rsp+1F0h+var_190]
0x180089466  mov     r8, rbx
0x180089469  mov     rdx, [rbp+0F0h+var_70]
0x180089470  mov     rcx, rsi
0x180089473  mov     rax, rdi
0x180089476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008947b  mov     rcx, [rbp+0F8h]; this
0x180089482  test    eax, eax
0x180089484  js      loc_180089A1A
0x18008948a  lea     rcx, [rsp+1F0h+TokenHandle]
0x18008948f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089494  nop
0x180089495  lea     rcx, [rsp+1F0h+var_180]
0x18008949a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008949f  nop
0x1800894a0  lea     rcx, [rbp+0F0h+var_140]
0x1800894a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800894a9  nop
0x1800894aa  lea     rcx, [rsp+1F0h+ExitCode]
0x1800894af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800894b4  nop
0x1800894b5  lea     rcx, [rbp+0F0h+var_168]
0x1800894b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800894be  mov     rdi, [rbp+0F0h+var_128]
0x1800894c2  mov     rsi, [rbp+0F0h+var_150]
0x1800894c6  mov     ecx, r15d
0x1800894c9  shr     ecx, 6
0x1800894cc  and     ecx, 1
0x1800894cf  mov     edx, ecx
0x1800894d1  or      edx, 2
0x1800894d4  test    r15b, 80h
0x1800894d8  cmovz   edx, ecx
0x1800894db  mov     ecx, edx
0x1800894dd  or      ecx, 4
0x1800894e0  bt      r15d, 8
0x1800894e5  cmovnb  ecx, edx
0x1800894e8  mov     ebx, ecx
0x1800894ea  or      ebx, 8
0x1800894ed  bt      r15d, 9
0x1800894f2  cmovnb  ebx, ecx
0x1800894f5  mov     rax, [rbp+0F0h+var_160]
0x1800894f9  mov     [rsp+1F0h+var_180], rax
0x1800894fe  lea     rcx, [rsp+1F0h+var_180]
0x180089503  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180089508  nop
0x180089509  mov     [rbp+0F0h+var_70], 0
0x180089514  mov     r9d, 28h ; '('; unsigned int
0x18008951a  lea     r8d, [r9+1]; unsigned int
0x18008951e  lea     rdx, aViewsizeprefer_3; "ViewSizePreferences.DesiredRemainingVie"...
0x180089525  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x180089529  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008952e  nop
0x18008952f  mov     r9d, ebx
0x180089532  mov     rdx, [rbp+0F0h+var_70]; HSTRING
0x180089539  lea     rcx, [rsp+1F0h+var_180]; this
0x18008953e  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x180089543  mov     rcx, [rbp+0F8h]; this
0x18008954a  test    eax, eax
0x18008954c  js      loc_180089A2F
0x180089552  lea     rdx, off_180123050; "ViewSizePreferences.SourceViewSizePrefe"...
0x180089559  lea     rcx, [rbp+0F0h+hstringHeader]
0x18008955d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180089562  nop
0x180089563  mov     r9d, ebx
0x180089566  mov     rdx, [rax+18h]; HSTRING
0x18008956a  lea     rcx, [rsp+1F0h+var_180]; this
0x18008956f  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x180089574  mov     rcx, [rbp+0F8h]; this
0x18008957b  test    eax, eax
0x18008957d  js      loc_180089A44
0x180089583  mov     ebx, [r13+0]
0x180089587  lea     rdx, off_180123048; "ViewSizePreferences.SourceWindow"
0x18008958e  lea     rcx, [rbp+0F0h+hstringHeader]
0x180089592  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180089597  nop
0x180089598  mov     r9d, ebx
0x18008959b  mov     rdx, [rax+18h]; HSTRING
0x18008959f  lea     rcx, [rsp+1F0h+var_180]; this
0x1800895a4  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x1800895a9  mov     rcx, [rbp+0F8h]; this
0x1800895b0  xor     ebx, ebx
0x1800895b2  test    eax, eax
0x1800895b4  js      loc_180089A59
0x1800895ba  lea     rcx, [rbp+0F0h+var_158]
0x1800895be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800895c3  lea     rdx, [rbp+0F0h+var_158]; struct Windows::Foundation::Collections::IPropertySet *
0x1800895c7  mov     rcx, [rbp+0F0h+var_160]; this
0x1800895cb  call    ?SerializePropertySet@LauncherMiscHelpers@@YAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAUIBuffer@Streams@Storage@5@@Z; LauncherMiscHelpers::SerializePropertySet(Windows::Foundation::Collections::IPropertySet *,Windows::Storage::Streams::IBuffer * *)
0x1800895d0  mov     rcx, [rbp+0F8h]; this
0x1800895d7  test    eax, eax
0x1800895d9  js      loc_180089A6E
0x1800895df  xor     ecx, ecx; string
0x1800895e1  call    cs:__imp_WindowsDeleteString
0x1800895e7  mov     [rbp+0F0h+var_168], rbx
0x1800895eb  mov     r9d, r15d
0x1800895ee  shr     r9d, 3
0x1800895f2  and     r9b, 1; bool
0x1800895f6  lea     rax, [rbp+0F0h+var_168]
0x1800895fa  mov     [rsp+1F0h+lpThreadId], rax; HSTRING *
0x1800895ff  mov     r8, rdi; unsigned __int16 *
0x180089602  mov     rdx, rsi; unsigned __int16 *
0x180089605  mov     rcx, r12; unsigned __int16 *
0x180089608  call    ?GetActivationInfo@@YAXPEBG00_NPEAPEAUHSTRING__@@2@Z; GetActivationInfo(ushort const *,ushort const *,ushort const *,bool,HSTRING__ * *,HSTRING__ * *)
0x18008960d  mov     r12d, r15d
0x180089610  shr     r12d, 4
0x180089614  and     r12b, 1
0x180089618  mov     [rbp+0F0h+var_170], rbx
0x18008961c  mov     [rbp+0F0h+var_70], rbx
0x180089623  lea     r9d, [rbx+4Bh]; unsigned int
0x180089627  lea     r8d, [rbx+4Ch]; unsigned int
0x18008962b  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Activation_Private_ApplicationActivationProperties@@3QBGB; "Windows.ApplicationModel.Activation.Pri"...
0x180089632  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x180089636  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008963b  nop
0x18008963c  lea     rdx, [rbp+0F0h+var_170]
0x180089640  mov     rcx, [rbp+0F0h+var_70]
0x180089647  call    ??$ActivateInstance@V?$ComPtr@UIApplicationActivationProperties@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationActivationProperties@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationProperties>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationProperties>>)
0x18008964c  mov     rcx, [rbp+0F8h]; this
0x180089653  test    eax, eax
0x180089655  js      loc_180089A83
0x18008965b  mov     rcx, [rbp+0F0h+var_170]
0x18008965f  mov     rax, [rcx]
0x180089662  mov     edx, [r13+8]
0x180089666  mov     rax, [rax+48h]
0x18008966a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008966f  mov     rcx, [rbp+0F8h]; this
0x180089676  test    eax, eax
0x180089678  js      loc_180089A98
0x18008967e  mov     rcx, [rbp+0F0h+var_170]
0x180089682  mov     rax, [rcx]
0x180089685  mov     rdx, [rbp+0F0h+var_158]
0x180089689  mov     rax, [rax+68h]
0x18008968d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089692  mov     rcx, [rbp+0F8h]; this
0x180089699  test    eax, eax
0x18008969b  js      loc_180089AAD
0x1800896a1  mov     [rsp+1F0h+ExitCode], 0FFFFFFFFh
0x1800896a9  xor     r8d, r8d
0x1800896ac  lea     rdx, [rsp+1F0h+ExitCode]
0x1800896b1  xor     ecx, ecx
0x1800896b3  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800896b9  cmp     [rsp+1F0h+ExitCode], 3
0x1800896be  jnz     short loc_1800896E1
0x1800896c0  mov     rcx, rdi
0x1800896c3  call    IsRuntimeBehaviorUniversal
0x1800896c8  test    al, al
0x1800896ca  jnz     short loc_1800896E1
0x1800896cc  mov     rcx, [rbp+0F0h+var_170]
0x1800896d0  mov     rax, [rcx]
0x1800896d3  mov     edx, 1000000h
0x1800896d8  mov     rax, [rax+38h]
0x1800896dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800896e1  mov     rdx, r13; struct CallerInformation *
0x1800896e4  lea     rcx, [rbp+0F0h+var_E8]; this
0x1800896e8  call    ??0CallerInformation@@QEAA@AEBV0@@Z; CallerInformation::CallerInformation(CallerInformation const &)
  ... truncated ...
```
