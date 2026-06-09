# Launcher::_LaunchFileInternalAsync<Windows::System::LaunchFileStatus,Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4>>(Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::System::LaunchFileStatus> * *)

- ea: `0x1800611c4`
- end: `0x1800618f3`
- name: `??$_LaunchFileInternalAsync@W4LaunchFileStatus@System@Windows@@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@3@@Launcher@@AEAAJPEAUIStorageFile@Storage@Windows@@PEAUILauncherOptions@System@3@_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@W4LaunchFileStatus@System@Windows@@@Foundation@3@@Z`
- size: `1839`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, HSTRING *), __int64, HSTRING string, _QWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180060f1c`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x180027a10`
- `0x180027c60`
- `0x180027d80`
- `0x18002cec0`
- `0x18003c234`
- `0x180047254`
- `0x180047570`
- `0x1800477e4`
- `0x1800596d8`
- `0x180061100`
- `0x1800611c4`
- `0x1800618fc`
- `0x180061b00`
- `0x180061b70`
- `0x180061c90`
- `0x180068a30`
- `0x18006e350`
- `0x18006f580`
- `0x18008a030`
- `0x180090a78`
- `0x18009386c`
- `0x1800993dc`
- `0x1800a1670`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800612e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800612e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006147d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800617d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006147d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800617d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061830`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006189e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006189e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Launcher::_LaunchFileInternalAsync<enum Windows::System::LaunchFileStatus,Windows::Internal::CBasicResult<enum Windows::System::LaunchFileStatus,4>>(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, HSTRING *),
        __int64 a4,
        HSTRING string,
        _QWORD *a6)
{
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING *v13; // r15
  __int64 FallbackUri; // rax
  __int64 (__fastcall *v16)(_QWORD, GUID *, HSTRING *); // rbx
  int v17; // eax
  HSTRING v18; // rsi
  __int64 (__fastcall *v19)(HSTRING, HSTRING *); // rdi
  int v20; // eax
  HSTRING v21; // rdi
  __int64 (__fastcall *v22)(HSTRING, __int64 *); // rbx
  int v23; // eax
  unsigned int OwnerWindowId; // ebx
  HSTRING *v25; // rdx
  int CallerAumidOrProcessName; // eax
  __int64 v27; // rdi
  int v28; // ebx
  HSTRING v29; // rbx
  __int64 v30; // rsi
  int v31; // eax
  HSTRING v32; // r14
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // r12d
  int v37; // [rsp+20h] [rbp-578h]
  int v38; // [rsp+20h] [rbp-578h]
  unsigned int v39; // [rsp+70h] [rbp-528h] BYREF
  HSTRING v40; // [rsp+78h] [rbp-520h] BYREF
  HSTRING v41; // [rsp+80h] [rbp-518h] BYREF
  HSTRING v42; // [rsp+88h] [rbp-510h] BYREF
  int v43[2]; // [rsp+90h] [rbp-508h] BYREF
  __int64 v44; // [rsp+98h] [rbp-500h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-4F8h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-4F0h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-4E8h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-4E0h] BYREF
  _BYTE v49[8]; // [rsp+C0h] [rbp-4D8h] BYREF
  _BYTE v50[12]; // [rsp+C8h] [rbp-4D0h] BYREF
  __int64 v51; // [rsp+D8h] [rbp-4C0h] BYREF
  HSTRING *v52; // [rsp+E0h] [rbp-4B8h] BYREF
  HSTRING v53; // [rsp+E8h] [rbp-4B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-4A8h] BYREF
  __int64 v55; // [rsp+108h] [rbp-490h]
  _BYTE v56[336]; // [rsp+110h] [rbp-488h] BYREF
  _BYTE v57[336]; // [rsp+260h] [rbp-338h] BYREF
  _BYTE v58[432]; // [rsp+3B0h] [rbp-1E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+0h]

  *(_QWORD *)v50 = a4;
  v53 = string;
  *a6 = 0;
  *(_QWORD *)v43 = WindowsGetStringRawBuffer(string, 0);
  LauncherClientProvider::LaunchFileAsync::Start<unsigned short const *>((LauncherClientProvider::LaunchFileAsync *)v56);
  v47 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v47);
  v45 = 0;
  v40 = 0;
  if ( (int)Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(&v47, &v45) < 0 )
  {
    v55 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"file", 5u, 4u);
    RoOriginateError(2147942487LL, v55);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x80070057LL,
      v37);
  }
  v9 = v45;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 96LL);
  WindowsDeleteString(v40);
  v40 = 0;
  v11 = v10(v9, &v40);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x697,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v11,
      v37);
  if ( (Microsoft_WindowsPhone_WindowsSystemLauncherEnableBits & 1) != 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v40, 0);
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWSPHONE_WindowsSystemLauncher_Context, "e", StringRawBuffer);
  }
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  GetLauncherService(v49, a4, &v44);
  v39 = 0;
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v52);
  v13 = v52;
  if ( v52 )
  {
    v46 = 0;
    v48 = 0;
    if ( a3 )
    {
      FallbackUri = GetFallbackUri(v43, a3);
      Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(&v48, FallbackUri);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
      v41 = 0;
      v16 = **a3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v17 = v16(a3, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v41);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B2,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v17,
          v37);
      v18 = v41;
      v19 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v41 + 48LL);
      WindowsDeleteString(v13[1]);
      v13[1] = 0;
      v20 = v19(v18, v13 + 1);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B3,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v20,
          v37);
      v21 = v41;
      v22 = *(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)v41 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v23 = v22(v21, &v46);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B6,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v23,
          v37);
      OwnerWindowId = GetOwnerWindowId(a3);
      ValidateUIThreadRequirements(OwnerWindowId);
      v39 = OwnerWindowId;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    }
    WindowsDeleteString(0);
    v41 = 0;
    CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v41, v25);
    if ( CallerAumidOrProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6C3,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)CallerAumidOrProcessName,
        v37);
    CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(v43);
    v27 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      v42 = v40;
      v28 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)v43 + 8LL), &v42);
    }
    else
    {
      v28 = -2147024882;
    }
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C7,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v28,
        v37);
    CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v51);
    v29 = v41;
    v42 = v41;
    v30 = v51;
    v31 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(v51 + 8), &v42);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6CB,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v31,
        v37);
    CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v42);
    v32 = v42;
    v33 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v42 + 1, &v53);
    if ( v33 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6CE,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v33,
        v37);
    LauncherClientProvider::LaunchFileAsync::Split(v56, v57);
    v34 = _lambda_4c3535c0fa3976dd819b46a4876c5029_::_lambda_4c3535c0fa3976dd819b46a4876c5029_(
            (unsigned int)v58,
            (unsigned int)v49,
            (unsigned int)&v44,
            (unsigned int)&v39,
            (__int64)v43,
            (__int64)&v45,
            (__int64)&v52,
            (__int64)&v48,
            (__int64)&v46,
            (__int64)v50,
            (__int64)&v42,
            (__int64)&v51,
            (__int64)v57);
    *(_DWORD *)v50 = 3;
    *(_QWORD *)&v50[4] = 128;
    v35 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<enum Windows::System::LaunchFileStatus,4>,_lambda_677a0aa250d01c8e687696f106069bec_,>(v34);
    v36 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<enum Windows::System::LaunchFileStatus,4>,enum Windows::System::LaunchFileStatus,Windows::Internal::ComTaskPoolHandler>(
            v50,
            a6,
            0,
            v35);
    _lambda_677a0aa250d01c8e687696f106069bec_::~_lambda_677a0aa250d01c8e687696f106069bec_((_lambda_677a0aa250d01c8e687696f106069bec_ *)v58);
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v56,
      0);
    if ( v36 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x747,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v36,
        v38);
    LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync((LauncherClientProvider::LaunchFileAsync *)v57);
    if ( v32 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    WindowsDeleteString(v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    if ( v13 )
      (*((void (__fastcall **)(HSTRING *))*v13 + 2))(v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    WindowsDeleteString(v40);
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync((LauncherClientProvider::LaunchFileAsync *)v56);
    return (unsigned int)v36;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A8,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x8007000ELL,
      v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    WindowsDeleteString(v40);
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync((LauncherClientProvider::LaunchFileAsync *)v56);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800611c4  mov     r11, rsp
0x1800611c7  mov     [r11+8], rbx
0x1800611cb  mov     [r11+10h], rsi
0x1800611cf  push    rdi
0x1800611d0  push    r12
0x1800611d2  push    r13
0x1800611d4  push    r14
0x1800611d6  push    r15
0x1800611d8  sub     rsp, 570h
0x1800611df  mov     rax, cs:__security_cookie
0x1800611e6  xor     rax, rsp
0x1800611e9  mov     [rsp+598h+var_38], rax
0x1800611f1  mov     rsi, r9
0x1800611f4  mov     r14, r8
0x1800611f7  mov     rbx, rdx
0x1800611fa  mov     [r11-4D0h], r9
0x180061201  mov     rcx, [rsp+598h+string]; string
0x180061209  mov     [r11-4B0h], rcx
0x180061210  mov     r12, [rsp+598h+arg_28]
0x180061218  xor     r13d, r13d
0x18006121b  mov     [r12], r13
0x18006121f  xor     edx, edx; length
0x180061221  call    cs:__imp_WindowsGetStringRawBuffer
0x180061227  mov     qword ptr [rsp+598h+var_508], rax
0x18006122f  lea     rdx, [rsp+598h+var_508]
0x180061237  lea     rcx, [rsp+598h+var_488]; this
0x18006123f  call    ??$Start@PEBG@LaunchFileAsync@LauncherClientProvider@@SA?AV01@$$QEAPEBG@Z; LauncherClientProvider::LaunchFileAsync::Start<ushort const *>(ushort const * &&)
0x180061244  nop
0x180061245  mov     [rsp+598h+var_4E8], rbx
0x18006124d  lea     rcx, [rsp+598h+var_4E8]
0x180061255  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006125a  nop
0x18006125b  mov     [rsp+598h+var_4F8], r13
0x180061263  mov     [rsp+598h+var_520], r13
0x180061268  lea     rdx, [rsp+598h+var_4F8]
0x180061270  lea     rcx, [rsp+598h+var_4E8]
0x180061278  call    ??$As@UIStorageItem@Storage@Windows@@@?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>>)
0x18006127d  test    eax, eax
0x18006127f  js      loc_180061869
0x180061285  mov     rdi, [rsp+598h+var_4F8]
0x18006128d  mov     rax, [rdi]
0x180061290  mov     rbx, [rax+60h]
0x180061294  mov     rcx, [rsp+598h+var_520]; string
0x180061299  call    cs:__imp_WindowsDeleteString
0x18006129f  mov     [rsp+598h+var_520], r13
0x1800612a4  lea     rdx, [rsp+598h+var_520]
0x1800612a9  mov     rcx, rdi
0x1800612ac  mov     rax, rbx
0x1800612af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612b4  mov     rcx, [rsp+598h]; this
0x1800612bc  test    eax, eax
0x1800612be  jns     short loc_1800612D4
0x1800612c0  mov     r9d, eax; char *
0x1800612c3  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800612ca  mov     edx, 697h; void *
0x1800612cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800612d4  test    cs:Microsoft_WindowsPhone_WindowsSystemLauncherEnableBits, 1
0x1800612db  jz      short loc_180061300
0x1800612dd  xor     edx, edx; length
0x1800612df  mov     rcx, [rsp+598h+var_520]; string
0x1800612e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800612ea  mov     r8, rax
0x1800612ed  lea     rdx, LaunchFile; "e"
0x1800612f4  lea     rcx, MICROSOFT_WINDOWSPHONE_WindowsSystemLauncher_Context
0x1800612fb  call    McTemplateU0z_EventWriteTransfer
0x180061300  mov     [rsp+598h+var_500], r13
0x180061308  lea     rcx, [rsp+598h+var_500]
0x180061310  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061315  lea     r8, [rsp+598h+var_500]
0x18006131d  mov     rdx, rsi
0x180061320  lea     rcx, [rsp+598h+var_4D8]
0x180061328  call    ?GetLauncherService@@YA?AV?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@_KPEAPEAUIAsUserPartialTrustComponentHost@Launch@Internal@System@Windows@@@Z; GetLauncherService(unsigned __int64,Windows::System::Internal::Launch::IAsUserPartialTrustComponentHost * *)
0x18006132d  nop
0x18006132e  mov     [rsp+598h+var_528], r13d
0x180061333  lea     rcx, [rsp+598h+var_4B8]
0x18006133b  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180061340  nop
0x180061341  mov     r15, [rsp+598h+var_4B8]
0x180061349  test    r15, r15
0x18006134c  jnz     short loc_1800613CC
0x18006134e  mov     rcx, [rsp+598h]; this
0x180061356  mov     ebx, 8007000Eh
0x18006135b  mov     r9d, ebx; char *
0x18006135e  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180061365  mov     edx, 6A8h; void *
0x18006136a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006136f  nop
0x180061370  lea     rcx, [rsp+598h+var_4D8]
0x180061378  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006137d  nop
0x18006137e  lea     rcx, [rsp+598h+var_500]
0x180061386  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006138b  nop
0x18006138c  mov     rcx, [rsp+598h+var_520]; string
0x180061391  call    cs:__imp_WindowsDeleteString
0x180061397  mov     [rsp+598h+var_520], r13
0x18006139c  lea     rcx, [rsp+598h+var_4F8]
0x1800613a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800613a9  nop
0x1800613aa  lea     rcx, [rsp+598h+var_4E8]
0x1800613b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800613b7  nop
0x1800613b8  lea     rcx, [rsp+598h+var_488]; this
0x1800613c0  call    ??1LaunchFileAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync(void)
0x1800613c5  mov     eax, ebx
0x1800613c7  jmp     loc_1800618C5
0x1800613cc  mov     [rsp+598h+var_4F0], r13
0x1800613d4  mov     [rsp+598h+var_4E0], r13
0x1800613dc  test    r14, r14
0x1800613df  jz      loc_180061526
0x1800613e5  mov     rdx, r14
0x1800613e8  lea     rcx, [rsp+598h+var_508]
0x1800613f0  call    ?GetFallbackUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherOptions@System@Windows@@@Z; GetFallbackUri(Windows::System::ILauncherOptions *)
0x1800613f5  mov     rdx, rax
0x1800613f8  lea     rcx, [rsp+598h+var_4E0]
0x180061400  call    ??4?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService> &&)
0x180061405  lea     rcx, [rsp+598h+var_508]
0x18006140d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061412  mov     [rsp+598h+var_518], r13
0x18006141a  mov     rax, [r14]
0x18006141d  mov     rbx, [rax]
0x180061420  lea     rcx, [rsp+598h+var_518]
0x180061428  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006142d  lea     r8, [rsp+598h+var_518]
0x180061435  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x18006143c  mov     rcx, r14
0x18006143f  mov     rax, rbx
0x180061442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061447  mov     rcx, [rsp+598h]; this
0x18006144f  test    eax, eax
0x180061451  jns     short loc_180061467
0x180061453  mov     r9d, eax; char *
0x180061456  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x18006145d  mov     edx, 6B2h; void *
0x180061462  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061467  mov     rsi, [rsp+598h+var_518]
0x18006146f  mov     rax, [rsi]
0x180061472  mov     rdi, [rax+30h]
0x180061476  lea     rbx, [r15+8]
0x18006147a  mov     rcx, [rbx]; string
0x18006147d  call    cs:__imp_WindowsDeleteString
0x180061483  mov     [rbx], r13
0x180061486  mov     rdx, rbx
0x180061489  mov     rcx, rsi
0x18006148c  mov     rax, rdi
0x18006148f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061494  mov     rcx, [rsp+598h]; this
0x18006149c  test    eax, eax
0x18006149e  jns     short loc_1800614B4
0x1800614a0  mov     r9d, eax; char *
0x1800614a3  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800614aa  mov     edx, 6B3h; void *
0x1800614af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800614b4  mov     rdi, [rsp+598h+var_518]
0x1800614bc  mov     rax, [rdi]
0x1800614bf  mov     rbx, [rax+40h]
0x1800614c3  lea     rcx, [rsp+598h+var_4F0]
0x1800614cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800614d0  lea     rdx, [rsp+598h+var_4F0]
0x1800614d8  mov     rcx, rdi
0x1800614db  mov     rax, rbx
0x1800614de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800614e3  mov     rcx, [rsp+598h]; this
0x1800614eb  test    eax, eax
0x1800614ed  jns     short loc_180061503
0x1800614ef  mov     r9d, eax; char *
0x1800614f2  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800614f9  mov     edx, 6B6h; void *
0x1800614fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061503  mov     rcx, r14
0x180061506  call    GetOwnerWindowId
0x18006150b  mov     ebx, eax
0x18006150d  mov     ecx, eax
0x18006150f  call    ?ValidateUIThreadRequirements@@YAXUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; ValidateUIThreadRequirements(Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180061514  mov     [rsp+598h+var_528], ebx
0x180061518  lea     rcx, [rsp+598h+var_518]
0x180061520  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061525  nop
0x180061526  xor     ecx, ecx; string
0x180061528  call    cs:__imp_WindowsDeleteString
0x18006152e  mov     [rsp+598h+var_518], r13
0x180061536  lea     rcx, [rsp+598h+var_518]; this
0x18006153e  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x180061543  mov     rcx, [rsp+598h]; this
0x18006154b  test    eax, eax
0x18006154d  jns     short loc_180061563
0x18006154f  mov     r9d, eax; char *
0x180061552  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180061559  mov     edx, 6C3h; void *
0x18006155e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061563  lea     rcx, [rsp+598h+var_508]
0x18006156b  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180061570  nop
0x180061571  mov     rdi, qword ptr [rsp+598h+var_508]
0x180061579  test    rdi, rdi
0x18006157c  jz      short loc_1800615A0
0x18006157e  mov     rax, [rsp+598h+var_520]
0x180061583  mov     [rsp+598h+var_510], rax
0x18006158b  lea     rcx, [rdi+8]; newString
0x18006158f  lea     rdx, [rsp+598h+var_510]; HSTRING *
0x180061597  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18006159c  mov     ebx, eax
0x18006159e  jmp     short loc_1800615A5
0x1800615a0  mov     ebx, 8007000Eh
0x1800615a5  mov     rcx, [rsp+598h]; this
0x1800615ad  test    ebx, ebx
0x1800615af  jns     short loc_1800615C5
0x1800615b1  mov     r9d, ebx; char *
0x1800615b4  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800615bb  mov     edx, 6C7h; void *
0x1800615c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800615c5  lea     rcx, [rsp+598h+var_4C0]
0x1800615cd  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x1800615d2  nop
0x1800615d3  mov     rbx, [rsp+598h+var_518]
0x1800615db  mov     [rsp+598h+var_510], rbx
0x1800615e3  mov     rsi, [rsp+598h+var_4C0]
0x1800615eb  lea     rcx, [rsi+8]; newString
0x1800615ef  lea     rdx, [rsp+598h+var_510]; HSTRING *
0x1800615f7  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800615fc  mov     rcx, [rsp+598h]; this
0x180061604  test    eax, eax
0x180061606  jns     short loc_18006161C
0x180061608  mov     r9d, eax; char *
0x18006160b  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180061612  mov     edx, 6CBh; void *
0x180061617  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006161c  lea     rcx, [rsp+598h+var_510]
0x180061624  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180061629  nop
0x18006162a  mov     r14, [rsp+598h+var_510]
0x180061632  lea     rcx, [r14+8]; newString
0x180061636  lea     rdx, [rsp+598h+var_4B0]; HSTRING *
0x18006163e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180061643  mov     rcx, [rsp+598h]; this
0x18006164b  test    eax, eax
0x18006164d  jns     short loc_180061663
0x18006164f  mov     r9d, eax; char *
0x180061652  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180061659  mov     edx, 6CEh; void *
0x18006165e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061663  lea     rdx, [rsp+598h+var_338]
0x18006166b  lea     rcx, [rsp+598h+var_488]
0x180061673  call    ?Split@LaunchFileAsync@LauncherClientProvider@@QEAA?AV12@XZ; LauncherClientProvider::LaunchFileAsync::Split(void)
0x180061678  nop
0x180061679  lea     rax, [rsp+598h+var_338]
0x180061681  mov     [rsp+598h+var_538], rax
0x180061686  lea     rax, [rsp+598h+var_4C0]
0x18006168e  mov     [rsp+598h+var_540], rax
0x180061693  lea     rax, [rsp+598h+var_510]
0x18006169b  mov     [rsp+598h+var_548], rax
0x1800616a0  lea     rax, [rsp+598h+var_4D0]
0x1800616a8  mov     [rsp+598h+var_550], rax
0x1800616ad  lea     rax, [rsp+598h+var_4F0]
0x1800616b5  mov     [rsp+598h+var_558], rax
0x1800616ba  lea     rax, [rsp+598h+var_4E0]
0x1800616c2  mov     [rsp+598h+var_560], rax
0x1800616c7  lea     rax, [rsp+598h+var_4B8]
0x1800616cf  mov     [rsp+598h+var_568], rax
0x1800616d4  lea     rax, [rsp+598h+var_4F8]
0x1800616dc  mov     [rsp+598h+var_570], rax
0x1800616e1  lea     rax, [rsp+598h+var_508]
0x1800616e9  mov     qword ptr [rsp+598h+var_578], rax; int
0x1800616ee  lea     r9, [rsp+598h+var_528]
0x1800616f3  lea     r8, [rsp+598h+var_500]
0x1800616fb  lea     rdx, [rsp+598h+var_4D8]
0x180061703  lea     rcx, [rsp+598h+var_1E8]
0x18006170b  call    ??0_lambda_4c3535c0fa3976dd819b46a4876c5029_@@QEAA@AEBV?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIAsUserPartialTrustComponentHost@Launch@Internal@System@Windows@@@23@AEBKAEBV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@23@AEBV?$ComPtr@UIStorageItem@Storage@Windows@@@23@3AEBV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@23@AEBV?$ComPtr@UIStorageFileQueryResult@Search@Storage@Windows@@@23@AEB_K33AEBVLaunchFileAsync@LauncherClientProvider@@@Z; _lambda_4c3535c0fa3976dd819b46a4876c5029_::_lambda_4c3535c0fa3976dd819b46a4876c5029_(Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService> const &,Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::IAsUserPartialTrustComponentHost> const &,ulong const &,Microsoft::WRL::ComPtr<CRefCountedObject<Microsoft::WRL::Wrappers::HString>> const &,Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem> const &,Microsoft::WRL::ComPtr<CRefCountedObject<Microsoft::WRL::Wrappers::HString>> const &,Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass> const &,Microsoft::WRL::ComPtr<Windows::Storage::Search::IStorageFileQueryResult> const &,unsigned __int64 const &,Microsoft::WRL::ComPtr<CRefCountedObject<Microsoft::WRL::Wrappers::HString>> const &,Microsoft::WRL::ComPtr<CRefCountedObject<Microsoft::WRL::Wrappers::HString>> const &,LauncherClientProvider::LaunchFileAsync const &)
0x180061710  nop
0x180061711  mov     [rsp+598h+var_4D0], 3
0x18006171c  mov     [rsp+598h+var_4CC], 80h
0x180061728  mov     rcx, rax
0x18006172b  call    ??$MakeOpLambda@$0A@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@Windows@@V_lambda_677a0aa250d01c8e687696f106069bec_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@Windows@@@01@$$QEAV_lambda_677a0aa250d01c8e687696f106069bec_@@@Z; Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4>,_lambda_677a0aa250d01c8e687696f106069bec_,>(_lambda_677a0aa250d01c8e687696f106069bec_ &&)
0x180061730  mov     r9, rax
0x180061733  xor     r8d, r8d
0x180061736  mov     rdx, r12
0x180061739  lea     rcx, [rsp+598h+var_4D0]
0x180061741  call    ??$MakeAsyncOperationHelper@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@Windows@@W4LaunchFileStatus@System@3@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@W4LaunchFileStatus@System@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4>,Windows::System::LaunchFileStatus,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::System::LaunchFileStatus> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4>> *)
0x180061746  mov     r12d, eax
0x180061749  lea     rcx, [rsp+598h+var_1E8]; this
0x180061751  call    ??1_lambda_677a0aa250d01c8e687696f106069bec_@@QEAA@XZ; _lambda_677a0aa250d01c8e687696f106069bec_::~_lambda_677a0aa250d01c8e687696f106069bec_(void)
0x180061756  xor     edx, edx
0x180061758  lea     rcx, [rsp+598h+var_488]
0x180061760  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180061765  test    r12d, r12d
0x180061768  jns     short loc_180061787
0x18006176a  mov     rcx, [rsp+598h]; this
0x180061772  mov     r9d, r12d; char *
0x180061775  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x18006177c  mov     edx, 747h; void *
0x180061781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061786  nop
0x180061787  lea     rcx, [rsp+598h+var_338]; this
0x18006178f  call    ??1LaunchFileAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::LaunchFileAsync::~LaunchFileAsync(void)
0x180061794  nop
0x180061795  test    r14, r14
0x180061798  jz      short loc_1800617AA
0x18006179a  mov     rax, [r14]
0x18006179d  mov     rcx, r14
0x1800617a0  mov     rax, [rax+10h]
  ... truncated ...
```
