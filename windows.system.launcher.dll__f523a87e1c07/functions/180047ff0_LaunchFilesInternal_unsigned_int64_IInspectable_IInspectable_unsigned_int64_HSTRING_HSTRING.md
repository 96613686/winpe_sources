# LaunchFilesInternal(unsigned __int64,IInspectable *,IInspectable *,unsigned __int64,HSTRING__ *,HSTRING__ *)

- ea: `0x180047ff0`
- end: `0x18004859e`
- name: `?LaunchFilesInternal@@YAX_KPEAUIInspectable@@1_KPEAUHSTRING__@@3@Z`
- size: `1454`
- prototype: `void __fastcall(unsigned __int64, struct IInspectable *, struct IInspectable *, unsigned __int64, HSTRING string, HSTRING)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b7680`
- `0x1800b76d0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18002cec0`
- `0x180047254`
- `0x180047ff0`
- `0x1800485a4`
- `0x1800486d8`
- `0x180048790`
- `0x180048848`
- `0x1800488f4`
- `0x180048ce4`
- `0x180048d94`
- `0x18004e550`
- `0x1800596d8`
- `0x180075ce4`
- `0x180079650`
- `0x18008a030`
- `0x1800ae588`
- `0x1800b201c`
- `0x1800b58e4`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048048`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048048`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004842f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004842f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048561`

## string_xrefs

- `0x180048097`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800480dc`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18004810a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall LaunchFilesInternal(
        __int64 a1,
        struct IInspectable *a2,
        struct IInspectable *a3,
        __int64 a4,
        HSTRING string,
        HSTRING a6)
{
  const unsigned __int16 *StringRawBuffer; // rbx
  __int64 v10; // rdx
  UserAwareCallerIdentity *v11; // rcx
  void **v12; // r8
  int v13; // eax
  int CallerPackageFamilyName; // eax
  HSTRING *v15; // rdx
  int CallerAumidOrProcessName; // eax
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v18; // eax
  int v19; // eax
  HRESULT (__stdcall *v20)(IInspectable *, const IID *const, void **); // rbx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // r15
  __int64 v29; // r14
  __int64 v30; // rbx
  __int64 v31; // rdi
  struct Windows::Storage::IStorageItem *v32; // rsi
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  char v35; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v36[7]; // [rsp+61h] [rbp-9Fh] BYREF
  struct Windows::Storage::IStorageItem *v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Storage::IStorageItem *v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v43; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v44; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v45; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v46; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v47; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v48; // [rsp+C0h] [rbp-40h] BYREF
  int v49[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h] BYREF
  struct Windows::Storage::IStorageItem *v51; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v52; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v53[40]; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v54; // [rsp+110h] [rbp+10h]
  HSTRING_HEADER hstringHeader; // [rsp+118h] [rbp+18h] BYREF
  __int64 v56; // [rsp+130h] [rbp+30h]
  HSTRING_HEADER v57; // [rsp+138h] [rbp+38h] BYREF
  __int64 v58; // [rsp+150h] [rbp+50h]
  HSTRING_HEADER v59; // [rsp+158h] [rbp+58h] BYREF
  __int64 v60; // [rsp+170h] [rbp+70h]
  _QWORD v61[42]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v41 = a4;
  v52 = a1;
  v47 = string;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v61);
  v61[0] = &LauncherServiceProvider::LaunchFiles::`vftable';
  LauncherServiceProvider::LaunchFiles::StartActivity((LauncherServiceProvider::LaunchFiles *)v61, StringRawBuffer);
  v13 = VerifyCaller(v11, v10, v12);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v13,
      v33);
  WindowsDeleteString(0);
  v45 = 0;
  CallerPackageFamilyName = GetCallerPackageFamilyName(&v45);
  if ( CallerPackageFamilyName == -2147024891 || CallerPackageFamilyName == -2147009196 )
    CallerPackageFamilyName = 0;
  if ( CallerPackageFamilyName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)CallerPackageFamilyName,
      v33);
  WindowsDeleteString(0);
  v44 = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v44, v15);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      v33);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x80070057LL,
      v33);
  v40 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v18 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct Windows::Storage::IStorageItem **))QueryInterface)(
          a2,
          &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
          &v40);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v18,
      v33);
  if ( !v40 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x8000FFFFLL,
      v33);
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v19 = CreateValidatedStorageItem(v40, v45, &v37);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v19,
      v33);
  v38 = 0;
  if ( a3 )
  {
    v20 = a3->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v21 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v20)(
            a3,
            &GUID_52fda447_2baa_412c_b29f_d4b1778efa1e,
            &v38);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v21,
        v33);
    if ( !v38 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x8000FFFFLL,
        v33);
  }
  v35 = 0;
  v22 = (*(__int64 (__fastcall **)(struct Windows::Storage::IStorageItem *, __int64, char *))(*(_QWORD *)v37 + 120LL))(
          v37,
          1,
          &v35);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v22,
      v33);
  if ( !v35 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x8000FFFFLL,
      v33);
  CallerInformation::Capture(v53, a1, v41);
  v39 = 0;
  if ( a6 )
  {
    v41 = 0;
    v23 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<Windows::Storage::IStorageFile>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v37,
            (__int64)&v41);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v23,
        v33);
    GetFileExtensionStringForAppResolverFromStorageFile(&v43, v41);
    v42 = 0;
    v36[0] = 0;
    v48 = 0;
    *(_QWORD *)v49 = 0;
    v50 = v38;
    v51 = v37;
    v46 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v24 = Microsoft::WRL::Details::MakeAndInitialize<CTargetAppResolver,ILauncherTargetResolver,LAUNCH_PARAMETERS const * &,IUnknown * &,Windows::Storage::Search::IStorageFileQueryResult * &,HSTRING__ * &,HSTRING__ * &,CallerInformation const &,bool const &,HSTRING__ * &>(
            (unsigned int)&v42,
            (unsigned int)&v46,
            (unsigned int)&v51,
            (unsigned int)&v50,
            (__int64)v49,
            (__int64)&v48,
            (struct CallerInformation *)v53,
            (__int64)v36,
            (__int64)&v47);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v24,
        v34);
    v25 = v42;
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v42 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v27 = v26(v25, v43, a6, &v39);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v27,
        v34);
    if ( !v39 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80070483LL,
        v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    WindowsDeleteString(v43);
    v43 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  }
  v46 = WindowsGetStringRawBuffer(v44, 0);
  LauncherServiceProvider::LaunchFiles::LaunchFileRequest<unsigned __int64 const &,unsigned short const *>(
    v61,
    &v52,
    &v46);
  v28 = v39;
  v56 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &LocaleName, 1u, 0);
  v29 = v56;
  v58 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v57, &LocaleName, 1u, 0);
  v30 = v58;
  v31 = v38;
  v32 = v37;
  v60 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v59, &LocaleName, 1u, 0);
  LaunchTargetApp(v53, v60, v32, v31, v30, v29, 0, 0, 0, v28, string);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v61,
    0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  WindowsDeleteString(v54);
  v54 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  WindowsDeleteString(v44);
  WindowsDeleteString(v45);
  LauncherServiceProvider::LaunchFiles::~LaunchFiles((LauncherServiceProvider::LaunchFiles *)v61);
}

```

## disassembly

```asm
0x180047ff0  mov     [rsp-8+arg_18], rbx
0x180047ff5  push    rbp
0x180047ff6  push    rsi
0x180047ff7  push    rdi
0x180047ff8  push    r12
0x180047ffa  push    r13
0x180047ffc  push    r14
0x180047ffe  push    r15
0x180048000  lea     rbp, [rsp-1E0h]
0x180048008  sub     rsp, 2E0h
0x18004800f  mov     rax, cs:__security_cookie
0x180048016  xor     rax, rsp
0x180048019  mov     [rbp+210h+var_40], rax
0x180048020  mov     [rbp+210h+var_288], r9
0x180048024  mov     r14, r8
0x180048027  mov     rdi, rdx
0x18004802a  mov     r12, rcx
0x18004802d  mov     [rbp+210h+var_230], rcx
0x180048031  mov     r13, [rbp+210h+string]
0x180048038  mov     [rbp+210h+var_258], r13
0x18004803c  mov     r15, [rbp+210h+arg_28]
0x180048043  xor     edx, edx; length
0x180048045  mov     rcx, r13; string
0x180048048  call    cs:__imp_WindowsGetStringRawBuffer
0x18004804e  mov     rbx, rax
0x180048051  lea     rdx, aLaunchfiles; "LaunchFiles"
0x180048058  lea     rcx, [rbp+210h+var_190]; struct wil::details::IFailureCallback *
0x18004805f  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180048064  lea     rax, ??_7LaunchFiles@LauncherServiceProvider@@6B@; const LauncherServiceProvider::LaunchFiles::`vftable'
0x18004806b  mov     [rbp+210h+var_190], rax
0x180048072  mov     rdx, rbx; unsigned __int16 *
0x180048075  lea     rcx, [rbp+210h+var_190]; this
0x18004807c  call    ?StartActivity@LaunchFiles@LauncherServiceProvider@@QEAAXPEBG@Z; LauncherServiceProvider::LaunchFiles::StartActivity(ushort const *)
0x180048081  nop
0x180048082  call    VerifyCaller
0x180048087  mov     rcx, [rbp+218h]; this
0x18004808e  xor     ebx, ebx
0x180048090  test    eax, eax
0x180048092  jns     short loc_1800480A9
0x180048094  mov     r9d, eax; char *
0x180048097  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18004809e  mov     edx, 148h; void *
0x1800480a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800480a9  xor     ecx, ecx; string
0x1800480ab  call    cs:__imp_WindowsDeleteString
0x1800480b1  mov     [rbp+210h+var_268], rbx
0x1800480b5  lea     rcx, [rbp+210h+var_268]
0x1800480b9  call    GetCallerPackageFamilyName
0x1800480be  cmp     eax, 80070005h
0x1800480c3  jz      short loc_1800480CC
0x1800480c5  cmp     eax, 80073D54h
0x1800480ca  jnz     short loc_1800480CE
0x1800480cc  mov     eax, ebx
0x1800480ce  mov     rcx, [rbp+218h]; this
0x1800480d5  test    eax, eax
0x1800480d7  jns     short loc_1800480EE
0x1800480d9  mov     r9d, eax; char *
0x1800480dc  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800480e3  mov     edx, 152h; void *
0x1800480e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800480ee  xor     ecx, ecx; string
0x1800480f0  call    cs:__imp_WindowsDeleteString
0x1800480f6  mov     [rbp+210h+var_270], rbx
0x1800480fa  lea     rcx, [rbp+210h+var_270]; this
0x1800480fe  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x180048103  mov     rcx, [rbp+218h]; this
0x18004810a  lea     rsi, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048111  test    eax, eax
0x180048113  jns     short loc_180048125
0x180048115  mov     r9d, eax; char *
0x180048118  mov     r8, rsi; unsigned int
0x18004811b  mov     edx, 156h; void *
0x180048120  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048125  mov     rcx, [rbp+218h]; this
0x18004812c  test    rdi, rdi
0x18004812f  jnz     short loc_180048145
0x180048131  mov     r9d, 80070057h; char *
0x180048137  mov     r8, rsi; unsigned int
0x18004813a  mov     edx, 158h; void *
0x18004813f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048145  mov     [rbp+210h+var_290], rbx
0x180048149  mov     rax, [rdi]
0x18004814c  mov     rbx, [rax]
0x18004814f  lea     rcx, [rbp+210h+var_290]
0x180048153  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048158  lea     r8, [rbp+210h+var_290]
0x18004815c  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180048163  mov     rcx, rdi
0x180048166  mov     rax, rbx
0x180048169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004816e  mov     rcx, [rbp+218h]; this
0x180048175  xor     edi, edi
0x180048177  test    eax, eax
0x180048179  jns     short loc_18004818C
0x18004817b  mov     r9d, eax; char *
0x18004817e  mov     r8, rsi; unsigned int
0x180048181  mov     edx, 15Bh; void *
0x180048186  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004818c  cmp     [rbp+210h+var_290], rdi
0x180048190  setnz   al
0x180048193  mov     rcx, [rbp+218h]; this
0x18004819a  test    al, al
0x18004819c  jnz     short loc_1800481B2
0x18004819e  mov     r9d, 8000FFFFh; char *
0x1800481a4  mov     r8, rsi; unsigned int
0x1800481a7  mov     edx, 15Ch; void *
0x1800481ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481b2  mov     [rsp+310h+var_2A8], rdi
0x1800481b7  lea     rcx, [rsp+310h+var_2A8]
0x1800481bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800481c1  lea     r8, [rsp+310h+var_2A8]; struct Windows::Storage::IStorageItem **
0x1800481c6  mov     rdx, [rbp+210h+var_268]; HSTRING
0x1800481ca  mov     rcx, [rbp+210h+var_290]; struct Windows::Storage::IStorageItem *
0x1800481ce  call    ?CreateValidatedStorageItem@@YAJPEAUIStorageItem@Storage@Windows@@PEAUHSTRING__@@PEAPEAU123@@Z; CreateValidatedStorageItem(Windows::Storage::IStorageItem *,HSTRING__ *,Windows::Storage::IStorageItem * *)
0x1800481d3  mov     rcx, [rbp+218h]; this
0x1800481da  test    eax, eax
0x1800481dc  jns     short loc_1800481EF
0x1800481de  mov     r9d, eax; char *
0x1800481e1  mov     r8, rsi; unsigned int
0x1800481e4  mov     edx, 15Fh; void *
0x1800481e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481ef  mov     [rsp+310h+var_2A0], rdi
0x1800481f4  test    r14, r14
0x1800481f7  jz      short loc_180048263
0x1800481f9  mov     rax, [r14]
0x1800481fc  mov     rbx, [rax]
0x1800481ff  lea     rcx, [rsp+310h+var_2A0]
0x180048204  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048209  lea     r8, [rsp+310h+var_2A0]
0x18004820e  lea     rdx, _GUID_52fda447_2baa_412c_b29f_d4b1778efa1e
0x180048215  mov     rcx, r14
0x180048218  mov     rax, rbx
0x18004821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048220  mov     rcx, [rbp+218h]; this
0x180048227  test    eax, eax
0x180048229  jns     short loc_18004823C
0x18004822b  mov     r9d, eax; char *
0x18004822e  mov     r8, rsi; unsigned int
0x180048231  mov     edx, 164h; void *
0x180048236  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004823c  cmp     [rsp+310h+var_2A0], rdi
0x180048241  setnz   al
0x180048244  mov     rcx, [rbp+218h]; this
0x18004824b  test    al, al
0x18004824d  jnz     short loc_180048263
0x18004824f  mov     r9d, 8000FFFFh; char *
0x180048255  mov     r8, rsi; unsigned int
0x180048258  mov     edx, 165h; void *
0x18004825d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048263  mov     [rsp+310h+var_2B0], dil
0x180048268  mov     rcx, [rsp+310h+var_2A8]
0x18004826d  mov     rax, [rcx]
0x180048270  lea     r8, [rsp+310h+var_2B0]
0x180048275  mov     edx, 1
0x18004827a  mov     rax, [rax+78h]
0x18004827e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048283  mov     rcx, [rbp+218h]; this
0x18004828a  test    eax, eax
0x18004828c  jns     short loc_18004829F
0x18004828e  mov     r9d, eax; char *
0x180048291  mov     r8, rsi; unsigned int
0x180048294  mov     edx, 169h; void *
0x180048299  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004829f  cmp     [rsp+310h+var_2B0], dil
0x1800482a4  setnz   al
0x1800482a7  mov     rcx, [rbp+218h]; this
0x1800482ae  test    al, al
0x1800482b0  jnz     short loc_1800482C6
0x1800482b2  mov     r9d, 8000FFFFh; char *
0x1800482b8  mov     r8, rsi; unsigned int
0x1800482bb  mov     edx, 16Ah; void *
0x1800482c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800482c6  mov     r8, [rbp+210h+var_288]
0x1800482ca  mov     rdx, r12
0x1800482cd  lea     rcx, [rbp+210h+var_228]
0x1800482d1  call    ?Capture@CallerInformation@@SA?AV1@_K0@Z; CallerInformation::Capture(unsigned __int64,unsigned __int64)
0x1800482d6  nop
0x1800482d7  mov     [rsp+310h+var_298], rdi
0x1800482dc  test    r15, r15
0x1800482df  jz      loc_180048442
0x1800482e5  mov     [rbp+210h+var_288], rdi
0x1800482e9  lea     rdx, [rbp+210h+var_288]
0x1800482ed  lea     rcx, [rsp+310h+var_2A8]
0x1800482f2  call    ??$As@UIStorageFile@Storage@Windows@@@?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<Windows::Storage::IStorageFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>)
0x1800482f7  mov     rcx, [rbp+218h]; this
0x1800482fe  test    eax, eax
0x180048300  jns     short loc_180048313
0x180048302  mov     r9d, eax; char *
0x180048305  mov     r8, rsi; unsigned int
0x180048308  mov     edx, 172h; void *
0x18004830d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048313  mov     rdx, [rbp+210h+var_288]
0x180048317  lea     rcx, [rbp+210h+var_278]
0x18004831b  call    ?GetFileExtensionStringForAppResolverFromStorageFile@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIStorageFile@Storage@Windows@@@Z; GetFileExtensionStringForAppResolverFromStorageFile(Windows::Storage::IStorageFile *)
0x180048320  nop
0x180048321  mov     [rbp+210h+var_280], rdi
0x180048325  mov     [rsp+310h+var_2AF], dil
0x18004832a  mov     [rbp+210h+var_250], rdi
0x18004832e  mov     qword ptr [rbp+210h+var_248], rdi
0x180048332  mov     rax, [rsp+310h+var_2A0]
0x180048337  mov     [rbp+210h+var_240], rax
0x18004833b  mov     rax, [rsp+310h+var_2A8]
0x180048340  mov     [rbp+210h+var_238], rax
0x180048344  mov     [rbp+210h+var_260], rdi
0x180048348  lea     rcx, [rbp+210h+var_280]
0x18004834c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048351  lea     rax, [rbp+210h+var_258]
0x180048355  mov     [rsp+310h+var_2D0], rax
0x18004835a  lea     rax, [rsp+310h+var_2AF]
0x18004835f  mov     [rsp+310h+var_2D8], rax
0x180048364  lea     rax, [rbp+210h+var_228]
0x180048368  mov     [rsp+310h+var_2E0], rax
0x18004836d  lea     rax, [rbp+210h+var_250]
0x180048371  mov     [rsp+310h+var_2E8], rax
0x180048376  lea     rax, [rbp+210h+var_248]
0x18004837a  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18004837f  lea     r9, [rbp+210h+var_240]
0x180048383  lea     r8, [rbp+210h+var_238]
0x180048387  lea     rdx, [rbp+210h+var_260]
0x18004838b  lea     rcx, [rbp+210h+var_280]
0x18004838f  call    ??$MakeAndInitialize@VCTargetAppResolver@@UILauncherTargetResolver@@AEAPEBULAUNCH_PARAMETERS@@AEAPEAUIUnknown@@AEAPEAUIStorageFileQueryResult@Search@Storage@Windows@@AEAPEAUHSTRING__@@AEAPEAU9@AEBVCallerInformation@@AEB_NAEAPEAU9@@Details@WRL@Microsoft@@YAJPEAPEAUILauncherTargetResolver@@AEAPEBULAUNCH_PARAMETERS@@AEAPEAUIUnknown@@AEAPEAUIStorageFileQueryResult@Search@Storage@Windows@@AEAPEAUHSTRING__@@4AEBVCallerInformation@@AEB_N4@Z; Microsoft::WRL::Details::MakeAndInitialize<CTargetAppResolver,ILauncherTargetResolver,LAUNCH_PARAMETERS const * &,IUnknown * &,Windows::Storage::Search::IStorageFileQueryResult * &,HSTRING__ * &,HSTRING__ * &,CallerInformation const &,bool const &,HSTRING__ * &>(ILauncherTargetResolver * *,LAUNCH_PARAMETERS const * &,IUnknown * &,Windows::Storage::Search::IStorageFileQueryResult * &,HSTRING__ * &,HSTRING__ * &,CallerInformation const &,bool const &,HSTRING__ * &)
0x180048394  mov     rcx, [rbp+218h]; this
0x18004839b  test    eax, eax
0x18004839d  jns     short loc_1800483B0
0x18004839f  mov     r9d, eax; char *
0x1800483a2  mov     r8, rsi; unsigned int
0x1800483a5  mov     edx, 178h; void *
0x1800483aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800483b0  mov     rdi, [rbp+210h+var_280]
0x1800483b4  mov     rax, [rdi]
0x1800483b7  mov     rbx, [rax+18h]
0x1800483bb  lea     rcx, [rsp+310h+var_298]
0x1800483c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800483c5  lea     r9, [rsp+310h+var_298]
0x1800483ca  mov     r8, r15
0x1800483cd  mov     rdx, [rbp+210h+var_278]
0x1800483d1  mov     rcx, rdi
0x1800483d4  mov     rax, rbx
0x1800483d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483dc  mov     rcx, [rbp+218h]; this
0x1800483e3  xor     edi, edi
0x1800483e5  test    eax, eax
0x1800483e7  jns     short loc_1800483FA
0x1800483e9  mov     r9d, eax; char *
0x1800483ec  mov     r8, rsi; unsigned int
0x1800483ef  mov     edx, 179h; void *
0x1800483f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800483fa  cmp     [rsp+310h+var_298], rdi
0x1800483ff  setz    al
0x180048402  mov     rcx, [rbp+218h]; this
0x180048409  test    al, al
0x18004840b  jz      short loc_180048421
0x18004840d  mov     r9d, 80070483h; char *
0x180048413  mov     r8, rsi; unsigned int
0x180048416  mov     edx, 17Ah; void *
0x18004841b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048421  lea     rcx, [rbp+210h+var_280]
0x180048425  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004842a  nop
0x18004842b  mov     rcx, [rbp+210h+var_278]; string
0x18004842f  call    cs:__imp_WindowsDeleteString
0x180048435  mov     [rbp+210h+var_278], rdi
0x180048439  lea     rcx, [rbp+210h+var_288]
0x18004843d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048442  xor     edx, edx; length
0x180048444  mov     rcx, [rbp+210h+var_270]; string
0x180048448  call    cs:__imp_WindowsGetStringRawBuffer
0x18004844e  mov     [rbp+210h+var_260], rax
0x180048452  lea     r8, [rbp+210h+var_260]
0x180048456  lea     rdx, [rbp+210h+var_230]
0x18004845a  lea     rcx, [rbp+210h+var_190]
0x180048461  call    ??$LaunchFileRequest@AEB_KPEBG@LaunchFiles@LauncherServiceProvider@@QEAAXAEB_K$$QEAPEBG@Z; LauncherServiceProvider::LaunchFiles::LaunchFileRequest<unsigned __int64 const &,ushort const *>(unsigned __int64 const &,ushort const * &&)
0x180048466  mov     r15, [rsp+310h+var_298]
0x18004846b  mov     [rbp+210h+var_1E0], rdi
0x18004846f  xor     r9d, r9d; unsigned int
0x180048472  lea     r8d, [r9+1]; unsigned int
0x180048476  lea     r12, LocaleName
0x18004847d  mov     rdx, r12; sourceString
0x180048480  lea     rcx, [rbp+210h+hstringHeader]; hstringHeader
0x180048484  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048489  nop
0x18004848a  mov     r14, [rbp+210h+var_1E0]
0x18004848e  mov     [rbp+210h+var_1C0], rdi
0x180048492  xor     r9d, r9d; unsigned int
0x180048495  lea     r8d, [r9+1]; unsigned int
0x180048499  mov     rdx, r12; sourceString
0x18004849c  lea     rcx, [rbp+210h+var_1D8]; hstringHeader
0x1800484a0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800484a5  nop
0x1800484a6  mov     rbx, [rbp+210h+var_1C0]
0x1800484aa  mov     rdi, [rsp+310h+var_2A0]
0x1800484af  mov     rsi, [rsp+310h+var_2A8]
0x1800484b4  mov     [rbp+210h+var_1A0], 0
0x1800484bc  xor     r9d, r9d; unsigned int
0x1800484bf  lea     r8d, [r9+1]; unsigned int
0x1800484c3  mov     rdx, r12; sourceString
0x1800484c6  lea     rcx, [rbp+210h+var_1B8]; hstringHeader
0x1800484ca  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800484cf  nop
0x1800484d0  mov     [rsp+310h+var_2C0], r13
  ... truncated ...
```
