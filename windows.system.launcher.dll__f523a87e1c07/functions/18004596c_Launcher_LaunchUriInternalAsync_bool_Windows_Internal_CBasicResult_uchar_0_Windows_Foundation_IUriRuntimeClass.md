# Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x18004596c`
- end: `0x18004618c`
- name: `??$_LaunchUriInternalAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@3@PEAUILauncherOptions@73@PEAUIPropertySet@Collections@23@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@_N@23@@Z`
- size: `2080`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int, HSTRING, int, HSTRING string, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043f78`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x180027a10`
- `0x180027c60`
- `0x180027d80`
- `0x18003ef08`
- `0x18004465c`
- `0x1800458ac`
- `0x18004596c`
- `0x1800471e0`
- `0x18004720c`
- `0x180047254`
- `0x180047570`
- `0x1800475d0`
- `0x1800477e4`
- `0x180047890`
- `0x180047fc4`
- `0x1800596d8`
- `0x18006e350`
- `0x18008a030`
- `0x18008df9c`
- `0x18008efac`
- `0x180090aa4`
- `0x18009386c`
- `0x1800993dc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045f0b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045f0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800459c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800459c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045b8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045b8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460eb`

## pseudocode

```c
__int64 __fastcall Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<unsigned char,0>>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        int a5,
        HSTRING a6,
        int a7,
        HSTRING string,
        __int64 a9)
{
  HSTRING *v11; // r15
  __int64 FallbackUri; // rax
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rdi
  int v21; // eax
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 (__fastcall *v26)(_QWORD, GUID *, HSTRING *); // rbx
  int v27; // eax
  int v28; // eax
  __int64 OwnerWindowId; // rbx
  __int64 v30; // rsi
  int v31; // eax
  HSTRING *v32; // rdx
  int CallerAumidOrProcessName; // eax
  HSTRING v34; // rbx
  HSTRING v35; // r14
  int v36; // eax
  char *v37; // r12
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // edi
  int v41; // [rsp+20h] [rbp-5B8h]
  int v42; // [rsp+20h] [rbp-5B8h]
  char v43; // [rsp+90h] [rbp-548h] BYREF
  _BYTE v44[7]; // [rsp+91h] [rbp-547h] BYREF
  HSTRING v45; // [rsp+98h] [rbp-540h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-538h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-530h] BYREF
  int v48; // [rsp+B0h] [rbp-528h] BYREF
  int v49; // [rsp+B8h] [rbp-520h] BYREF
  HSTRING v50; // [rsp+C0h] [rbp-518h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-510h] BYREF
  int v52; // [rsp+D0h] [rbp-508h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-500h] BYREF
  HSTRING v54; // [rsp+E0h] [rbp-4F8h] BYREF
  __int64 v55; // [rsp+E8h] [rbp-4F0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+F0h] [rbp-4E8h] BYREF
  int v57; // [rsp+F8h] [rbp-4E0h] BYREF
  __int64 v58; // [rsp+FCh] [rbp-4DCh]
  _BYTE v59[8]; // [rsp+108h] [rbp-4D0h] BYREF
  __int64 v60; // [rsp+110h] [rbp-4C8h] BYREF
  _QWORD v61[3]; // [rsp+118h] [rbp-4C0h] BYREF
  _BYTE v62[336]; // [rsp+130h] [rbp-4A8h] BYREF
  _BYTE v63[336]; // [rsp+280h] [rbp-358h] BYREF
  _BYTE v64[464]; // [rsp+3D0h] [rbp-208h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+0h]

  v49 = a3;
  v54 = string;
  v60 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  LauncherClientProvider::LaunchUriAsync::Start<unsigned short const *>((LauncherClientProvider::LaunchUriAsync *)v62);
  v61[2] = 0;
  v53 = 0;
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&StringRawBuffer);
  v11 = (HSTRING *)StringRawBuffer;
  if ( !StringRawBuffer )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x214,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x8007000ELL,
      v41);
  v51 = 0;
  v48 = 0;
  v44[0] = 0;
  v43 = 0;
  v52 = 0;
  if ( a4 )
  {
    FallbackUri = GetFallbackUri(&v55, a4);
    Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(&v53, FallbackUri);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    v13 = (*a4)[10];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v14 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v13)(a4, &v51);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v14,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v62);
      return v15;
    }
    v47 = 0;
    v17 = **a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v18 = v17(a4, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v47);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v18,
        v41);
    v19 = v47;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 48LL);
    WindowsDeleteString(v11[1]);
    v11[1] = 0;
    v21 = v20(v19, v11 + 1);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v21,
        v41);
    v46 = 0;
    v22 = **a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v23 = v22(a4, &GUID_f0770655_4b63_4e3a_9107_4e687841923a, &v46);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v23,
        v41);
    v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v46 + 48LL))(v46, &v43);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v24,
        v41);
    v45 = 0;
    if ( (int)Microsoft::WRL::ComPtr<Windows::System::ILauncherUIOptions>::As<Windows::System::Private::ILauncherUIOptionsInternal>(
                &v51,
                &v45) >= 0 )
    {
      v25 = (*(__int64 (__fastcall **)(HSTRING, _BYTE *))(*(_QWORD *)v45 + 80LL))(v45, v44);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v25,
          v41);
    }
    v50 = 0;
    v26 = (__int64 (__fastcall *)(_QWORD, GUID *, HSTRING *))**a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v27 = v26(a4, &GUID_8a9b29f1_7ca7_49de_9bd3_3c5b7184f616, &v50);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v27,
        v41);
    v28 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)v50 + 48LL))(v50, &v52);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v28,
        v41);
    OwnerWindowId = (unsigned int)GetOwnerWindowId(a4);
    ValidateUIThreadRequirements(OwnerWindowId);
    v48 = OwnerWindowId;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  }
  GetLauncherService(v59);
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v55);
  v30 = v55;
  v31 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(v55 + 8), &v54);
  if ( v31 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v31,
      v41);
  WindowsDeleteString(0);
  v50 = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v50, v32);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      v41);
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v54);
  v34 = v50;
  v45 = v50;
  v35 = v54;
  v36 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v54 + 1, &v45);
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v36,
      v41);
  v46 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
  v47 = 0;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v47);
  v45 = a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v45);
  v37 = (char *)operator new(0x20u);
  *((_DWORD *)v37 + 2) = 1;
  *((_DWORD *)v37 + 3) = 1;
  *(_QWORD *)v37 = ___7___Ref_count_obj2_VLaunchUriAsyncOpState__2_____LaunchUriInternalAsync__NV__CBasicResult_E_0A__Internal_Windows___Launcher__AEAAJPEAUIUriRuntimeClass_Foundation_Windows__W4LaunchType_Launch_Internal_System_5_PEAUILauncherOptions_95_PEAUIPropertySet_Collections_45_3_KPEAUHSTRING____PEAPEAU__IAsyncOperation__N_45__Z__std__6B_;
  *((_QWORD *)v37 + 3) = 0;
  *((_QWORD *)v37 + 2) = 0;
  InitializeSRWLock((PSRWLOCK)v37 + 3);
  v61[0] = v37 + 16;
  v61[1] = v37;
  LauncherClientProvider::LaunchUriAsync::Split(v62, v63);
  v38 = _lambda_9d4e42fefa12b04ae325b222a27027ce_::_lambda_9d4e42fefa12b04ae325b222a27027ce_(
          (unsigned int)v64,
          (unsigned int)v59,
          (unsigned int)&v48,
          (unsigned int)&v46,
          (__int64)&v49,
          (__int64)&v51,
          (__int64)&StringRawBuffer,
          (__int64)&v47,
          (__int64)&v45,
          (__int64)&v53,
          (__int64)&v60,
          (__int64)v44,
          (__int64)&v43,
          (__int64)&v55,
          (__int64)&v52,
          (__int64)&v54,
          (__int64)v63,
          (__int64)v61);
  v57 = 3;
  v58 = 128;
  v39 = Windows::Internal::MakeOpLambda<1,Windows::Internal::CBasicResult<unsigned char,0>,_lambda_da225a7cdf57dc8e8263eb3946dbc5ab_,>(v38);
  v40 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler>(
          &v57,
          a9,
          0,
          v39);
  _lambda_cf6083327d3aaca30ba38e0587da4456_::~_lambda_cf6083327d3aaca30ba38e0587da4456_((_lambda_cf6083327d3aaca30ba38e0587da4456_ *)v64);
  wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v62,
    0);
  if ( v40 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v40,
      v42);
  LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v63);
  if ( v37 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  if ( v35 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v35 + 16LL))(v35);
  WindowsDeleteString(v34);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  if ( v11 )
    (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v62);
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x18004596c  mov     r11, rsp
0x18004596f  mov     [r11+8], rbx
0x180045973  mov     [r11+10h], rsi
0x180045977  push    rdi
0x180045978  push    r12
0x18004597a  push    r13
0x18004597c  push    r14
0x18004597e  push    r15
0x180045980  sub     rsp, 5B0h
0x180045987  mov     rax, cs:__security_cookie
0x18004598e  xor     rax, rsp
0x180045991  mov     [rsp+5D8h+var_38], rax
0x180045999  mov     r14, r9
0x18004599c  mov     r12, rdx
0x18004599f  mov     [r11-520h], r8d
0x1800459a6  mov     rcx, [rsp+5D8h+string]; string
0x1800459ae  mov     [r11-4F8h], rcx
0x1800459b5  mov     r13, [rsp+5D8h+arg_40]
0x1800459bd  xor     edi, edi
0x1800459bf  mov     [r11-4C8h], rdi
0x1800459c6  xor     edx, edx; length
0x1800459c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800459ce  mov     [rsp+5D8h+var_4E8], rax
0x1800459d6  lea     rdx, [rsp+5D8h+var_4E8]
0x1800459de  lea     rcx, [rsp+5D8h+var_4A8]; this
0x1800459e6  call    ??$Start@PEBG@LaunchUriAsync@LauncherClientProvider@@SA?AV01@$$QEAPEBG@Z; LauncherClientProvider::LaunchUriAsync::Start<ushort const *>(ushort const * &&)
0x1800459eb  nop
0x1800459ec  mov     [rsp+5D8h+var_4B0], rdi
0x1800459f4  mov     [rsp+5D8h+var_500], rdi
0x1800459fc  lea     rcx, [rsp+5D8h+var_4E8]
0x180045a04  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180045a09  nop
0x180045a0a  mov     rcx, [rsp+5D8h]; this
0x180045a12  mov     r15, [rsp+5D8h+var_4E8]
0x180045a1a  test    r15, r15
0x180045a1d  jnz     short loc_180045A36
0x180045a1f  mov     r9d, 8007000Eh; char *
0x180045a25  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045a2c  mov     edx, 214h; void *
0x180045a31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045a36  mov     [rsp+5D8h+var_510], rdi
0x180045a3e  mov     [rsp+5D8h+var_528], edi
0x180045a45  mov     [rsp+5D8h+var_547], dil
0x180045a4d  mov     [rsp+5D8h+var_548], dil
0x180045a55  mov     [rsp+5D8h+var_508], edi
0x180045a5c  test    r14, r14
0x180045a5f  jz      loc_180045D97
0x180045a65  mov     rdx, r14
0x180045a68  lea     rcx, [rsp+5D8h+var_4F0]
0x180045a70  call    ?GetFallbackUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherOptions@System@Windows@@@Z; GetFallbackUri(Windows::System::ILauncherOptions *)
0x180045a75  mov     rdx, rax
0x180045a78  lea     rcx, [rsp+5D8h+var_500]
0x180045a80  call    ??4?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService> &&)
0x180045a85  lea     rcx, [rsp+5D8h+var_4F0]
0x180045a8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045a92  mov     rax, [r14]
0x180045a95  mov     rbx, [rax+50h]
0x180045a99  lea     rcx, [rsp+5D8h+var_510]
0x180045aa1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045aa6  lea     rdx, [rsp+5D8h+var_510]
0x180045aae  mov     rcx, r14
0x180045ab1  mov     rax, rbx
0x180045ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ab9  mov     ebx, eax
0x180045abb  test    eax, eax
0x180045abd  jns     short loc_180045B21
0x180045abf  mov     rcx, [rsp+5D8h]; this
0x180045ac7  mov     r9d, eax; char *
0x180045aca  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045ad1  mov     edx, 223h; void *
0x180045ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045adb  nop
0x180045adc  lea     rcx, [rsp+5D8h+var_510]
0x180045ae4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045ae9  nop
0x180045aea  test    r15, r15
0x180045aed  jz      short loc_180045AFF
0x180045aef  mov     rax, [r15]
0x180045af2  mov     rcx, r15
0x180045af5  mov     rax, [rax+10h]
0x180045af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045afe  nop
0x180045aff  lea     rcx, [rsp+5D8h+var_500]
0x180045b07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045b0c  nop
0x180045b0d  lea     rcx, [rsp+5D8h+var_4A8]; this
0x180045b15  call    ??1LaunchUriAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync(void)
0x180045b1a  mov     eax, ebx
0x180045b1c  jmp     loc_18004615E
0x180045b21  mov     [rsp+5D8h+var_530], rdi
0x180045b29  mov     rax, [r14]
0x180045b2c  mov     rbx, [rax]
0x180045b2f  lea     rcx, [rsp+5D8h+var_530]
0x180045b37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045b3c  lea     r8, [rsp+5D8h+var_530]
0x180045b44  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x180045b4b  mov     rcx, r14
0x180045b4e  mov     rax, rbx
0x180045b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b56  mov     rcx, [rsp+5D8h]; this
0x180045b5e  test    eax, eax
0x180045b60  jns     short loc_180045B76
0x180045b62  mov     r9d, eax; char *
0x180045b65  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045b6c  mov     edx, 227h; void *
0x180045b71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045b76  mov     rsi, [rsp+5D8h+var_530]
0x180045b7e  mov     rax, [rsi]
0x180045b81  mov     rdi, [rax+30h]
0x180045b85  lea     rbx, [r15+8]
0x180045b89  mov     rcx, [rbx]; string
0x180045b8c  call    cs:__imp_WindowsDeleteString
0x180045b92  mov     qword ptr [rbx], 0
0x180045b99  mov     rdx, rbx
0x180045b9c  mov     rcx, rsi
0x180045b9f  mov     rax, rdi
0x180045ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ba7  mov     rcx, [rsp+5D8h]; this
0x180045baf  xor     edi, edi
0x180045bb1  test    eax, eax
0x180045bb3  jns     short loc_180045BC9
0x180045bb5  mov     r9d, eax; char *
0x180045bb8  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045bbf  mov     edx, 228h; void *
0x180045bc4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045bc9  mov     [rsp+5D8h+var_538], rdi
0x180045bd1  mov     rax, [r14]
0x180045bd4  mov     rbx, [rax]
0x180045bd7  lea     rcx, [rsp+5D8h+var_538]
0x180045bdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045be4  lea     r8, [rsp+5D8h+var_538]
0x180045bec  lea     rdx, _GUID_f0770655_4b63_4e3a_9107_4e687841923a
0x180045bf3  mov     rcx, r14
0x180045bf6  mov     rax, rbx
0x180045bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bfe  mov     rcx, [rsp+5D8h]; this
0x180045c06  test    eax, eax
0x180045c08  jns     short loc_180045C1E
0x180045c0a  mov     r9d, eax; char *
0x180045c0d  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045c14  mov     edx, 22Ch; void *
0x180045c19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045c1e  mov     rcx, [rsp+5D8h+var_538]
0x180045c26  mov     rax, [rcx]
0x180045c29  lea     rdx, [rsp+5D8h+var_548]
0x180045c31  mov     rax, [rax+30h]
0x180045c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c3a  mov     rcx, [rsp+5D8h]; this
0x180045c42  test    eax, eax
0x180045c44  jns     short loc_180045C5A
0x180045c46  mov     r9d, eax; char *
0x180045c49  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045c50  mov     edx, 22Dh; void *
0x180045c55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045c5a  mov     [rsp+5D8h+var_540], rdi
0x180045c62  lea     rdx, [rsp+5D8h+var_540]
0x180045c6a  lea     rcx, [rsp+5D8h+var_510]
0x180045c72  call    ??$As@UILauncherUIOptionsInternal@Private@System@Windows@@@?$ComPtr@UILauncherUIOptions@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILauncherUIOptionsInternal@Private@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::ILauncherUIOptions>::As<Windows::System::Private::ILauncherUIOptionsInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Private::ILauncherUIOptionsInternal>>)
0x180045c77  test    eax, eax
0x180045c79  js      short loc_180045CB7
0x180045c7b  mov     rcx, [rsp+5D8h+var_540]
0x180045c83  mov     rax, [rcx]
0x180045c86  lea     rdx, [rsp+5D8h+var_547]
0x180045c8e  mov     rax, [rax+50h]
0x180045c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c97  mov     rcx, [rsp+5D8h]; this
0x180045c9f  test    eax, eax
0x180045ca1  jns     short loc_180045CB7
0x180045ca3  mov     r9d, eax; char *
0x180045ca6  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045cad  mov     edx, 234h; void *
0x180045cb2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045cb7  mov     [rsp+5D8h+var_518], rdi
0x180045cbf  mov     rax, [r14]
0x180045cc2  mov     rbx, [rax]
0x180045cc5  lea     rcx, [rsp+5D8h+var_518]
0x180045ccd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045cd2  lea     r8, [rsp+5D8h+var_518]
0x180045cda  lea     rdx, _GUID_8a9b29f1_7ca7_49de_9bd3_3c5b7184f616
0x180045ce1  mov     rcx, r14
0x180045ce4  mov     rax, rbx
0x180045ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cec  mov     rcx, [rsp+5D8h]; this
0x180045cf4  test    eax, eax
0x180045cf6  jns     short loc_180045D0C
0x180045cf8  mov     r9d, eax; char *
0x180045cfb  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045d02  mov     edx, 239h; void *
0x180045d07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d0c  mov     rcx, [rsp+5D8h+var_518]
0x180045d14  mov     rax, [rcx]
0x180045d17  lea     rdx, [rsp+5D8h+var_508]
0x180045d1f  mov     rax, [rax+30h]
0x180045d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d28  mov     rcx, [rsp+5D8h]; this
0x180045d30  test    eax, eax
0x180045d32  jns     short loc_180045D48
0x180045d34  mov     r9d, eax; char *
0x180045d37  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045d3e  mov     edx, 23Ah; void *
0x180045d43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d48  mov     rcx, r14
0x180045d4b  call    GetOwnerWindowId
0x180045d50  mov     ebx, eax
0x180045d52  mov     ecx, eax
0x180045d54  call    ?ValidateUIThreadRequirements@@YAXUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; ValidateUIThreadRequirements(Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180045d59  mov     [rsp+5D8h+var_528], ebx
0x180045d60  lea     rcx, [rsp+5D8h+var_518]
0x180045d68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045d6d  nop
0x180045d6e  lea     rcx, [rsp+5D8h+var_540]
0x180045d76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045d7b  nop
0x180045d7c  lea     rcx, [rsp+5D8h+var_538]
0x180045d84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045d89  nop
0x180045d8a  lea     rcx, [rsp+5D8h+var_530]
0x180045d92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045d97  lea     rcx, [rsp+5D8h+var_4D0]
0x180045d9f  call    ?GetLauncherService@@YA?AV?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@XZ; GetLauncherService(void)
0x180045da4  nop
0x180045da5  lea     rcx, [rsp+5D8h+var_4F0]
0x180045dad  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180045db2  nop
0x180045db3  mov     rsi, [rsp+5D8h+var_4F0]
0x180045dbb  lea     rcx, [rsi+8]; newString
0x180045dbf  lea     rdx, [rsp+5D8h+var_4F8]; HSTRING *
0x180045dc7  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180045dcc  mov     rcx, [rsp+5D8h]; this
0x180045dd4  test    eax, eax
0x180045dd6  jns     short loc_180045DED
0x180045dd8  mov     r9d, eax; char *
0x180045ddb  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045de2  mov     edx, 248h; void *
0x180045de7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045dec  nop
0x180045ded  xor     ecx, ecx; string
0x180045def  call    cs:__imp_WindowsDeleteString
0x180045df5  mov     [rsp+5D8h+var_518], rdi
0x180045dfd  lea     rcx, [rsp+5D8h+var_518]; this
0x180045e05  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x180045e0a  mov     rcx, [rsp+5D8h]; this
0x180045e12  test    eax, eax
0x180045e14  jns     short loc_180045E2A
0x180045e16  mov     r9d, eax; char *
0x180045e19  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045e20  mov     edx, 24Ch; void *
0x180045e25  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045e2a  lea     rcx, [rsp+5D8h+var_4F8]
0x180045e32  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180045e37  nop
0x180045e38  mov     rbx, [rsp+5D8h+var_518]
0x180045e40  mov     [rsp+5D8h+var_540], rbx
0x180045e48  mov     r14, [rsp+5D8h+var_4F8]
0x180045e50  lea     rcx, [r14+8]; newString
0x180045e54  lea     rdx, [rsp+5D8h+var_540]; HSTRING *
0x180045e5c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180045e61  mov     rcx, [rsp+5D8h]; this
0x180045e69  test    eax, eax
0x180045e6b  jns     short loc_180045E81
0x180045e6d  mov     r9d, eax; char *
0x180045e70  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180045e77  mov     edx, 24Fh; void *
0x180045e7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045e81  mov     [rsp+5D8h+var_538], r12
0x180045e89  lea     rcx, [rsp+5D8h+var_538]
0x180045e91  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180045e96  nop
0x180045e97  mov     [rsp+5D8h+var_530], rdi
0x180045e9f  lea     rcx, [rsp+5D8h+var_530]
0x180045ea7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180045eac  nop
0x180045ead  mov     rax, [rsp+5D8h+arg_28]
0x180045eb5  mov     [rsp+5D8h+var_540], rax
0x180045ebd  lea     rcx, [rsp+5D8h+var_540]
0x180045ec5  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180045eca  nop
0x180045ecb  mov     ecx, 20h ; ' '; Size
0x180045ed0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045ed5  mov     r12, rax
0x180045ed8  mov     eax, 1
0x180045edd  mov     [r12+8], eax
0x180045ee2  mov     [r12+0Ch], eax
0x180045ee7  lea     rax, ??_7?$_Ref_count_obj2@VLaunchUriAsyncOpState@?2???$_LaunchUriInternalAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@5@PEAUILauncherOptions@95@PEAUIPropertySet@Collections@45@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@_N@45@@Z@@std@@6B@; const std::_Ref_count_obj2<`Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)'::`3'::LaunchUriAsyncOpState>::`vftable'
0x180045eee  mov     [r12], rax
0x180045ef2  lea     rdi, [r12+10h]
0x180045ef7  mov     qword ptr [r12+18h], 0
0x180045f00  mov     qword ptr [rdi], 0
0x180045f07  lea     rcx, [rdi+8]; SRWLock
0x180045f0b  call    cs:__imp_InitializeSRWLock
0x180045f11  mov     [rsp+5D8h+var_4C0], rdi
0x180045f19  mov     [rsp+5D8h+var_4B8], r12
0x180045f21  lea     rdx, [rsp+5D8h+var_358]
0x180045f29  lea     rcx, [rsp+5D8h+var_4A8]
0x180045f31  call    ?Split@LaunchUriAsync@LauncherClientProvider@@QEAA?AV12@XZ; LauncherClientProvider::LaunchUriAsync::Split(void)
0x180045f36  nop
0x180045f37  lea     rax, [rsp+5D8h+var_4C0]
0x180045f3f  mov     [rsp+5D8h+var_550], rax
0x180045f47  lea     rax, [rsp+5D8h+var_358]
0x180045f4f  mov     [rsp+5D8h+var_558], rax
  ... truncated ...
```
