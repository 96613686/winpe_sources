# Launcher::_LaunchUriInternalAsync<Windows::System::LaunchUriResult *,Windows::Internal::CMarshaledInterfaceResult<Windows::System::ILaunchUriResult>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *> * *)

- ea: `0x1800469b4`
- end: `0x1800471d7`
- name: `??$_LaunchUriInternalAsync@PEAVLaunchUriResult@System@Windows@@V?$CMarshaledInterfaceResult@UILaunchUriResult@System@Windows@@@Internal@3@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@3@PEAUILauncherOptions@73@PEAUIPropertySet@Collections@23@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@23@@Z`
- size: `2083`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int, HSTRING, char, HSTRING string, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800452f0`

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
- `0x1800469b4`
- `0x1800471e0`
- `0x18004720c`
- `0x180047254`
- `0x180047570`
- `0x1800475d0`
- `0x180047744`
- `0x1800477e4`
- `0x180047890`
- `0x1800596d8`
- `0x18006e350`
- `0x18008a030`
- `0x18008df9c`
- `0x18008efac`
- `0x1800907c8`
- `0x18009386c`
- `0x1800993dc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180046f50`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180046f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046a0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046a0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047136`

## string_xrefs

- `0x180047082`: `Windows.Foundation.IAsyncOperation`1<Windows.System.LaunchUriResult>`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Launcher::_LaunchUriInternalAsync<Windows::System::LaunchUriResult *,Windows::Internal::CMarshaledInterfaceResult<Windows::System::ILaunchUriResult>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        int a5,
        HSTRING a6,
        char a7,
        HSTRING string,
        __int64 a9)
{
  int v11; // r13d
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
  int v41; // r9d
  int v42; // edi
  int v43; // [rsp+20h] [rbp-5A8h]
  int v44; // [rsp+20h] [rbp-5A8h]
  char v45; // [rsp+90h] [rbp-538h] BYREF
  _BYTE v46[7]; // [rsp+91h] [rbp-537h] BYREF
  int v47; // [rsp+98h] [rbp-530h] BYREF
  HSTRING v48; // [rsp+A0h] [rbp-528h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-520h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-518h] BYREF
  HSTRING v51; // [rsp+B8h] [rbp-510h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-508h] BYREF
  int v53; // [rsp+C8h] [rbp-500h] BYREF
  unsigned int v54; // [rsp+CCh] [rbp-4FCh] BYREF
  __int64 v55; // [rsp+D0h] [rbp-4F8h] BYREF
  HSTRING v56; // [rsp+D8h] [rbp-4F0h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-4E8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+E8h] [rbp-4E0h] BYREF
  int v59; // [rsp+F0h] [rbp-4D8h] BYREF
  __int64 v60; // [rsp+F4h] [rbp-4D4h]
  _BYTE v61[8]; // [rsp+100h] [rbp-4C8h] BYREF
  _QWORD v62[3]; // [rsp+108h] [rbp-4C0h] BYREF
  _BYTE v63[336]; // [rsp+120h] [rbp-4A8h] BYREF
  _BYTE v64[336]; // [rsp+270h] [rbp-358h] BYREF
  _BYTE v65[464]; // [rsp+3C0h] [rbp-208h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+0h]

  v56 = string;
  v11 = a9;
  v47 = 3;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  LauncherClientProvider::LaunchUriAsync::Start<unsigned short const *>((LauncherClientProvider::LaunchUriAsync *)v63);
  v62[2] = 0;
  v55 = 0;
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&StringRawBuffer);
  v12 = (HSTRING *)StringRawBuffer;
  if ( !StringRawBuffer )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x214,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x8007000ELL,
      v43);
  v52 = 0;
  v54 = 0;
  v46[0] = 0;
  v45 = 0;
  v53 = 0;
  if ( a4 )
  {
    FallbackUri = GetFallbackUri(&v57, a4);
    Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(&v55, FallbackUri);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
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
        v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      if ( v12 )
        (*((void (__fastcall **)(HSTRING *))*v12 + 2))(v12);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v63);
      return v16;
    }
    v50 = 0;
    v18 = **a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v19 = v18(a4, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v50);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v19,
        v43);
    v20 = v50;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 48LL);
    WindowsDeleteString(v12[1]);
    v12[1] = 0;
    v22 = v21(v20, v12 + 1);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v22,
        v43);
    v49 = 0;
    v23 = **a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v24 = v23(a4, &GUID_f0770655_4b63_4e3a_9107_4e687841923a, &v49);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v24,
        v43);
    v25 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v49 + 48LL))(v49, &v45);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v25,
        v43);
    v48 = 0;
    if ( (int)Microsoft::WRL::ComPtr<Windows::System::ILauncherUIOptions>::As<Windows::System::Private::ILauncherUIOptionsInternal>(
                &v52,
                &v48) >= 0 )
    {
      v26 = (*(__int64 (__fastcall **)(HSTRING, _BYTE *))(*(_QWORD *)v48 + 80LL))(v48, v46);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)v26,
          v43);
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
        v43);
    v29 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)v51 + 48LL))(v51, &v53);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v29,
        v43);
    OwnerWindowId = GetOwnerWindowId(a4);
    ValidateUIThreadRequirements(OwnerWindowId);
    v54 = OwnerWindowId;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  }
  GetLauncherService(v61);
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v57);
  v31 = v57;
  v32 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(v57 + 8), &v56);
  if ( v32 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v32,
      v43);
  WindowsDeleteString(0);
  v51 = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v51, v33);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      v43);
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v56);
  v35 = v51;
  v48 = v51;
  v36 = v56;
  v37 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v56 + 1, &v48);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v37,
      v43);
  v49 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v49);
  v50 = 0;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v50);
  v48 = a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
  v38 = (char *)operator new(0x20u);
  *((_DWORD *)v38 + 2) = 1;
  *((_DWORD *)v38 + 3) = 1;
  *(_QWORD *)v38 = ___7___Ref_count_obj2_VLaunchUriAsyncOpState__2_____LaunchUriInternalAsync__NV__CBasicResult_E_0A__Internal_Windows___Launcher__AEAAJPEAUIUriRuntimeClass_Foundation_Windows__W4LaunchType_Launch_Internal_System_5_PEAUILauncherOptions_95_PEAUIPropertySet_Collections_45_3_KPEAUHSTRING____PEAPEAU__IAsyncOperation__N_45__Z__std__6B_;
  *((_QWORD *)v38 + 3) = 0;
  *((_QWORD *)v38 + 2) = 0;
  InitializeSRWLock((PSRWLOCK)v38 + 3);
  v62[0] = v38 + 16;
  v62[1] = v38;
  LauncherClientProvider::LaunchUriAsync::Split(v63, v64);
  v39 = _lambda_9d4e42fefa12b04ae325b222a27027ce_::_lambda_9d4e42fefa12b04ae325b222a27027ce_(
          (unsigned int)v65,
          (unsigned int)v61,
          (unsigned int)&v54,
          (unsigned int)&v49,
          (__int64)&v47,
          (__int64)&v52,
          (__int64)&StringRawBuffer,
          (__int64)&v50,
          (__int64)&v48,
          (__int64)&v55,
          (__int64)&a7,
          (__int64)v46,
          (__int64)&v45,
          (__int64)&v57,
          (__int64)&v53,
          (__int64)&v56,
          (__int64)v64,
          (__int64)v62);
  v59 = 3;
  v60 = 128;
  v40 = Windows::Internal::MakeOpLambda<1,Windows::Internal::CMarshaledInterfaceResult<Windows::System::ILaunchUriResult>,_lambda_9d4e42fefa12b04ae325b222a27027ce_,>(v39);
  v42 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::LaunchUriResult *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::System::ILaunchUriResult>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
          v11,
          (unsigned int)&v59,
          (unsigned int)L"Windows.Foundation.IAsyncOperation`1<Windows.System.LaunchUriResult>",
          v41,
          v40);
  _lambda_cf6083327d3aaca30ba38e0587da4456_::~_lambda_cf6083327d3aaca30ba38e0587da4456_((_lambda_cf6083327d3aaca30ba38e0587da4456_ *)v65);
  wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v63,
    0);
  if ( v42 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)(unsigned int)v42,
      v44);
  LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v64);
  if ( v38 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  if ( v36 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
  WindowsDeleteString(v35);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v61);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  if ( v12 )
    (*((void (__fastcall **)(HSTRING *))*v12 + 2))(v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync((LauncherClientProvider::LaunchUriAsync *)v63);
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x1800469b4  mov     [rsp+arg_0], rbx
0x1800469b9  mov     [rsp+arg_8], rsi
0x1800469be  push    rdi
0x1800469bf  push    r12
0x1800469c1  push    r13
0x1800469c3  push    r14
0x1800469c5  push    r15
0x1800469c7  sub     rsp, 5A0h
0x1800469ce  mov     rax, cs:__security_cookie
0x1800469d5  xor     rax, rsp
0x1800469d8  mov     [rsp+5C8h+var_38], rax
0x1800469e0  mov     r14, r9
0x1800469e3  mov     r12, rdx
0x1800469e6  mov     rcx, [rsp+5C8h+string]; string
0x1800469ee  mov     [rsp+5C8h+var_4F0], rcx
0x1800469f6  mov     r13, [rsp+5C8h+arg_40]
0x1800469fe  xor     edi, edi
0x180046a00  mov     [rsp+5C8h+var_530], 3
0x180046a0b  xor     edx, edx; length
0x180046a0d  call    cs:__imp_WindowsGetStringRawBuffer
0x180046a13  mov     [rsp+5C8h+var_4E0], rax
0x180046a1b  lea     rdx, [rsp+5C8h+var_4E0]
0x180046a23  lea     rcx, [rsp+5C8h+var_4A8]; this
0x180046a2b  call    ??$Start@PEBG@LaunchUriAsync@LauncherClientProvider@@SA?AV01@$$QEAPEBG@Z; LauncherClientProvider::LaunchUriAsync::Start<ushort const *>(ushort const * &&)
0x180046a30  nop
0x180046a31  mov     [rsp+5C8h+var_4B0], rdi
0x180046a39  mov     [rsp+5C8h+var_4F8], rdi
0x180046a41  lea     rcx, [rsp+5C8h+var_4E0]
0x180046a49  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180046a4e  nop
0x180046a4f  mov     rcx, [rsp+5C8h]; this
0x180046a57  mov     r15, [rsp+5C8h+var_4E0]
0x180046a5f  test    r15, r15
0x180046a62  jnz     short loc_180046A7B
0x180046a64  mov     r9d, 8007000Eh; char *
0x180046a6a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046a71  mov     edx, 214h; void *
0x180046a76  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046a7b  mov     [rsp+5C8h+var_508], rdi
0x180046a83  mov     [rsp+5C8h+var_4FC], edi
0x180046a8a  mov     [rsp+5C8h+var_537], dil
0x180046a92  mov     [rsp+5C8h+var_538], dil
0x180046a9a  mov     [rsp+5C8h+var_500], edi
0x180046aa1  test    r14, r14
0x180046aa4  jz      loc_180046DDC
0x180046aaa  mov     rdx, r14
0x180046aad  lea     rcx, [rsp+5C8h+var_4E8]
0x180046ab5  call    ?GetFallbackUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherOptions@System@Windows@@@Z; GetFallbackUri(Windows::System::ILauncherOptions *)
0x180046aba  mov     rdx, rax
0x180046abd  lea     rcx, [rsp+5C8h+var_4F8]
0x180046ac5  call    ??4?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService>::operator=(Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::ILauncherService> &&)
0x180046aca  lea     rcx, [rsp+5C8h+var_4E8]
0x180046ad2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046ad7  mov     rax, [r14]
0x180046ada  mov     rbx, [rax+50h]
0x180046ade  lea     rcx, [rsp+5C8h+var_508]
0x180046ae6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046aeb  lea     rdx, [rsp+5C8h+var_508]
0x180046af3  mov     rcx, r14
0x180046af6  mov     rax, rbx
0x180046af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046afe  mov     ebx, eax
0x180046b00  test    eax, eax
0x180046b02  jns     short loc_180046B66
0x180046b04  mov     rcx, [rsp+5C8h]; this
0x180046b0c  mov     r9d, eax; char *
0x180046b0f  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046b16  mov     edx, 223h; void *
0x180046b1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046b20  nop
0x180046b21  lea     rcx, [rsp+5C8h+var_508]
0x180046b29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046b2e  nop
0x180046b2f  test    r15, r15
0x180046b32  jz      short loc_180046B44
0x180046b34  mov     rax, [r15]
0x180046b37  mov     rcx, r15
0x180046b3a  mov     rax, [rax+10h]
0x180046b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b43  nop
0x180046b44  lea     rcx, [rsp+5C8h+var_4F8]
0x180046b4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046b51  nop
0x180046b52  lea     rcx, [rsp+5C8h+var_4A8]; this
0x180046b5a  call    ??1LaunchUriAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::LaunchUriAsync::~LaunchUriAsync(void)
0x180046b5f  mov     eax, ebx
0x180046b61  jmp     loc_1800471A9
0x180046b66  mov     [rsp+5C8h+var_518], rdi
0x180046b6e  mov     rax, [r14]
0x180046b71  mov     rbx, [rax]
0x180046b74  lea     rcx, [rsp+5C8h+var_518]
0x180046b7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046b81  lea     r8, [rsp+5C8h+var_518]
0x180046b89  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x180046b90  mov     rcx, r14
0x180046b93  mov     rax, rbx
0x180046b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b9b  mov     rcx, [rsp+5C8h]; this
0x180046ba3  test    eax, eax
0x180046ba5  jns     short loc_180046BBB
0x180046ba7  mov     r9d, eax; char *
0x180046baa  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046bb1  mov     edx, 227h; void *
0x180046bb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046bbb  mov     rsi, [rsp+5C8h+var_518]
0x180046bc3  mov     rax, [rsi]
0x180046bc6  mov     rdi, [rax+30h]
0x180046bca  lea     rbx, [r15+8]
0x180046bce  mov     rcx, [rbx]; string
0x180046bd1  call    cs:__imp_WindowsDeleteString
0x180046bd7  mov     qword ptr [rbx], 0
0x180046bde  mov     rdx, rbx
0x180046be1  mov     rcx, rsi
0x180046be4  mov     rax, rdi
0x180046be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bec  mov     rcx, [rsp+5C8h]; this
0x180046bf4  xor     edi, edi
0x180046bf6  test    eax, eax
0x180046bf8  jns     short loc_180046C0E
0x180046bfa  mov     r9d, eax; char *
0x180046bfd  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046c04  mov     edx, 228h; void *
0x180046c09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046c0e  mov     [rsp+5C8h+var_520], rdi
0x180046c16  mov     rax, [r14]
0x180046c19  mov     rbx, [rax]
0x180046c1c  lea     rcx, [rsp+5C8h+var_520]
0x180046c24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046c29  lea     r8, [rsp+5C8h+var_520]
0x180046c31  lea     rdx, _GUID_f0770655_4b63_4e3a_9107_4e687841923a
0x180046c38  mov     rcx, r14
0x180046c3b  mov     rax, rbx
0x180046c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c43  mov     rcx, [rsp+5C8h]; this
0x180046c4b  test    eax, eax
0x180046c4d  jns     short loc_180046C63
0x180046c4f  mov     r9d, eax; char *
0x180046c52  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046c59  mov     edx, 22Ch; void *
0x180046c5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046c63  mov     rcx, [rsp+5C8h+var_520]
0x180046c6b  mov     rax, [rcx]
0x180046c6e  lea     rdx, [rsp+5C8h+var_538]
0x180046c76  mov     rax, [rax+30h]
0x180046c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c7f  mov     rcx, [rsp+5C8h]; this
0x180046c87  test    eax, eax
0x180046c89  jns     short loc_180046C9F
0x180046c8b  mov     r9d, eax; char *
0x180046c8e  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046c95  mov     edx, 22Dh; void *
0x180046c9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046c9f  mov     [rsp+5C8h+var_528], rdi
0x180046ca7  lea     rdx, [rsp+5C8h+var_528]
0x180046caf  lea     rcx, [rsp+5C8h+var_508]
0x180046cb7  call    ??$As@UILauncherUIOptionsInternal@Private@System@Windows@@@?$ComPtr@UILauncherUIOptions@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILauncherUIOptionsInternal@Private@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::ILauncherUIOptions>::As<Windows::System::Private::ILauncherUIOptionsInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Private::ILauncherUIOptionsInternal>>)
0x180046cbc  test    eax, eax
0x180046cbe  js      short loc_180046CFC
0x180046cc0  mov     rcx, [rsp+5C8h+var_528]
0x180046cc8  mov     rax, [rcx]
0x180046ccb  lea     rdx, [rsp+5C8h+var_537]
0x180046cd3  mov     rax, [rax+50h]
0x180046cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cdc  mov     rcx, [rsp+5C8h]; this
0x180046ce4  test    eax, eax
0x180046ce6  jns     short loc_180046CFC
0x180046ce8  mov     r9d, eax; char *
0x180046ceb  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046cf2  mov     edx, 234h; void *
0x180046cf7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046cfc  mov     [rsp+5C8h+var_510], rdi
0x180046d04  mov     rax, [r14]
0x180046d07  mov     rbx, [rax]
0x180046d0a  lea     rcx, [rsp+5C8h+var_510]
0x180046d12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046d17  lea     r8, [rsp+5C8h+var_510]
0x180046d1f  lea     rdx, _GUID_8a9b29f1_7ca7_49de_9bd3_3c5b7184f616
0x180046d26  mov     rcx, r14
0x180046d29  mov     rax, rbx
0x180046d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d31  mov     rcx, [rsp+5C8h]; this
0x180046d39  test    eax, eax
0x180046d3b  jns     short loc_180046D51
0x180046d3d  mov     r9d, eax; char *
0x180046d40  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046d47  mov     edx, 239h; void *
0x180046d4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046d51  mov     rcx, [rsp+5C8h+var_510]
0x180046d59  mov     rax, [rcx]
0x180046d5c  lea     rdx, [rsp+5C8h+var_500]
0x180046d64  mov     rax, [rax+30h]
0x180046d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d6d  mov     rcx, [rsp+5C8h]; this
0x180046d75  test    eax, eax
0x180046d77  jns     short loc_180046D8D
0x180046d79  mov     r9d, eax; char *
0x180046d7c  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046d83  mov     edx, 23Ah; void *
0x180046d88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046d8d  mov     rcx, r14
0x180046d90  call    GetOwnerWindowId
0x180046d95  mov     ebx, eax
0x180046d97  mov     ecx, eax
0x180046d99  call    ?ValidateUIThreadRequirements@@YAXUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; ValidateUIThreadRequirements(Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180046d9e  mov     [rsp+5C8h+var_4FC], ebx
0x180046da5  lea     rcx, [rsp+5C8h+var_510]
0x180046dad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046db2  nop
0x180046db3  lea     rcx, [rsp+5C8h+var_528]
0x180046dbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046dc0  nop
0x180046dc1  lea     rcx, [rsp+5C8h+var_520]
0x180046dc9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046dce  nop
0x180046dcf  lea     rcx, [rsp+5C8h+var_518]
0x180046dd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046ddc  lea     rcx, [rsp+5C8h+var_4C8]
0x180046de4  call    ?GetLauncherService@@YA?AV?$ComPtr@UILauncherService@Launch@Internal@System@Windows@@@WRL@Microsoft@@XZ; GetLauncherService(void)
0x180046de9  nop
0x180046dea  lea     rcx, [rsp+5C8h+var_4E8]
0x180046df2  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180046df7  nop
0x180046df8  mov     rsi, [rsp+5C8h+var_4E8]
0x180046e00  lea     rcx, [rsi+8]; newString
0x180046e04  lea     rdx, [rsp+5C8h+var_4F0]; HSTRING *
0x180046e0c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180046e11  mov     rcx, [rsp+5C8h]; this
0x180046e19  test    eax, eax
0x180046e1b  jns     short loc_180046E32
0x180046e1d  mov     r9d, eax; char *
0x180046e20  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046e27  mov     edx, 248h; void *
0x180046e2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046e31  nop
0x180046e32  xor     ecx, ecx; string
0x180046e34  call    cs:__imp_WindowsDeleteString
0x180046e3a  mov     [rsp+5C8h+var_510], rdi
0x180046e42  lea     rcx, [rsp+5C8h+var_510]; this
0x180046e4a  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x180046e4f  mov     rcx, [rsp+5C8h]; this
0x180046e57  test    eax, eax
0x180046e59  jns     short loc_180046E6F
0x180046e5b  mov     r9d, eax; char *
0x180046e5e  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046e65  mov     edx, 24Ch; void *
0x180046e6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046e6f  lea     rcx, [rsp+5C8h+var_4F0]
0x180046e77  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180046e7c  nop
0x180046e7d  mov     rbx, [rsp+5C8h+var_510]
0x180046e85  mov     [rsp+5C8h+var_528], rbx
0x180046e8d  mov     r14, [rsp+5C8h+var_4F0]
0x180046e95  lea     rcx, [r14+8]; newString
0x180046e99  lea     rdx, [rsp+5C8h+var_528]; HSTRING *
0x180046ea1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180046ea6  mov     rcx, [rsp+5C8h]; this
0x180046eae  test    eax, eax
0x180046eb0  jns     short loc_180046EC6
0x180046eb2  mov     r9d, eax; char *
0x180046eb5  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180046ebc  mov     edx, 24Fh; void *
0x180046ec1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046ec6  mov     [rsp+5C8h+var_520], r12
0x180046ece  lea     rcx, [rsp+5C8h+var_520]
0x180046ed6  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180046edb  nop
0x180046edc  mov     [rsp+5C8h+var_518], rdi
0x180046ee4  lea     rcx, [rsp+5C8h+var_518]
0x180046eec  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180046ef1  nop
0x180046ef2  mov     rax, [rsp+5C8h+arg_28]
0x180046efa  mov     [rsp+5C8h+var_528], rax
0x180046f02  lea     rcx, [rsp+5C8h+var_528]
0x180046f0a  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180046f0f  nop
0x180046f10  mov     ecx, 20h ; ' '; Size
0x180046f15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046f1a  mov     r12, rax
0x180046f1d  mov     eax, 1
0x180046f22  mov     [r12+8], eax
0x180046f27  mov     [r12+0Ch], eax
0x180046f2c  lea     rax, ??_7?$_Ref_count_obj2@VLaunchUriAsyncOpState@?2???$_LaunchUriInternalAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@5@PEAUILauncherOptions@95@PEAUIPropertySet@Collections@45@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@_N@45@@Z@@std@@6B@; const std::_Ref_count_obj2<`Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)'::`3'::LaunchUriAsyncOpState>::`vftable'
0x180046f33  mov     [r12], rax
0x180046f37  lea     rdi, [r12+10h]
0x180046f3c  mov     qword ptr [r12+18h], 0
0x180046f45  mov     qword ptr [rdi], 0
0x180046f4c  lea     rcx, [rdi+8]; SRWLock
0x180046f50  call    cs:__imp_InitializeSRWLock
0x180046f56  mov     [rsp+5C8h+var_4C0], rdi
0x180046f5e  mov     [rsp+5C8h+var_4B8], r12
0x180046f66  lea     rdx, [rsp+5C8h+var_358]
0x180046f6e  lea     rcx, [rsp+5C8h+var_4A8]
0x180046f76  call    ?Split@LaunchUriAsync@LauncherClientProvider@@QEAA?AV12@XZ; LauncherClientProvider::LaunchUriAsync::Split(void)
0x180046f7b  nop
0x180046f7c  lea     rax, [rsp+5C8h+var_4C0]
0x180046f84  mov     [rsp+5C8h+var_540], rax
0x180046f8c  lea     rax, [rsp+5C8h+var_358]
0x180046f94  mov     [rsp+5C8h+var_548], rax
0x180046f9c  lea     rax, [rsp+5C8h+var_4F0]
0x180046fa4  mov     [rsp+5C8h+var_550], rax
  ... truncated ...
```
