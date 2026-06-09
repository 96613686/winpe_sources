# Launcher::_LaunchFileInternalAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x180027dd0`
- end: `0x1800285c7`
- name: `??$_LaunchFileInternalAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@Launcher@@AEAAJPEAUIStorageFile@Storage@Windows@@PEAUILauncherOptions@System@3@_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@_N@Foundation@3@@Z`
- size: `2039`
- prototype: `__int64 __fastcall(__int64, int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 (__fastcall ***)(_QWORD, GUID *, HSTRING *), __int64, HSTRING string, _QWORD *)`
- caller_count: `1`
- callee_count: `29`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028854`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x1800210f8`
- `0x180027c60`
- `0x180027d80`
- `0x180027dd0`
- `0x180028b18`
- `0x180028b70`
- `0x18003c234`
- `0x180047254`
- `0x180047570`
- `0x1800477e4`
- `0x180047fc4`
- `0x1800596d8`
- `0x180061100`
- `0x1800618fc`
- `0x1800619b8`
- `0x180061a24`
- `0x180061b00`
- `0x180061b70`
- `0x18006e350`
- `0x18006f5c8`
- `0x18008a030`
- `0x180090b44`
- `0x18009386c`
- `0x1800993dc`
- `0x1800a1670`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002855c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002855c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027e2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027e2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800281e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800281e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028546`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180028572`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180028572`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Launcher::_LaunchFileInternalAsync<bool,Windows::Internal::CBasicResult<unsigned char,0>>(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 (__fastcall ***a3)(_QWORD, GUID *, HSTRING *),
        __int64 a4,
        HSTRING string,
        _QWORD *a6)
{
  const unsigned __int16 *StringRawBuffer; // rbx
  int (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  PCWSTR v13; // rax
  HSTRING *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 FallbackUri; // rax
  __int64 (__fastcall *v20)(_QWORD, GUID *, HSTRING *); // rbx
  int v21; // eax
  HSTRING v22; // rsi
  __int64 (__fastcall *v23)(HSTRING, HSTRING *); // rdi
  int v24; // eax
  HSTRING v25; // rdi
  __int64 (__fastcall *v26)(HSTRING, __int64 *); // rbx
  int v27; // eax
  __int64 OwnerWindowId; // rbx
  HSTRING *v29; // rdx
  int CallerAumidOrProcessName; // eax
  __int64 v31; // rdi
  int v32; // ebx
  HSTRING v33; // rbx
  __int64 v34; // rsi
  int v35; // eax
  HSTRING v36; // r14
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // r12d
  HRESULT v41; // eax
  int v42; // [rsp+20h] [rbp-578h]
  int v43; // [rsp+20h] [rbp-578h]
  int v44; // [rsp+70h] [rbp-528h] BYREF
  HSTRING v45; // [rsp+78h] [rbp-520h] BYREF
  HSTRING v46; // [rsp+80h] [rbp-518h] BYREF
  __int64 v47; // [rsp+88h] [rbp-510h] BYREF
  __int64 v48; // [rsp+90h] [rbp-508h] BYREF
  HSTRING v49; // [rsp+98h] [rbp-500h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-4F8h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-4F0h] BYREF
  int v52[2]; // [rsp+B0h] [rbp-4E8h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-4E0h] BYREF
  _BYTE v54[12]; // [rsp+C0h] [rbp-4D8h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-4C8h] BYREF
  HSTRING *v56; // [rsp+D8h] [rbp-4C0h] BYREF
  HSTRING v57; // [rsp+E0h] [rbp-4B8h] BYREF
  int (__fastcall ***v58)(_QWORD, _QWORD, _QWORD); // [rsp+E8h] [rbp-4B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-4A8h] BYREF
  HSTRING v60; // [rsp+108h] [rbp-490h] BYREF
  void **v61; // [rsp+110h] [rbp-488h] BYREF
  _BYTE v62[272]; // [rsp+118h] [rbp-480h] BYREF
  _BYTE v63[8]; // [rsp+228h] [rbp-370h] BYREF
  _BYTE v64[48]; // [rsp+230h] [rbp-368h] BYREF
  _BYTE v65[336]; // [rsp+260h] [rbp-338h] BYREF
  _BYTE v66[432]; // [rsp+3B0h] [rbp-1E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+0h]

  v57 = string;
  *(_QWORD *)v54 = 0;
  *a6 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v61);
  v61 = &LauncherClientProvider::LaunchFileAsync::`vftable';
  LauncherClientProvider::LaunchFileAsync::StartActivity(
    (LauncherClientProvider::LaunchFileAsync *)&v61,
    StringRawBuffer);
  v58 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
  if ( a2 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[1])(a2);
  v47 = 0;
  v45 = 0;
  v9 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  if ( v9(a2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v47) < 0 )
  {
    v60 = 0;
    v41 = WindowsCreateStringReference(L"file", 4u, &hstringHeader, &v60);
    if ( v41 < 0 )
    {
      RaiseException(v41, 1u, 0, 0);
      __debugbreak();
    }
    RoOriginateError(2147942487LL, v60);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x80070057LL,
      v42);
  }
  v10 = v47;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 96LL);
  WindowsDeleteString(v45);
  v45 = 0;
  v12 = v11(v10, &v45);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x697,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v12,
      v42);
  if ( (Microsoft_WindowsPhone_WindowsSystemLauncherEnableBits & 1) != 0 )
  {
    v13 = WindowsGetStringRawBuffer(v45, 0);
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWSPHONE_WindowsSystemLauncher_Context, "e", v13);
  }
  v48 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  GetLauncherService(&v51, 0, &v48);
  v44 = 0;
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v56);
  v14 = v56;
  if ( v56 )
  {
    v50 = 0;
    v53 = 0;
    if ( a3 )
    {
      FallbackUri = GetFallbackUri(v52, a3);
      Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(&v53, FallbackUri);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
      v46 = 0;
      v20 = **a3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v21 = v20(a3, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v46);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B2,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v21,
          v42);
      v22 = v46;
      v23 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v46 + 48LL);
      WindowsDeleteString(v14[1]);
      v14[1] = 0;
      v24 = v23(v22, v14 + 1);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B3,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v24,
          v42);
      v25 = v46;
      v26 = *(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)v46 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      v27 = v26(v25, &v50);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B6,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v27,
          v42);
      OwnerWindowId = (unsigned int)GetOwnerWindowId(a3);
      ValidateUIThreadRequirements(OwnerWindowId);
      v44 = OwnerWindowId;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    }
    WindowsDeleteString(0);
    v46 = 0;
    CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v46, v29);
    if ( CallerAumidOrProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6C3,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)CallerAumidOrProcessName,
        v42);
    CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(v52);
    v31 = *(_QWORD *)v52;
    if ( *(_QWORD *)v52 )
    {
      v49 = v45;
      v32 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)v52 + 8LL), &v49);
    }
    else
    {
      v32 = -2147024882;
    }
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C7,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v32,
        v42);
    CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v55);
    v33 = v46;
    v49 = v46;
    v34 = v55;
    v35 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(v55 + 8), &v49);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6CB,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v35,
        v42);
    CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v49);
    v36 = v49;
    v37 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v49 + 1, &v57);
    if ( v37 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6CE,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v37,
        v42);
    LauncherClientProvider::LaunchFileAsync::Split(&v61, v65);
    v38 = _lambda_4c3535c0fa3976dd819b46a4876c5029_::_lambda_4c3535c0fa3976dd819b46a4876c5029_(
            (unsigned int)v66,
            (unsigned int)&v51,
            (unsigned int)&v48,
            (unsigned int)&v44,
            (__int64)v52,
            (__int64)&v47,
            (__int64)&v56,
            (__int64)&v53,
            (__int64)&v50,
            (__int64)v54,
            (__int64)&v49,
            (__int64)&v55,
            (__int64)v65);
    *(_DWORD *)v54 = 3;
    *(_QWORD *)&v54[4] = 128;
    v39 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<unsigned char,0>,_lambda_4c3535c0fa3976dd819b46a4876c5029_,>(v38);
    v40 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler>(
            v54,
            a6,
            0,
            v39);
    _lambda_677a0aa250d01c8e687696f106069bec_::~_lambda_677a0aa250d01c8e687696f106069bec_((_lambda_677a0aa250d01c8e687696f106069bec_ *)v66);
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v61,
      0);
    if ( v40 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x747,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v40,
        v43);
    LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync((LauncherClientProvider::LaunchFileAsync *)v65);
    if ( v36 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    WindowsDeleteString(v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    if ( v14 )
      (*((void (__fastcall **)(HSTRING *))*v14 + 2))(v14);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    WindowsDeleteString(v45);
    v45 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync((LauncherClientProvider::LaunchFileAsync *)&v61);
    return (unsigned int)v40;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A8,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x8007000ELL,
      v42);
    v15 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    WindowsDeleteString(v45);
    v45 = 0;
    v17 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
    v61 = &LauncherClientProvider::LaunchFileAsync::`vftable';
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v61);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v64);
    wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v63);
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(v62);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180027dd0  mov     r11, rsp
0x180027dd3  mov     [r11+8], rbx
0x180027dd7  mov     [r11+10h], rsi
0x180027ddb  push    rdi
0x180027ddc  push    r12
0x180027dde  push    r13
0x180027de0  push    r14
0x180027de2  push    r15
0x180027de4  sub     rsp, 570h
0x180027deb  mov     rax, cs:__security_cookie
0x180027df2  xor     rax, rsp
0x180027df5  mov     [rsp+598h+var_38], rax
0x180027dfd  mov     r14, r8
0x180027e00  mov     rsi, rdx
0x180027e03  mov     rcx, [rsp+598h+string]; string
0x180027e0b  mov     [r11-4B8h], rcx
0x180027e12  mov     r12, [rsp+598h+arg_28]
0x180027e1a  xor     r13d, r13d
0x180027e1d  mov     [r11-4D8h], r13
0x180027e24  mov     [r12], r13
0x180027e28  xor     edx, edx; length
0x180027e2a  call    cs:__imp_WindowsGetStringRawBuffer
0x180027e30  mov     rbx, rax
0x180027e33  lea     rdx, aLaunchfileasyn; "LaunchFileAsync"
0x180027e3a  lea     rcx, [rsp+598h+var_488]; struct wil::details::IFailureCallback *
0x180027e42  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180027e47  lea     rax, ??_7LaunchFileAsync@LauncherClientProvider@@6B@; const LauncherClientProvider::LaunchFileAsync::`vftable'
0x180027e4e  mov     [rsp+598h+var_488], rax
0x180027e56  mov     rdx, rbx; unsigned __int16 *
0x180027e59  lea     rcx, [rsp+598h+var_488]; this
0x180027e61  call    ?StartActivity@LaunchFileAsync@LauncherClientProvider@@QEAAXPEBG@Z; LauncherClientProvider::LaunchFileAsync::StartActivity(ushort const *)
0x180027e66  nop
0x180027e67  mov     [rsp+598h+var_4B0], rsi
0x180027e6f  test    rsi, rsi
0x180027e72  jz      short loc_180027E84
0x180027e74  mov     rax, [rsi]
0x180027e77  mov     rcx, rsi
0x180027e7a  mov     rax, [rax+8]
0x180027e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e83  nop
0x180027e84  mov     [rsp+598h+var_510], r13
0x180027e8c  mov     [rsp+598h+var_520], r13
0x180027e91  mov     rax, [rsi]
0x180027e94  mov     rbx, [rax]
0x180027e97  lea     rcx, [rsp+598h+var_510]
0x180027e9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027ea4  lea     r8, [rsp+598h+var_510]
0x180027eac  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180027eb3  mov     rcx, rsi
0x180027eb6  mov     rax, rbx
0x180027eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ebe  nop
0x180027ebf  test    eax, eax
0x180027ec1  js      loc_180028522
0x180027ec7  mov     rdi, [rsp+598h+var_510]
0x180027ecf  mov     rax, [rdi]
0x180027ed2  mov     rbx, [rax+60h]
0x180027ed6  mov     rcx, [rsp+598h+var_520]; string
0x180027edb  call    cs:__imp_WindowsDeleteString
0x180027ee1  mov     [rsp+598h+var_520], r13
0x180027ee6  lea     rdx, [rsp+598h+var_520]
0x180027eeb  mov     rcx, rdi
0x180027eee  mov     rax, rbx
0x180027ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ef6  mov     rcx, [rsp+598h]; this
0x180027efe  test    eax, eax
0x180027f00  jns     short loc_180027F16
0x180027f02  mov     r9d, eax; char *
0x180027f05  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180027f0c  mov     edx, 697h; void *
0x180027f11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027f16  test    cs:Microsoft_WindowsPhone_WindowsSystemLauncherEnableBits, 1
0x180027f1d  jz      short loc_180027F42
0x180027f1f  xor     edx, edx; length
0x180027f21  mov     rcx, [rsp+598h+var_520]; string
0x180027f26  call    cs:__imp_WindowsGetStringRawBuffer
0x180027f2c  mov     r8, rax
0x180027f2f  lea     rdx, LaunchFile; "e"
0x180027f36  lea     rcx, MICROSOFT_WINDOWSPHONE_WindowsSystemLauncher_Context
0x180027f3d  call    McTemplateU0z_EventWriteTransfer
0x180027f42  mov     [rsp+598h+var_508], r13
0x180027f4a  lea     rcx, [rsp+598h+var_508]
0x180027f52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027f57  lea     r8, [rsp+598h+var_508]
0x180027f5f  xor     edx, edx
0x180027f61  lea     rcx, [rsp+598h+var_4F0]
0x180027f69  call    ?GetLauncherService@@YA?AV?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@_KPEAPEAUIAsUserPartialTrustComponentHost@Launch@Internal@System@Windows@@@Z; GetLauncherService(unsigned __int64,Windows::System::Internal::Launch::IAsUserPartialTrustComponentHost * *)
0x180027f6e  nop
0x180027f6f  mov     [rsp+598h+var_528], r13d
0x180027f74  lea     rcx, [rsp+598h+var_4C0]
0x180027f7c  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180027f81  nop
0x180027f82  mov     r15, [rsp+598h+var_4C0]
0x180027f8a  test    r15, r15
0x180027f8d  jnz     loc_180028085
0x180027f93  mov     rcx, [rsp+598h]; this
0x180027f9b  mov     ebx, 8007000Eh
0x180027fa0  mov     r9d, ebx; char *
0x180027fa3  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180027faa  mov     edx, 6A8h; void *
0x180027faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027fb4  nop
0x180027fb5  mov     rcx, [rsp+598h+var_4F0]
0x180027fbd  test    rcx, rcx
0x180027fc0  jz      short loc_180027FD7
0x180027fc2  mov     [rsp+598h+var_4F0], r13
0x180027fca  mov     rax, [rcx]
0x180027fcd  mov     rax, [rax+10h]
0x180027fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fd6  nop
0x180027fd7  mov     rcx, [rsp+598h+var_508]
0x180027fdf  test    rcx, rcx
0x180027fe2  jz      short loc_180027FF9
0x180027fe4  mov     [rsp+598h+var_508], r13
0x180027fec  mov     rax, [rcx]
0x180027fef  mov     rax, [rax+10h]
0x180027ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff8  nop
0x180027ff9  mov     rcx, [rsp+598h+var_520]; string
0x180027ffe  call    cs:__imp_WindowsDeleteString
0x180028004  mov     [rsp+598h+var_520], r13
0x180028009  mov     rcx, [rsp+598h+var_510]
0x180028011  test    rcx, rcx
0x180028014  jz      short loc_18002802B
0x180028016  mov     [rsp+598h+var_510], r13
0x18002801e  mov     rax, [rcx]
0x180028021  mov     rax, [rax+10h]
0x180028025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002802a  nop
0x18002802b  mov     rax, [rsi]
0x18002802e  mov     rcx, rsi
0x180028031  mov     rax, [rax+10h]
0x180028035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002803a  nop
0x18002803b  lea     rax, ??_7LaunchFileAsync@LauncherClientProvider@@6B@; const LauncherClientProvider::LaunchFileAsync::`vftable'
0x180028042  mov     [rsp+598h+var_488], rax
0x18002804a  lea     rcx, [rsp+598h+var_488]
0x180028052  call    ?Destroy@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180028057  lea     rcx, [rsp+598h+var_368]; this
0x18002805f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180028064  lea     rcx, [rsp+598h+var_370]
0x18002806c  call    ?reset@?$shared_object@V?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180028071  lea     rcx, [rsp+598h+var_480]
0x180028079  call    ??1?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002807e  mov     eax, ebx
0x180028080  jmp     loc_180028599
0x180028085  mov     [rsp+598h+var_4F8], r13
0x18002808d  mov     [rsp+598h+var_4E0], r13
0x180028095  test    r14, r14
0x180028098  jz      loc_1800281DF
0x18002809e  mov     rdx, r14
0x1800280a1  lea     rcx, [rsp+598h+var_4E8]
0x1800280a9  call    ?GetFallbackUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherOptions@System@Windows@@@Z; GetFallbackUri(Windows::System::ILauncherOptions *)
0x1800280ae  mov     rdx, rax
0x1800280b1  lea     rcx, [rsp+598h+var_4E0]
0x1800280b9  call    ??4?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService> &&)
0x1800280be  lea     rcx, [rsp+598h+var_4E8]
0x1800280c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800280cb  mov     [rsp+598h+var_518], r13
0x1800280d3  mov     rax, [r14]
0x1800280d6  mov     rbx, [rax]
0x1800280d9  lea     rcx, [rsp+598h+var_518]
0x1800280e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800280e6  lea     r8, [rsp+598h+var_518]
0x1800280ee  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x1800280f5  mov     rcx, r14
0x1800280f8  mov     rax, rbx
0x1800280fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028100  mov     rcx, [rsp+598h]; this
0x180028108  test    eax, eax
0x18002810a  jns     short loc_180028120
0x18002810c  mov     r9d, eax; char *
0x18002810f  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180028116  mov     edx, 6B2h; void *
0x18002811b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028120  mov     rsi, [rsp+598h+var_518]
0x180028128  mov     rax, [rsi]
0x18002812b  mov     rdi, [rax+30h]
0x18002812f  lea     rbx, [r15+8]
0x180028133  mov     rcx, [rbx]; string
0x180028136  call    cs:__imp_WindowsDeleteString
0x18002813c  mov     [rbx], r13
0x18002813f  mov     rdx, rbx
0x180028142  mov     rcx, rsi
0x180028145  mov     rax, rdi
0x180028148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002814d  mov     rcx, [rsp+598h]; this
0x180028155  test    eax, eax
0x180028157  jns     short loc_18002816D
0x180028159  mov     r9d, eax; char *
0x18002815c  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180028163  mov     edx, 6B3h; void *
0x180028168  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002816d  mov     rdi, [rsp+598h+var_518]
0x180028175  mov     rax, [rdi]
0x180028178  mov     rbx, [rax+40h]
0x18002817c  lea     rcx, [rsp+598h+var_4F8]
0x180028184  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028189  lea     rdx, [rsp+598h+var_4F8]
0x180028191  mov     rcx, rdi
0x180028194  mov     rax, rbx
0x180028197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002819c  mov     rcx, [rsp+598h]; this
0x1800281a4  test    eax, eax
0x1800281a6  jns     short loc_1800281BC
0x1800281a8  mov     r9d, eax; char *
0x1800281ab  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800281b2  mov     edx, 6B6h; void *
0x1800281b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800281bc  mov     rcx, r14
0x1800281bf  call    GetOwnerWindowId
0x1800281c4  mov     ebx, eax
0x1800281c6  mov     ecx, eax
0x1800281c8  call    ?ValidateUIThreadRequirements@@YAXUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; ValidateUIThreadRequirements(Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x1800281cd  mov     [rsp+598h+var_528], ebx
0x1800281d1  lea     rcx, [rsp+598h+var_518]
0x1800281d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800281de  nop
0x1800281df  xor     ecx, ecx; string
0x1800281e1  call    cs:__imp_WindowsDeleteString
0x1800281e7  mov     [rsp+598h+var_518], r13
0x1800281ef  lea     rcx, [rsp+598h+var_518]; this
0x1800281f7  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x1800281fc  mov     rcx, [rsp+598h]; this
0x180028204  test    eax, eax
0x180028206  jns     short loc_18002821C
0x180028208  mov     r9d, eax; char *
0x18002820b  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180028212  mov     edx, 6C3h; void *
0x180028217  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002821c  lea     rcx, [rsp+598h+var_4E8]
0x180028224  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180028229  nop
0x18002822a  mov     rdi, qword ptr [rsp+598h+var_4E8]
0x180028232  test    rdi, rdi
0x180028235  jz      short loc_180028259
0x180028237  mov     rax, [rsp+598h+var_520]
0x18002823c  mov     [rsp+598h+var_500], rax
0x180028244  lea     rcx, [rdi+8]; newString
0x180028248  lea     rdx, [rsp+598h+var_500]; HSTRING *
0x180028250  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180028255  mov     ebx, eax
0x180028257  jmp     short loc_18002825E
0x180028259  mov     ebx, 8007000Eh
0x18002825e  mov     rcx, [rsp+598h]; this
0x180028266  test    ebx, ebx
0x180028268  jns     short loc_18002827E
0x18002826a  mov     r9d, ebx; char *
0x18002826d  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180028274  mov     edx, 6C7h; void *
0x180028279  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002827e  lea     rcx, [rsp+598h+var_4C8]
0x180028286  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x18002828b  nop
0x18002828c  mov     rbx, [rsp+598h+var_518]
0x180028294  mov     [rsp+598h+var_500], rbx
0x18002829c  mov     rsi, [rsp+598h+var_4C8]
0x1800282a4  lea     rcx, [rsi+8]; newString
0x1800282a8  lea     rdx, [rsp+598h+var_500]; HSTRING *
0x1800282b0  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800282b5  mov     rcx, [rsp+598h]; this
0x1800282bd  test    eax, eax
0x1800282bf  jns     short loc_1800282D5
0x1800282c1  mov     r9d, eax; char *
0x1800282c4  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800282cb  mov     edx, 6CBh; void *
0x1800282d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800282d5  lea     rcx, [rsp+598h+var_500]
0x1800282dd  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x1800282e2  nop
0x1800282e3  mov     r14, [rsp+598h+var_500]
0x1800282eb  lea     rcx, [r14+8]; newString
0x1800282ef  lea     rdx, [rsp+598h+var_4B8]; HSTRING *
0x1800282f7  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800282fc  mov     rcx, [rsp+598h]; this
0x180028304  test    eax, eax
0x180028306  jns     short loc_18002831C
0x180028308  mov     r9d, eax; char *
0x18002830b  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180028312  mov     edx, 6CEh; void *
0x180028317  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002831c  lea     rdx, [rsp+598h+var_338]
0x180028324  lea     rcx, [rsp+598h+var_488]
0x18002832c  call    ?Split@LaunchFileAsync@LauncherClientProvider@@QEAA?AV12@XZ; LauncherClientProvider::LaunchFileAsync::Split(void)
0x180028331  nop
0x180028332  lea     rax, [rsp+598h+var_338]
0x18002833a  mov     [rsp+598h+var_538], rax
0x18002833f  lea     rax, [rsp+598h+var_4C8]
0x180028347  mov     [rsp+598h+var_540], rax
0x18002834c  lea     rax, [rsp+598h+var_500]
0x180028354  mov     [rsp+598h+var_548], rax
0x180028359  lea     rax, [rsp+598h+var_4D8]
0x180028361  mov     [rsp+598h+var_550], rax
0x180028366  lea     rax, [rsp+598h+var_4F8]
0x18002836e  mov     [rsp+598h+var_558], rax
0x180028373  lea     rax, [rsp+598h+var_4E0]
0x18002837b  mov     [rsp+598h+var_560], rax
0x180028380  lea     rax, [rsp+598h+var_4C0]
0x180028388  mov     [rsp+598h+var_568], rax
0x18002838d  lea     rax, [rsp+598h+var_510]
  ... truncated ...
```
