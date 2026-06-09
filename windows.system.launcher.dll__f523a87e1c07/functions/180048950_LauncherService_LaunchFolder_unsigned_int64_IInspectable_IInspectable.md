# LauncherService::LaunchFolder(unsigned __int64,IInspectable *,IInspectable *)

- ea: `0x180048950`
- end: `0x180048cdc`
- name: `?LaunchFolder@LauncherService@@UEAAJ_KPEAUIInspectable@@1@Z`
- size: `908`
- prototype: `__int64 __fastcall(LauncherService *__hidden this, unsigned __int64, struct IInspectable *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180047254`
- `0x1800486d8`
- `0x180048950`
- `0x180048ce4`
- `0x18004e550`
- `0x1800596d8`
- `0x180075ce4`
- `0x180087fb0`
- `0x18008a030`
- `0x1800ae61c`
- `0x1800b2048`
- `0x1800b58e4`
- `0x1800bae88`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c9a`

## string_xrefs

- `0x1800489ec`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048a28`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048a55`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048a9c`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048ac8`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048b18`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048b66`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048bbb`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048c2d`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall LauncherService::LaunchFolder(
        LauncherService *this,
        __int64 a2,
        struct IInspectable *a3,
        struct IInspectable *a4)
{
  int CallerPackageFamilyName; // eax
  HSTRING *v8; // rdx
  int CallerAumidOrProcessName; // eax
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v11; // eax
  int v12; // eax
  struct Windows::Storage::IStorageItem *v13; // rbx
  __int64 (__fastcall *v14)(struct Windows::Storage::IStorageItem *, GUID *, IUnknown **); // rdi
  int v15; // eax
  HRESULT (__stdcall *v16)(IInspectable *, const IID *const, void **); // rbx
  int v17; // eax
  __int64 v18; // rbx
  IUnknown *v19; // rdi
  __int64 v20; // rax
  int v21; // eax
  struct Windows::Storage::IStorageItem *v23; // [rsp+20h] [rbp-1E8h] BYREF
  __int64 v24; // [rsp+28h] [rbp-1E0h] BYREF
  struct Windows::Storage::IStorageItem *v25; // [rsp+30h] [rbp-1D8h] BYREF
  IUnknown *v26; // [rsp+38h] [rbp-1D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1C8h] BYREF
  HSTRING v28; // [rsp+48h] [rbp-1C0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-1B0h] BYREF
  _BYTE v31[40]; // [rsp+60h] [rbp-1A8h] BYREF
  HSTRING v32; // [rsp+88h] [rbp-180h]
  _QWORD v33[42]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v30 = a2;
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v33);
  v33[0] = &LauncherServiceProvider::LaunchFolder::`vftable';
  LauncherServiceProvider::LaunchFolder::StartActivity((LauncherServiceProvider::LaunchFolder *)v33);
  WindowsDeleteString(0);
  v28 = 0;
  CallerPackageFamilyName = GetCallerPackageFamilyName(&v28);
  if ( CallerPackageFamilyName == -2147024891 || CallerPackageFamilyName == -2147009196 )
    CallerPackageFamilyName = 0;
  if ( CallerPackageFamilyName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)CallerPackageFamilyName,
      (int)v23);
  WindowsDeleteString(0);
  string = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&string, v8);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      (int)v23);
  v23 = 0;
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x80070057LL,
      (int)v23);
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v11 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct Windows::Storage::IStorageItem **))QueryInterface)(
          a3,
          &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
          &v23);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v11,
      (int)v23);
  if ( !v23 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x8000FFFFLL,
      0);
  v26 = 0;
  v25 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v12 = CreateValidatedStorageItem(v23, v28, &v25);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v12,
      (int)v23);
  v13 = v25;
  v14 = **(__int64 (__fastcall ***)(struct Windows::Storage::IStorageItem *, GUID *, IUnknown **))v25;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v15 = v14(v13, &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b, &v26);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v15,
      (int)v23);
  v24 = 0;
  if ( a4 )
  {
    v16 = a4->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    v17 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v16)(
            a4,
            &GUID_802508e2_9c2c_5b91_89a8_39bcf7223344,
            &v24);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v17,
        (int)v23);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  LauncherServiceProvider::LaunchFolder::LaunchFolderRequest<unsigned __int64 const &,unsigned short const *>(
    v33,
    &v30,
    &StringRawBuffer);
  v18 = v24;
  v19 = v26;
  v20 = CallerInformation::Capture(v31, a2, 0);
  v21 = LaunchFileExplorer(v20, v19, v18);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v21,
      (int)v23);
  WindowsDeleteString(v32);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v33,
    0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  WindowsDeleteString(string);
  WindowsDeleteString(v28);
  LauncherServiceProvider::LaunchFolder::~LaunchFolder((LauncherServiceProvider::LaunchFolder *)v33);
  return 0;
}

```

## disassembly

```asm
0x180048950  mov     [rsp+arg_0], rbx
0x180048955  push    rdi
0x180048956  push    r14
0x180048958  push    r15
0x18004895a  sub     rsp, 1F0h
0x180048961  mov     rax, cs:__security_cookie
0x180048968  xor     rax, rsp
0x18004896b  mov     [rsp+208h+var_28], rax
0x180048973  mov     r14, r9
0x180048976  mov     rdi, r8
0x180048979  mov     r15, rdx
0x18004897c  mov     [rsp+208h+var_1B0], rdx
0x180048981  lea     rdx, aLaunchfolder; "LaunchFolder"
0x180048988  lea     rcx, [rsp+208h+var_178]; struct wil::details::IFailureCallback *
0x180048990  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180048995  lea     rax, ??_7LaunchFolder@LauncherServiceProvider@@6B@; const LauncherServiceProvider::LaunchFolder::`vftable'
0x18004899c  mov     [rsp+208h+var_178], rax
0x1800489a4  lea     rcx, [rsp+208h+var_178]; this
0x1800489ac  call    ?StartActivity@LaunchFolder@LauncherServiceProvider@@QEAAXXZ; LauncherServiceProvider::LaunchFolder::StartActivity(void)
0x1800489b1  nop
0x1800489b2  xor     ecx, ecx; string
0x1800489b4  call    cs:__imp_WindowsDeleteString
0x1800489ba  mov     [rsp+208h+var_1C0], 0
0x1800489c3  lea     rcx, [rsp+208h+var_1C0]
0x1800489c8  call    GetCallerPackageFamilyName
0x1800489cd  cmp     eax, 80070005h
0x1800489d2  jz      short loc_1800489DB
0x1800489d4  cmp     eax, 80073D54h
0x1800489d9  jnz     short loc_1800489DD
0x1800489db  xor     eax, eax
0x1800489dd  mov     rcx, [rsp+208h]; this
0x1800489e5  test    eax, eax
0x1800489e7  jns     short loc_1800489FE
0x1800489e9  mov     r9d, eax; char *
0x1800489ec  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800489f3  mov     edx, 19Fh; void *
0x1800489f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800489fe  xor     ecx, ecx; string
0x180048a00  call    cs:__imp_WindowsDeleteString
0x180048a06  mov     [rsp+208h+string], 0
0x180048a0f  lea     rcx, [rsp+208h+string]; this
0x180048a14  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x180048a19  mov     rcx, [rsp+208h]; this
0x180048a21  test    eax, eax
0x180048a23  jns     short loc_180048A39
0x180048a25  mov     r9d, eax; char *
0x180048a28  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048a2f  mov     edx, 1A3h; void *
0x180048a34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048a39  mov     [rsp+208h+var_1E8], 0; int
0x180048a42  mov     rcx, [rsp+208h]; this
0x180048a4a  test    rdi, rdi
0x180048a4d  jnz     short loc_180048A66
0x180048a4f  mov     r9d, 80070057h; char *
0x180048a55  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048a5c  mov     edx, 1A6h; void *
0x180048a61  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048a66  mov     rax, [rdi]
0x180048a69  mov     rbx, [rax]
0x180048a6c  lea     rcx, [rsp+208h+var_1E8]
0x180048a71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048a76  lea     r8, [rsp+208h+var_1E8]
0x180048a7b  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180048a82  mov     rcx, rdi
0x180048a85  mov     rax, rbx
0x180048a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a8d  mov     rcx, [rsp+208h]; this
0x180048a95  test    eax, eax
0x180048a97  jns     short loc_180048AAD
0x180048a99  mov     r9d, eax; char *
0x180048a9c  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048aa3  mov     edx, 1A8h; void *
0x180048aa8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048aad  cmp     [rsp+208h+var_1E8], 0
0x180048ab3  setnz   al
0x180048ab6  mov     rcx, [rsp+208h]; this
0x180048abe  test    al, al
0x180048ac0  jnz     short loc_180048AD9
0x180048ac2  mov     r9d, 8000FFFFh; char *
0x180048ac8  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048acf  mov     edx, 1A9h; void *
0x180048ad4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048ad9  mov     [rsp+208h+var_1D0], 0
0x180048ae2  mov     [rsp+208h+var_1D8], 0
0x180048aeb  lea     rcx, [rsp+208h+var_1D8]
0x180048af0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048af5  lea     r8, [rsp+208h+var_1D8]; struct Windows::Storage::IStorageItem **
0x180048afa  mov     rdx, [rsp+208h+var_1C0]; HSTRING
0x180048aff  mov     rcx, [rsp+208h+var_1E8]; struct Windows::Storage::IStorageItem *
0x180048b04  call    ?CreateValidatedStorageItem@@YAJPEAUIStorageItem@Storage@Windows@@PEAUHSTRING__@@PEAPEAU123@@Z; CreateValidatedStorageItem(Windows::Storage::IStorageItem *,HSTRING__ *,Windows::Storage::IStorageItem * *)
0x180048b09  mov     rcx, [rsp+208h]; this
0x180048b11  test    eax, eax
0x180048b13  jns     short loc_180048B2A
0x180048b15  mov     r9d, eax; char *
0x180048b18  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048b1f  mov     edx, 1AEh; void *
0x180048b24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b2a  mov     rbx, [rsp+208h+var_1D8]
0x180048b2f  mov     rax, [rbx]
0x180048b32  mov     rdi, [rax]
0x180048b35  lea     rcx, [rsp+208h+var_1D0]
0x180048b3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048b3f  lea     r8, [rsp+208h+var_1D0]
0x180048b44  lea     rdx, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x180048b4b  mov     rcx, rbx
0x180048b4e  mov     rax, rdi
0x180048b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b56  nop
0x180048b57  mov     rcx, [rsp+208h]; this
0x180048b5f  test    eax, eax
0x180048b61  jns     short loc_180048B77
0x180048b63  mov     r9d, eax; char *
0x180048b66  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048b6d  mov     edx, 1AFh; void *
0x180048b72  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b77  mov     [rsp+208h+var_1E0], 0
0x180048b80  test    r14, r14
0x180048b83  jz      short loc_180048BCC
0x180048b85  mov     rax, [r14]
0x180048b88  mov     rbx, [rax]
0x180048b8b  lea     rcx, [rsp+208h+var_1E0]
0x180048b90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048b95  lea     r8, [rsp+208h+var_1E0]
0x180048b9a  lea     rdx, _GUID_802508e2_9c2c_5b91_89a8_39bcf7223344
0x180048ba1  mov     rcx, r14
0x180048ba4  mov     rax, rbx
0x180048ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bac  mov     rcx, [rsp+208h]; this
0x180048bb4  test    eax, eax
0x180048bb6  jns     short loc_180048BCC
0x180048bb8  mov     r9d, eax; char *
0x180048bbb  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048bc2  mov     edx, 1B5h; void *
0x180048bc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048bcc  xor     edx, edx; length
0x180048bce  mov     rcx, [rsp+208h+string]; string
0x180048bd3  call    cs:__imp_WindowsGetStringRawBuffer
0x180048bd9  mov     [rsp+208h+var_1B8], rax
0x180048bde  lea     r8, [rsp+208h+var_1B8]
0x180048be3  lea     rdx, [rsp+208h+var_1B0]
0x180048be8  lea     rcx, [rsp+208h+var_178]
0x180048bf0  call    ??$LaunchFolderRequest@AEB_KPEBG@LaunchFolder@LauncherServiceProvider@@QEAAXAEB_K$$QEAPEBG@Z; LauncherServiceProvider::LaunchFolder::LaunchFolderRequest<unsigned __int64 const &,ushort const *>(unsigned __int64 const &,ushort const * &&)
0x180048bf5  mov     rbx, [rsp+208h+var_1E0]
0x180048bfa  mov     rdi, [rsp+208h+var_1D0]
0x180048bff  xor     r8d, r8d
0x180048c02  mov     rdx, r15
0x180048c05  lea     rcx, [rsp+208h+var_1A8]
0x180048c0a  call    ?Capture@CallerInformation@@SA?AV1@_K0@Z; CallerInformation::Capture(unsigned __int64,unsigned __int64)
0x180048c0f  nop
0x180048c10  mov     r8, rbx
0x180048c13  mov     rdx, rdi
0x180048c16  mov     rcx, rax
0x180048c19  call    ?LaunchFileExplorer@@YAJAEBVCallerInformation@@PEAUIStorageFolder@Storage@Windows@@PEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@4@@Z; LaunchFileExplorer(CallerInformation const &,Windows::Storage::IStorageFolder *,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> *)
0x180048c1e  mov     rcx, [rsp+208h]; this
0x180048c26  test    eax, eax
0x180048c28  jns     short loc_180048C3F
0x180048c2a  mov     r9d, eax; char *
0x180048c2d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048c34  mov     edx, 1B9h; void *
0x180048c39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048c3f  mov     rcx, [rsp+208h+var_180]; string
0x180048c47  call    cs:__imp_WindowsDeleteString
0x180048c4d  xor     edx, edx
0x180048c4f  lea     rcx, [rsp+208h+var_178]
0x180048c57  call    ?Stop@?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180048c5c  nop
0x180048c5d  lea     rcx, [rsp+208h+var_1E0]
0x180048c62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c67  nop
0x180048c68  lea     rcx, [rsp+208h+var_1D8]
0x180048c6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c72  nop
0x180048c73  lea     rcx, [rsp+208h+var_1D0]
0x180048c78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c7d  nop
0x180048c7e  lea     rcx, [rsp+208h+var_1E8]
0x180048c83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c88  nop
0x180048c89  mov     rcx, [rsp+208h+string]; string
0x180048c8e  call    cs:__imp_WindowsDeleteString
0x180048c94  nop
0x180048c95  mov     rcx, [rsp+208h+var_1C0]; string
0x180048c9a  call    cs:__imp_WindowsDeleteString
0x180048ca0  nop
0x180048ca1  lea     rcx, [rsp+208h+var_178]; this
0x180048ca9  call    ??1LaunchFolder@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::LaunchFolder::~LaunchFolder(void)
0x180048cae  xor     eax, eax
0x180048cb0  jmp     short loc_180048CB6
0x180048cb2  mov     eax, dword ptr [rsp+208h+var_1E8]
0x180048cb6  mov     rcx, [rsp+208h+var_28]
0x180048cbe  xor     rcx, rsp; StackCookie
0x180048cc1  call    __security_check_cookie
0x180048cc6  mov     rbx, [rsp+208h+arg_0]
0x180048cce  add     rsp, 1F0h
0x180048cd5  pop     r15
0x180048cd7  pop     r14
0x180048cd9  pop     rdi
0x180048cda  retn
```
