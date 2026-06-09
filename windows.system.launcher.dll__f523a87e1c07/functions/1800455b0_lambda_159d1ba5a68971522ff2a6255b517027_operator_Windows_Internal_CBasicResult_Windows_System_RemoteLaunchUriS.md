# _lambda_159d1ba5a68971522ff2a6255b517027_::operator()(Windows::Internal::CBasicResult<Windows::System::RemoteLaunchUriStatus,0> &)

- ea: `0x1800455b0`
- end: `0x1800458a4`
- name: `??R_lambda_159d1ba5a68971522ff2a6255b517027_@@QEAAJAEAV?$CBasicResult@W4RemoteLaunchUriStatus@System@Windows@@$0A@@Internal@Windows@@@Z`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800a3820`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180028740`
- `0x180028b70`
- `0x180045504`
- `0x1800455b0`
- `0x180047254`
- `0x1800596d8`
- `0x18006e350`
- `0x18008a030`
- `0x1800a1da0`
- `0x1800a1f78`
- `0x1800a201c`
- `0x1800a26a4`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004568f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800456df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800456f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004568f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800456df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800456f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004560f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004560f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045867`

## string_xrefs

- `0x1800455e8`: `RemoteLaunchUriAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_159d1ba5a68971522ff2a6255b517027_::operator()(_QWORD *a1, __int64 a2)
{
  HSTRING *v4; // rdx
  int CallerAumidOrProcessName; // eax
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, HSTRING *); // rbx
  HSTRING *v8; // rdx
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v18; // [rsp+20h] [rbp-E0h]
  HSTRING v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v22; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v24; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v26; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR v27[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v28[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v28);
  v28[0] = &LauncherClientProvider::RemoteLaunchUriAsync::`vftable';
  LauncherClientProvider::RemoteLaunchUriAsync::StartActivity((LauncherClientProvider::RemoteLaunchUriAsync *)v28);
  WindowsDeleteString(0);
  v24 = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&v24, v4);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.remotelauncher.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      v18);
  StringRawBuffer = &LocaleName;
  string = 0;
  v6 = a1[1];
  v7 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v7(v6, &string) >= 0 )
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  WindowsDeleteString(0);
  v22 = 0;
  v9 = LauncherMiscHelpers::CreateCorrelationVector(&v22, v8);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v26 = WindowsGetStringRawBuffer(v22, 0);
    v27[0] = WindowsGetStringRawBuffer(v24, 0);
    LauncherClientProvider::RemoteLaunchUriAsync::RemoteLaunchUriRequest<unsigned short const *,unsigned short const * &,unsigned short const *>(
      v28,
      v27,
      &StringRawBuffer,
      &v26);
    v19 = 0;
    v11 = a1[1];
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 128LL);
    WindowsDeleteString(0);
    v19 = 0;
    v13 = v12(v11, &v19);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v20 = 0;
      v21 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      v14 = Microsoft::WRL::Details::MakeAndInitialize<RemoteLauncherInteropImpl,Windows::System::Internal::Launch::IRemoteLauncherInteropStatics,>(&v21);
      v10 = v14;
      if ( v14 >= 0 )
      {
        v18 = a1[2];
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v21 + 48LL))(
                v21,
                *a1,
                v19,
                a1[3]);
        LauncherClientProvider::RemoteLaunchUriAsync::RemoteLaunchUriStatus<enum Windows::System::RemoteLaunchUriStatus &>(
          v28,
          &v20);
        if ( v10 >= 0 )
        {
          *(_DWORD *)(a2 + 16) = v20;
          wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v28,
            0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
          WindowsDeleteString(v19);
          v10 = 0;
          goto LABEL_16;
        }
        v15 = (unsigned int)v10;
        v16 = 149;
      }
      else
      {
        v15 = (unsigned int)v14;
        v16 = 140;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.remotelauncher.cpp",
        (const char *)v15,
        v18);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.remotelauncher.cpp",
        (const char *)(unsigned int)v13,
        v18);
    }
    WindowsDeleteString(v19);
LABEL_16:
    v19 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x84,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.remotelauncher.cpp",
    (const char *)(unsigned int)v9,
    v18);
LABEL_17:
  WindowsDeleteString(v22);
  v22 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v24);
  LauncherClientProvider::RemoteLaunchUriAsync::~RemoteLaunchUriAsync((LauncherClientProvider::RemoteLaunchUriAsync *)v28);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800455b0  mov     [rsp-8+arg_10], rbx
0x1800455b5  mov     [rsp-8+arg_18], rsi
0x1800455ba  push    rbp
0x1800455bb  push    rdi
0x1800455bc  push    r12
0x1800455be  push    r14
0x1800455c0  push    r15
0x1800455c2  lea     rbp, [rsp-0F0h]
0x1800455ca  sub     rsp, 1F0h
0x1800455d1  mov     rax, cs:__security_cookie
0x1800455d8  xor     rax, rsp
0x1800455db  mov     [rbp+110h+var_30], rax
0x1800455e2  mov     r14, rdx
0x1800455e5  mov     rsi, rcx
0x1800455e8  lea     rdx, aRemotelaunchur; "RemoteLaunchUriAsync"
0x1800455ef  lea     rcx, [rbp+110h+var_180]; struct wil::details::IFailureCallback *
0x1800455f3  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800455f8  lea     rax, ??_7RemoteLaunchUriAsync@LauncherClientProvider@@6B@; const LauncherClientProvider::RemoteLaunchUriAsync::`vftable'
0x1800455ff  mov     [rbp+110h+var_180], rax
0x180045603  lea     rcx, [rbp+110h+var_180]; this
0x180045607  call    ?StartActivity@RemoteLaunchUriAsync@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::RemoteLaunchUriAsync::StartActivity(void)
0x18004560c  nop
0x18004560d  xor     ecx, ecx; string
0x18004560f  call    cs:__imp_WindowsDeleteString
0x180045615  xor     r15d, r15d
0x180045618  mov     [rsp+210h+var_1A8], r15
0x18004561d  lea     rcx, [rsp+210h+var_1A8]; this
0x180045622  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x180045627  mov     rcx, [rbp+118h]; this
0x18004562e  lea     r12, aOnecoreuapShel_36; "onecoreuap\\shell\\windows.system.launc"...
0x180045635  test    eax, eax
0x180045637  jns     short loc_180045648
0x180045639  mov     r9d, eax; char *
0x18004563c  mov     r8, r12; unsigned int
0x18004563f  lea     edx, [r15+78h]; void *
0x180045643  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045648  lea     rax, LocaleName
0x18004564f  mov     [rsp+210h+var_1A0], rax
0x180045654  mov     [rsp+210h+string], r15
0x180045659  mov     rdi, [rsi+8]
0x18004565d  mov     rax, [rdi]
0x180045660  mov     rbx, [rax+88h]
0x180045667  xor     ecx, ecx; string
0x180045669  call    cs:__imp_WindowsDeleteString
0x18004566f  mov     [rsp+210h+string], r15
0x180045674  lea     rdx, [rsp+210h+string]
0x180045679  mov     rcx, rdi
0x18004567c  mov     rax, rbx
0x18004567f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045684  test    eax, eax
0x180045686  js      short loc_18004569A
0x180045688  xor     edx, edx; length
0x18004568a  mov     rcx, [rsp+210h+string]; string
0x18004568f  call    cs:__imp_WindowsGetStringRawBuffer
0x180045695  mov     [rsp+210h+var_1A0], rax
0x18004569a  mov     [rsp+210h+var_1B8], r15
0x18004569f  xor     ecx, ecx; string
0x1800456a1  call    cs:__imp_WindowsDeleteString
0x1800456a7  mov     [rsp+210h+var_1B8], r15
0x1800456ac  lea     rcx, [rsp+210h+var_1B8]; string
0x1800456b1  call    ?CreateCorrelationVector@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::CreateCorrelationVector(HSTRING__ * *)
0x1800456b6  mov     ebx, eax
0x1800456b8  test    eax, eax
0x1800456ba  jns     short loc_1800456D8
0x1800456bc  mov     rcx, [rbp+118h]; this
0x1800456c3  mov     r9d, eax; char *
0x1800456c6  mov     r8, r12; unsigned int
0x1800456c9  mov     edx, 84h; void *
0x1800456ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800456d3  jmp     loc_180045842
0x1800456d8  xor     edx, edx; length
0x1800456da  mov     rcx, [rsp+210h+var_1B8]; string
0x1800456df  call    cs:__imp_WindowsGetStringRawBuffer
0x1800456e5  mov     [rsp+210h+var_198], rax
0x1800456ea  xor     edx, edx; length
0x1800456ec  mov     rcx, [rsp+210h+var_1A8]; string
0x1800456f1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800456f7  mov     [rbp+110h+var_190], rax
0x1800456fb  lea     r9, [rsp+210h+var_198]
0x180045700  lea     r8, [rsp+210h+var_1A0]
0x180045705  lea     rdx, [rbp+110h+var_190]
0x180045709  lea     rcx, [rbp+110h+var_180]
0x18004570d  call    ??$RemoteLaunchUriRequest@PEBGAEAPEBGPEBG@RemoteLaunchUriAsync@LauncherClientProvider@@QEAAX$$QEAPEBGAEAPEBG0@Z; LauncherClientProvider::RemoteLaunchUriAsync::RemoteLaunchUriRequest<ushort const *,ushort const * &,ushort const *>(ushort const * &&,ushort const * &,ushort const * &&)
0x180045712  mov     [rsp+210h+var_1D0], r15
0x180045717  mov     rdi, [rsi+8]
0x18004571b  mov     rax, [rdi]
0x18004571e  mov     rbx, [rax+80h]
0x180045725  xor     ecx, ecx; string
0x180045727  call    cs:__imp_WindowsDeleteString
0x18004572d  mov     [rsp+210h+var_1D0], r15
0x180045732  lea     rdx, [rsp+210h+var_1D0]
0x180045737  mov     rcx, rdi
0x18004573a  mov     rax, rbx
0x18004573d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045742  mov     ebx, eax
0x180045744  test    eax, eax
0x180045746  jns     short loc_180045770
0x180045748  mov     rcx, [rbp+118h]; this
0x18004574f  mov     r9d, eax; char *
0x180045752  mov     r8, r12; unsigned int
0x180045755  mov     edx, 88h; void *
0x18004575a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004575f  nop
0x180045760  mov     rcx, [rsp+210h+var_1D0]; string
0x180045765  call    cs:__imp_WindowsDeleteString
0x18004576b  jmp     loc_18004583D
0x180045770  mov     [rsp+210h+var_1C8], r15d
0x180045775  mov     [rsp+210h+var_1C0], r15
0x18004577a  lea     rcx, [rsp+210h+var_1C0]
0x18004577f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045784  lea     rcx, [rsp+210h+var_1C0]
0x180045789  call    ??$MakeAndInitialize@VRemoteLauncherInteropImpl@@UIRemoteLauncherInteropStatics@Launch@Internal@System@Windows@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIRemoteLauncherInteropStatics@Launch@Internal@System@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RemoteLauncherInteropImpl,Windows::System::Internal::Launch::IRemoteLauncherInteropStatics,>(Windows::System::Internal::Launch::IRemoteLauncherInteropStatics * *)
0x18004578e  mov     ebx, eax
0x180045790  test    eax, eax
0x180045792  jns     short loc_1800457B8
0x180045794  mov     r9d, eax; char *
0x180045797  mov     edx, 8Ch; void *
0x18004579c  mov     r8, r12; unsigned int
0x18004579f  mov     rcx, [rbp+118h]; this
0x1800457a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800457ab  nop
0x1800457ac  lea     rcx, [rsp+210h+var_1C0]
0x1800457b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800457b6  jmp     short loc_180045760
0x1800457b8  mov     rcx, [rsp+210h+var_1C0]
0x1800457bd  mov     rdx, [rsp+210h+var_1B8]
0x1800457c2  mov     rax, [rcx]
0x1800457c5  lea     r8, [rsp+210h+var_1C8]
0x1800457ca  mov     [rsp+210h+var_1E0], r8
0x1800457cf  mov     [rsp+210h+var_1E8], rdx
0x1800457d4  mov     rdx, [rsi+10h]
0x1800457d8  mov     [rsp+210h+var_1F0], rdx
0x1800457dd  mov     r9, [rsi+18h]
0x1800457e1  mov     r8, [rsp+210h+var_1D0]
0x1800457e6  mov     rdx, [rsi]
0x1800457e9  mov     rax, [rax+30h]
0x1800457ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457f2  mov     ebx, eax
0x1800457f4  lea     rdx, [rsp+210h+var_1C8]
0x1800457f9  lea     rcx, [rbp+110h+var_180]
0x1800457fd  call    ??$RemoteLaunchUriStatus@AEAW40System@Windows@@@RemoteLaunchUriAsync@LauncherClientProvider@@QEAAXAEAW4RemoteLaunchUriStatus@System@Windows@@@Z; LauncherClientProvider::RemoteLaunchUriAsync::RemoteLaunchUriStatus<Windows::System::RemoteLaunchUriStatus &>(Windows::System::RemoteLaunchUriStatus &)
0x180045802  test    ebx, ebx
0x180045804  jns     short loc_180045810
0x180045806  mov     r9d, ebx
0x180045809  mov     edx, 95h
0x18004580e  jmp     short loc_18004579C
0x180045810  mov     eax, [rsp+210h+var_1C8]
0x180045814  mov     [r14+10h], eax
0x180045818  xor     edx, edx
0x18004581a  lea     rcx, [rbp+110h+var_180]
0x18004581e  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180045823  nop
0x180045824  lea     rcx, [rsp+210h+var_1C0]
0x180045829  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004582e  nop
0x18004582f  mov     rcx, [rsp+210h+var_1D0]; string
0x180045834  call    cs:__imp_WindowsDeleteString
0x18004583a  mov     ebx, r15d
0x18004583d  mov     [rsp+210h+var_1D0], r15
0x180045842  mov     rcx, [rsp+210h+var_1B8]; string
0x180045847  call    cs:__imp_WindowsDeleteString
0x18004584d  mov     [rsp+210h+var_1B8], r15
0x180045852  mov     rcx, [rsp+210h+string]; string
0x180045857  call    cs:__imp_WindowsDeleteString
0x18004585d  mov     [rsp+210h+string], r15
0x180045862  mov     rcx, [rsp+210h+var_1A8]; string
0x180045867  call    cs:__imp_WindowsDeleteString
0x18004586d  nop
0x18004586e  lea     rcx, [rbp+110h+var_180]; this
0x180045872  call    ??1RemoteLaunchUriAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::RemoteLaunchUriAsync::~RemoteLaunchUriAsync(void)
0x180045877  mov     eax, ebx
0x180045879  mov     rcx, [rbp+110h+var_30]
0x180045880  xor     rcx, rsp; StackCookie
0x180045883  call    __security_check_cookie
0x180045888  lea     r11, [rsp+210h+var_20]
0x180045890  mov     rbx, [r11+40h]
0x180045894  mov     rsi, [r11+48h]
0x180045898  mov     rsp, r11
0x18004589b  pop     r15
0x18004589d  pop     r14
0x18004589f  pop     r12
0x1800458a1  pop     rdi
0x1800458a2  pop     rbp
0x1800458a3  retn
```
