# Launcher::_LaunchUriInternalAsync<Windows::System::LaunchUriStatus,Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriStatus> * *)

- ea: `0x180046194`
- end: `0x1800469ad`
- name: `??$_LaunchUriInternalAsync@W4LaunchUriStatus@System@Windows@@V?$CBasicResult@W4LaunchUriStatus@System@Windows@@$02@Internal@3@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@3@PEAUILauncherOptions@73@PEAUIPropertySet@Collections@23@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@W4LaunchUriStatus@System@Windows@@@23@@Z`
- size: `2073`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int, HSTRING, char, HSTRING string, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180044184`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x180027a10`
- `0x180027c60`
- `0x180027d80`
- `0x18003ef08`
- `0x18004465c`
- `0x1800447e4`
- `0x1800458ac`
- `0x180046194`
- `0x1800471e0`
- `0x18004720c`
- `0x180047254`
- `0x180047570`
- `0x1800475d0`
- `0x1800477e4`
- `0x180047890`
- `0x180050e68`
- `0x1800596d8`
- `0x18006e350`
- `0x18008a030`
- `0x18008df9c`
- `0x18008efac`
- `0x18009386c`
- `0x1800993dc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004672c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004672c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800461e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800461e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800463ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004690c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800463ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004690c`

## pseudocode

```c
__int64 __fastcall Launcher::_LaunchUriInternalAsync<enum Windows::System::LaunchUriStatus,Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        int a5,
        HSTRING a6,
        char a7,
        HSTRING string,
        __int64 a9)
{
  __int64 v11; // r13
  HSTRING *v12; // r15
  __int64 FallbackUri; // rax
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rdi
  int v22; // eax
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rbx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 (__fastcall *v27)(_QWORD, GUID *, HSTRING *); // rbx
  int v28; // eax
  int v29; // eax
  unsigned int OwnerWindowId; // ebx
  __int64 v31; // rsi
  int v32; // eax
  HSTRING *v33; // rdx
  int CallerAumidOrProcessName; // eax
  HSTRING v35; // rbx
  HSTRING v36; // r14
  int v37; // eax
  char *v38; // r12
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // edi
  int v42; // [rsp+20h] [rbp-5B8h]
  int v43; // [rsp+20h] [rbp-5B8h]
  char v44; // [rsp+90h] [rbp-548h] BYREF
  _BYTE v45[7]; // [rsp+91h] [rbp-547h] BYREF
  HSTRING v46; // [rsp+98h] [rbp-540h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-538h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-530h] BYREF
  unsigned int v49; // [rsp+B0h] [rbp-528h] BYREF
  int v50; // [rsp+B8h] [rbp-520h] BYREF
  HSTRING v51; // [rsp+C0h] [rbp-518h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-510h] BYREF
  int v53; // [rsp+D0h] [rbp-508h] BYREF
  __int64 v54; // [rsp+D8h] [rbp-500h] BYREF
  HSTRING v55; // [rsp+E0h] [rbp-4F8h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-4F0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+F0h] [rbp-4E8h] BYREF
  int v58; // [rsp+F8h] [rbp-4E0h] BYREF
  __int64 v59; // [rsp+FCh] [rbp-4DCh]
  _BYTE v60[8]; // [rsp+108h] [rbp-4D0h] BYREF
  _QWORD v61[4]; // [rsp+110h] [rbp-4C8h] BYREF
  _BYTE v62[336]; // [rsp+130h] [rbp-4A8h] BYREF
  _BYTE v63[336]; // [rsp+280h] [rbp-358h] BYREF
  _BYTE v64[464]; // [rsp+3D0h] [rbp-208h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+0h]

  v50 = a3;
  v55 = string;
  v11 = a9;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  LauncherClientProvider::LaunchUriAsync::Start<unsigned short const *>((LauncherClientProvider::LaunchUriAsync *)v62);
  v61[2] = 0;
  v54 = 0;
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&StringRawBuffer);
  v12 = (HSTRING *)StringRawBuffer;
  if ( !StringRawBuffer )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x214,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x8007000ELL,
      v42);
  v52 = 0;
  v49 = 0;
  v45[0] = 0;
  v44 = 0;
  v53 = 0;
  if ( a4 )
  {
    FallbackUri = GetFallbackUri(&v56, a4);
    Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(&v54, FallbackUri);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    v14 = (*a4)[10];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v14)(a4, &v52);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v15,
        v42);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      if ( v12 )
        (*((void (__fastcall **)(HSTRING *))*v12 + 2))(v12);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v62);
      return v16;
    }
    v48 = 0;
    v18 = **a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v19 = v18(a4, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v48);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v19,
        v42);
    v20 = v48;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 48LL);
    WindowsDeleteString(v12[1]);
    v12[1] = 0;
    v22 = v21(v20, v12 + 1);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v22,
        v42);
    v47 = 0;
    v23 = **a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v24 = v23(a4, &GUID_f0770655_4b63_4e3a_9107_4e687841923a, &v47);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v24,
        v42);
    v25 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v47 + 48LL))(v47, &v44);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v25,
        v42);
    v46 = 0;
    if ( (int)Microsoft::WRL::ComPtr<Windows::System::ILauncherUIOptions>::As<Windows::System::Private::ILauncherUIOptionsInternal>(
                &v52,
                &v46) >= 0 )
    {
      v26 = (*(__int64 (__fastcall **)(HSTRING, _BYTE *))(*(_QWORD *)v46 + 80LL))(v46, v45);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v26,
          v42);
    }
    v51 = 0;
    v27 = (__int64 (__fastcall *)(_QWORD, GUID *, HSTRING *))**a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v28 = v27(a4, &GUID_8a9b29f1_7ca7_49de_9bd3_3c5b7184f616, &v51);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v28,
        v42);
    v29 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)v51 + 48LL))(v51, &v53);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v29,
        v42);
    OwnerWindowId = GetOwnerWindowId(a4);
    ValidateUIThreadRequirements(OwnerWindowId);
    v49 = OwnerWindowId;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  }
  GetLauncherService(v60);
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v56);
  v31 = v56;
  v32 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(v56 + 8), &v55);
  if ( v32 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v32,
      v42);
  WindowsDeleteString(0);
  v51 = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v51, v33);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      v42);
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v55);
  v35 = v51;
  v46 = v51;
  v36 = v55;
  v37 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v55 + 1, &v46);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v37,
      v42);
  v47 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v47);
  v48 = 0;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
  v46 = a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
  v38 = (char *)operator new(0x20u);
  *((_DWORD *)v38 + 2) = 1;
  *((_DWORD *)v38 + 3) = 1;
  *(_QWORD *)v38 = ___7___Ref_count_obj2_VLaunchUriAsyncOpState__2_____LaunchUriInternalAsync__NV__CBasicResult_E_0A__Internal_Windows___Launcher__AEAAJPEAUIUriRuntimeClass_Foundation_Windows__W4LaunchType_Launch_Internal_System_5_PEAUILauncherOptions_95_PEAUIPropertySet_Collections_45_3_KPEAUHSTRING____PEAPEAU__IAsyncOperation__N_45__Z__std__6B_;
  *((_QWORD *)v38 + 3) = 0;
  *((_QWORD *)v38 + 2) = 0;
  InitializeSRWLock((PSRWLOCK)v38 + 3);
  v61[0] = v38 + 16;
  v61[1] = v38;
  LauncherClientProvider::LaunchUriAsync::Split(v62, v63);
  v39 = _lambda_9d4e42fefa12b04ae325b222a27027ce_::_lambda_9d4e42fefa12b04ae325b222a27027ce_(
          (unsigned int)v64,
          (unsigned int)v60,
          (unsigned int)&v49,
          (unsigned int)&v47,
          (__int64)&v50,
          (__int64)&v52,
          (__int64)&StringRawBuffer,
          (__int64)&v48,
          (__int64)&v46,
          (__int64)&v54,
          (__int64)&a7,
          (__int64)v45,
          (__int64)&v44,
          (__int64)&v56,
          (__int64)&v53,
          (__int64)&v55,
          (__int64)v63,
          (__int64)v61);
  v58 = 3;
  v59 = 128;
  v40 = Windows::Internal::MakeOpLambda<1,Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>,_lambda_cf6083327d3aaca30ba38e0587da4456_,>(v39);
  v41 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>,enum Windows::System::LaunchUriStatus,Windows::Internal::ComTaskPoolHandler>(
          &v58,
          v11,
          0,
          v40);
  _lambda_cf6083327d3aaca30ba38e0587da4456_::~_lambda_cf6083327d3aaca30ba38e0587da4456_((_lambda_cf6083327d3aaca30ba38e0587da4456_ *)v64);
  wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v62,
    0);
  if ( v41 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v41,
      v43);
  LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v63);
  if ( v38 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  if ( v36 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
  WindowsDeleteString(v35);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  if ( v12 )
    (*((void (__fastcall **)(HSTRING *))*v12 + 2))(v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v62);
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x180046194  mov     r11, rsp
0x180046197  mov     [r11+8], rbx
0x18004619b  mov     [r11+10h], rsi
0x18004619f  push    rdi
0x1800461a0  push    r12
0x1800461a2  push    r13
0x1800461a4  push    r14
0x1800461a6  push    r15
0x1800461a8  sub     rsp, 5B0h
0x1800461af  mov     rax, cs:__security_cookie
0x1800461b6  xor     rax, rsp
0x1800461b9  mov     [rsp+5D8h+var_38], rax
0x1800461c1  mov     r14, r9
0x1800461c4  mov     r12, rdx
0x1800461c7  mov     [r11-520h], r8d
0x1800461ce  mov     rcx, [rsp+5D8h+string]; string
0x1800461d6  mov     [r11-4F8h], rcx
0x1800461dd  mov     r13, [rsp+5D8h+arg_40]
0x1800461e5  xor     edi, edi
0x1800461e7  xor     edx, edx; length
0x1800461e9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800461ef  mov     [rsp+5D8h+var_4E8], rax
0x1800461f7  lea     rdx, [rsp+5D8h+var_4E8]
0x1800461ff  lea     rcx, [rsp+5D8h+var_4A8]; this
0x180046207  call    ??$Start@PEBG@LaunchUriAsync@LauncherClientProvider@@SA?AV01@$$QEAPEBG@Z; LauncherClientProvider::LaunchUriAsync::Start<ushort const *>(ushort const * &&)
0x18004620c  nop
0x18004620d  mov     [rsp+5D8h+var_4B8], rdi
0x180046215  mov     [rsp+5D8h+var_500], rdi
0x18004621d  lea     rcx, [rsp+5D8h+var_4E8]
0x180046225  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x18004622a  nop
0x18004622b  mov     rcx, [rsp+5D8h]; this
0x180046233  mov     r15, [rsp+5D8h+var_4E8]
0x18004623b  test    r15, r15
0x18004623e  jnz     short loc_180046257
0x180046240  mov     r9d, 8007000Eh; char *
0x180046246  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x18004624d  mov     edx, 214h; void *
0x180046252  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046257  mov     [rsp+5D8h+var_510], rdi
0x18004625f  mov     [rsp+5D8h+var_528], edi
0x180046266  mov     [rsp+5D8h+var_547], dil
0x18004626e  mov     [rsp+5D8h+var_548], dil
0x180046276  mov     [rsp+5D8h+var_508], edi
0x18004627d  test    r14, r14
0x180046280  jz      loc_1800465B8
0x180046286  mov     rdx, r14
0x180046289  lea     rcx, [rsp+5D8h+var_4F0]
0x180046291  call    ?GetFallbackUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherOptions@System@Windows@@@Z; GetFallbackUri(Windows::System::ILauncherOptions *)
0x180046296  mov     rdx, rax
0x180046299  lea     rcx, [rsp+5D8h+var_500]
0x1800462a1  call    ??4?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService> &&)
0x1800462a6  lea     rcx, [rsp+5D8h+var_4F0]
0x1800462ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800462b3  mov     rax, [r14]
0x1800462b6  mov     rbx, [rax+50h]
0x1800462ba  lea     rcx, [rsp+5D8h+var_510]
0x1800462c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800462c7  lea     rdx, [rsp+5D8h+var_510]
0x1800462cf  mov     rcx, r14
0x1800462d2  mov     rax, rbx
0x1800462d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462da  mov     ebx, eax
0x1800462dc  test    eax, eax
0x1800462de  jns     short loc_180046342
0x1800462e0  mov     rcx, [rsp+5D8h]; this
0x1800462e8  mov     r9d, eax; char *
0x1800462eb  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800462f2  mov     edx, 223h; void *
0x1800462f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800462fc  nop
0x1800462fd  lea     rcx, [rsp+5D8h+var_510]
0x180046305  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004630a  nop
0x18004630b  test    r15, r15
0x18004630e  jz      short loc_180046320
0x180046310  mov     rax, [r15]
0x180046313  mov     rcx, r15
0x180046316  mov     rax, [rax+10h]
0x18004631a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004631f  nop
0x180046320  lea     rcx, [rsp+5D8h+var_500]
0x180046328  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004632d  nop
0x18004632e  lea     rcx, [rsp+5D8h+var_4A8]; this
0x180046336  call    ??1LaunchUriAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync(void)
0x18004633b  mov     eax, ebx
0x18004633d  jmp     loc_18004697F
0x180046342  mov     [rsp+5D8h+var_530], rdi
0x18004634a  mov     rax, [r14]
0x18004634d  mov     rbx, [rax]
0x180046350  lea     rcx, [rsp+5D8h+var_530]
0x180046358  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004635d  lea     r8, [rsp+5D8h+var_530]
0x180046365  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x18004636c  mov     rcx, r14
0x18004636f  mov     rax, rbx
0x180046372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046377  mov     rcx, [rsp+5D8h]; this
0x18004637f  test    eax, eax
0x180046381  jns     short loc_180046397
0x180046383  mov     r9d, eax; char *
0x180046386  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x18004638d  mov     edx, 227h; void *
0x180046392  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046397  mov     rsi, [rsp+5D8h+var_530]
0x18004639f  mov     rax, [rsi]
0x1800463a2  mov     rdi, [rax+30h]
0x1800463a6  lea     rbx, [r15+8]
0x1800463aa  mov     rcx, [rbx]; string
0x1800463ad  call    cs:__imp_WindowsDeleteString
0x1800463b3  mov     qword ptr [rbx], 0
0x1800463ba  mov     rdx, rbx
0x1800463bd  mov     rcx, rsi
0x1800463c0  mov     rax, rdi
0x1800463c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463c8  mov     rcx, [rsp+5D8h]; this
0x1800463d0  xor     edi, edi
0x1800463d2  test    eax, eax
0x1800463d4  jns     short loc_1800463EA
0x1800463d6  mov     r9d, eax; char *
0x1800463d9  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800463e0  mov     edx, 228h; void *
0x1800463e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800463ea  mov     [rsp+5D8h+var_538], rdi
0x1800463f2  mov     rax, [r14]
0x1800463f5  mov     rbx, [rax]
0x1800463f8  lea     rcx, [rsp+5D8h+var_538]
0x180046400  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046405  lea     r8, [rsp+5D8h+var_538]
0x18004640d  lea     rdx, _GUID_f0770655_4b63_4e3a_9107_4e687841923a
0x180046414  mov     rcx, r14
0x180046417  mov     rax, rbx
0x18004641a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004641f  mov     rcx, [rsp+5D8h]; this
0x180046427  test    eax, eax
0x180046429  jns     short loc_18004643F
0x18004642b  mov     r9d, eax; char *
0x18004642e  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046435  mov     edx, 22Ch; void *
0x18004643a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004643f  mov     rcx, [rsp+5D8h+var_538]
0x180046447  mov     rax, [rcx]
0x18004644a  lea     rdx, [rsp+5D8h+var_548]
0x180046452  mov     rax, [rax+30h]
0x180046456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004645b  mov     rcx, [rsp+5D8h]; this
0x180046463  test    eax, eax
0x180046465  jns     short loc_18004647B
0x180046467  mov     r9d, eax; char *
0x18004646a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046471  mov     edx, 22Dh; void *
0x180046476  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004647b  mov     [rsp+5D8h+var_540], rdi
0x180046483  lea     rdx, [rsp+5D8h+var_540]
0x18004648b  lea     rcx, [rsp+5D8h+var_510]
0x180046493  call    ??$As@UILauncherUIOptionsInternal@Private@System@Windows@@@?$ComPtr@UILauncherUIOptions@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILauncherUIOptionsInternal@Private@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::ILauncherUIOptions>::As<Windows::System::Private::ILauncherUIOptionsInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Private::ILauncherUIOptionsInternal>>)
0x180046498  test    eax, eax
0x18004649a  js      short loc_1800464D8
0x18004649c  mov     rcx, [rsp+5D8h+var_540]
0x1800464a4  mov     rax, [rcx]
0x1800464a7  lea     rdx, [rsp+5D8h+var_547]
0x1800464af  mov     rax, [rax+50h]
0x1800464b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464b8  mov     rcx, [rsp+5D8h]; this
0x1800464c0  test    eax, eax
0x1800464c2  jns     short loc_1800464D8
0x1800464c4  mov     r9d, eax; char *
0x1800464c7  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x1800464ce  mov     edx, 234h; void *
0x1800464d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800464d8  mov     [rsp+5D8h+var_518], rdi
0x1800464e0  mov     rax, [r14]
0x1800464e3  mov     rbx, [rax]
0x1800464e6  lea     rcx, [rsp+5D8h+var_518]
0x1800464ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800464f3  lea     r8, [rsp+5D8h+var_518]
0x1800464fb  lea     rdx, _GUID_8a9b29f1_7ca7_49de_9bd3_3c5b7184f616
0x180046502  mov     rcx, r14
0x180046505  mov     rax, rbx
0x180046508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004650d  mov     rcx, [rsp+5D8h]; this
0x180046515  test    eax, eax
0x180046517  jns     short loc_18004652D
0x180046519  mov     r9d, eax; char *
0x18004651c  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046523  mov     edx, 239h; void *
0x180046528  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004652d  mov     rcx, [rsp+5D8h+var_518]
0x180046535  mov     rax, [rcx]
0x180046538  lea     rdx, [rsp+5D8h+var_508]
0x180046540  mov     rax, [rax+30h]
0x180046544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046549  mov     rcx, [rsp+5D8h]; this
0x180046551  test    eax, eax
0x180046553  jns     short loc_180046569
0x180046555  mov     r9d, eax; char *
0x180046558  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x18004655f  mov     edx, 23Ah; void *
0x180046564  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046569  mov     rcx, r14
0x18004656c  call    GetOwnerWindowId
0x180046571  mov     ebx, eax
0x180046573  mov     ecx, eax
0x180046575  call    ?ValidateUIThreadRequirements@@YAXUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; ValidateUIThreadRequirements(Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x18004657a  mov     [rsp+5D8h+var_528], ebx
0x180046581  lea     rcx, [rsp+5D8h+var_518]
0x180046589  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004658e  nop
0x18004658f  lea     rcx, [rsp+5D8h+var_540]
0x180046597  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004659c  nop
0x18004659d  lea     rcx, [rsp+5D8h+var_538]
0x1800465a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800465aa  nop
0x1800465ab  lea     rcx, [rsp+5D8h+var_530]
0x1800465b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800465b8  lea     rcx, [rsp+5D8h+var_4D0]
0x1800465c0  call    ?GetLauncherService@@YA?AV?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@XZ; GetLauncherService(void)
0x1800465c5  nop
0x1800465c6  lea     rcx, [rsp+5D8h+var_4F0]
0x1800465ce  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x1800465d3  nop
0x1800465d4  mov     rsi, [rsp+5D8h+var_4F0]
0x1800465dc  lea     rcx, [rsi+8]; newString
0x1800465e0  lea     rdx, [rsp+5D8h+var_4F8]; HSTRING *
0x1800465e8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800465ed  mov     rcx, [rsp+5D8h]; this
0x1800465f5  test    eax, eax
0x1800465f7  jns     short loc_18004660E
0x1800465f9  mov     r9d, eax; char *
0x1800465fc  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046603  mov     edx, 248h; void *
0x180046608  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004660d  nop
0x18004660e  xor     ecx, ecx; string
0x180046610  call    cs:__imp_WindowsDeleteString
0x180046616  mov     [rsp+5D8h+var_518], rdi
0x18004661e  lea     rcx, [rsp+5D8h+var_518]; this
0x180046626  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x18004662b  mov     rcx, [rsp+5D8h]; this
0x180046633  test    eax, eax
0x180046635  jns     short loc_18004664B
0x180046637  mov     r9d, eax; char *
0x18004663a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046641  mov     edx, 24Ch; void *
0x180046646  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004664b  lea     rcx, [rsp+5D8h+var_4F8]
0x180046653  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180046658  nop
0x180046659  mov     rbx, [rsp+5D8h+var_518]
0x180046661  mov     [rsp+5D8h+var_540], rbx
0x180046669  mov     r14, [rsp+5D8h+var_4F8]
0x180046671  lea     rcx, [r14+8]; newString
0x180046675  lea     rdx, [rsp+5D8h+var_540]; HSTRING *
0x18004667d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180046682  mov     rcx, [rsp+5D8h]; this
0x18004668a  test    eax, eax
0x18004668c  jns     short loc_1800466A2
0x18004668e  mov     r9d, eax; char *
0x180046691  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046698  mov     edx, 24Fh; void *
0x18004669d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800466a2  mov     [rsp+5D8h+var_538], r12
0x1800466aa  lea     rcx, [rsp+5D8h+var_538]
0x1800466b2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800466b7  nop
0x1800466b8  mov     [rsp+5D8h+var_530], rdi
0x1800466c0  lea     rcx, [rsp+5D8h+var_530]
0x1800466c8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800466cd  nop
0x1800466ce  mov     rax, [rsp+5D8h+arg_28]
0x1800466d6  mov     [rsp+5D8h+var_540], rax
0x1800466de  lea     rcx, [rsp+5D8h+var_540]
0x1800466e6  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800466eb  nop
0x1800466ec  mov     ecx, 20h ; ' '; Size
0x1800466f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800466f6  mov     r12, rax
0x1800466f9  mov     eax, 1
0x1800466fe  mov     [r12+8], eax
0x180046703  mov     [r12+0Ch], eax
0x180046708  lea     rax, ??_7?$_Ref_count_obj2@VLaunchUriAsyncOpState@?2???$_LaunchUriInternalAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@5@PEAUILauncherOptions@95@PEAUIPropertySet@Collections@45@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@_N@45@@Z@@std@@6B@; const std::_Ref_count_obj2<`Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)'::`3'::LaunchUriAsyncOpState>::`vftable'
0x18004670f  mov     [r12], rax
0x180046713  lea     rdi, [r12+10h]
0x180046718  mov     qword ptr [r12+18h], 0
0x180046721  mov     qword ptr [rdi], 0
0x180046728  lea     rcx, [rdi+8]; SRWLock
0x18004672c  call    cs:__imp_InitializeSRWLock
0x180046732  mov     [rsp+5D8h+var_4C8], rdi
0x18004673a  mov     [rsp+5D8h+var_4C0], r12
0x180046742  lea     rdx, [rsp+5D8h+var_358]
0x18004674a  lea     rcx, [rsp+5D8h+var_4A8]
0x180046752  call    ?Split@LaunchUriAsync@LauncherClientProvider@@QEAA?AV12@XZ; LauncherClientProvider::LaunchUriAsync::Split(void)
0x180046757  nop
0x180046758  lea     rax, [rsp+5D8h+var_4C8]
0x180046760  mov     [rsp+5D8h+var_550], rax
0x180046768  lea     rax, [rsp+5D8h+var_358]
0x180046770  mov     [rsp+5D8h+var_558], rax
0x180046778  lea     rax, [rsp+5D8h+var_4F8]
  ... truncated ...
```
