# MinUriExperienceLauncherModalImpl::LaunchAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,_GUID,IInspectable *,IInspectable *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,Windows::System::ILauncherUIOptions *,unsigned __int64)

- ea: `0x1800755c0`
- end: `0x18007595e`
- name: `?LaunchAsync@MinUriExperienceLauncherModalImpl@@UEAAJPEAUHSTRING__@@0000U_GUID@@PEAUIInspectable@@2UWindowId@WindowManagement@ApplicationModel@Internal@Windows@@PEAUILauncherUIOptions@System@9@_K@Z`
- size: `926`
- prototype: `int __high(HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, struct _GUID, struct IInspectable *, struct IInspectable *, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, struct Windows::System::ILauncherUIOptions *, unsigned __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x180027a10`
- `0x18003ab7c`
- `0x1800486d8`
- `0x1800596d8`
- `0x1800755c0`
- `0x180075964`
- `0x1800759b0`
- `0x180075b90`
- `0x180075c70`
- `0x180075ce4`
- `0x180075dc0`
- `0x18008a030`
- `0x1800bad30`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800758d7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800758d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800758a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800758a2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180075894`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180075894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075901`

## string_xrefs

- `0x18007568b`: `onecoreuap\shell\windows.system.launcher\inc\MinUriExperienceLauncherModalImpl.h`
- `0x1800756cd`: `onecoreuap\shell\windows.system.launcher\inc\MinUriExperienceLauncherModalImpl.h`
- `0x180075710`: `onecoreuap\shell\windows.system.launcher\inc\MinUriExperienceLauncherModalImpl.h`
- `0x1800757e7`: `onecoreuap\shell\windows.system.launcher\inc\MinUriExperienceLauncherModalImpl.h`
- `0x180075824`: `onecoreuap\shell\windows.system.launcher\inc\MinUriExperienceLauncherModalImpl.h`
- `0x1800758c3`: `onecoreuap\shell\windows.system.launcher\inc\MinUriExperienceLauncherModalImpl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MinUriExperienceLauncherModalImpl::LaunchAsync(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        __int64 a5,
        __int64 a6,
        _OWORD *a7,
        __int64 a8,
        __int64 (__fastcall ***a9)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // edi
  HSTRING *v19; // rax
  int v20; // eax
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v22; // rdi
  const unsigned __int16 *v23; // rax
  __int64 v24; // r14
  __int64 (__fastcall *v25)(__int64, HSTRING, HSTRING, HSTRING *); // rsi
  HSTRING v26; // rdi
  int v27; // eax
  int v28; // eax
  int v29; // esi
  HANDLE v31; // rbx
  signed int LastError; // eax
  HSTRING *v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  DWORD dwProcessId; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp-90h] BYREF
  int v40[2]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v42[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v43[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  *(_QWORD *)v40 = a8;
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v43);
  v43[0] = &LauncherServiceProvider::DoModalLaunch::`vftable';
  LauncherServiceProvider::DoModalLaunch::StartActivity((LauncherServiceProvider::DoModalLaunch *)v43);
  v39 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))a9;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v39);
  v37 = 0;
  v13 = **a9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v14 = v13(a9, &GUID_35367f5c_ff56_4f2c_b59b_c05f7716b07c, &v37);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\MinUriExperienceLauncherModalImpl.h",
      (const char *)(unsigned int)v14,
      (int)v33);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    LauncherServiceProvider::DoModalLaunch::~DoModalLaunch((LauncherServiceProvider::DoModalLaunch *)v43);
    return v15;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v37 + 56LL))(v37, a1, 1);
  v18 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\MinUriExperienceLauncherModalImpl.h",
      (const char *)(unsigned int)v16,
      (int)v33);
    v15 = v18;
    goto LABEL_11;
  }
  v38 = 0;
  v19 = Windows::Internal::StringReference::StringReference(v42, (const unsigned __int16 (*)[66])v17);
  v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>(
          *v19,
          &v38);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\MinUriExperienceLauncherModalImpl.h",
      (const char *)(unsigned int)v20,
      (int)v33);
  WindowsDeleteString(0);
  string = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
  v22 = WindowsGetStringRawBuffer(a3, 0);
  v23 = WindowsGetStringRawBuffer(a2, 0);
  GetActivationInfo(v23, v22, StringRawBuffer, 1, v33, &string);
  v36 = 0;
  v24 = v38;
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING *))(*(_QWORD *)v38 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  *(_OWORD *)v42 = *a7;
  v34 = v40[0];
  v26 = string;
  v27 = v25(v24, string, a2, v42);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\MinUriExperienceLauncherModalImpl.h",
      (const char *)(unsigned int)v27,
      v34);
  dwProcessId = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v36 + 48LL))(v36, &dwProcessId);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\MinUriExperienceLauncherModalImpl.h",
      (const char *)(unsigned int)v28,
      v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    WindowsDeleteString(v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v15 = v29;
    goto LABEL_11;
  }
  LauncherServiceProvider::DoModalLaunch::ActivationComplete<unsigned int &>((__int64)v43, (int *)&dwProcessId);
  v31 = OpenProcess(1u, 0, dwProcessId);
  *(_QWORD *)v40 = v31;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !v31 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\MinUriExperienceLauncherModalImpl.h",
      (const char *)(unsigned int)LastError,
      v34);
  TerminateProcess(v31, 0);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v43,
    0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  WindowsDeleteString(v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  LauncherServiceProvider::DoModalLaunch::~DoModalLaunch((LauncherServiceProvider::DoModalLaunch *)v43);
  return 0;
}

```

## disassembly

```asm
0x1800755c0  mov     [rsp-8+arg_10], rbx
0x1800755c5  push    rbp
0x1800755c6  push    rsi
0x1800755c7  push    rdi
0x1800755c8  push    r12
0x1800755ca  push    r13
0x1800755cc  push    r14
0x1800755ce  push    r15
0x1800755d0  lea     rbp, [rsp-110h]
0x1800755d8  sub     rsp, 210h
0x1800755df  mov     rax, cs:__security_cookie
0x1800755e6  xor     rax, rsp
0x1800755e9  mov     [rbp+140h+var_40], rax
0x1800755f0  mov     r14, r9
0x1800755f3  mov     r12, r8
0x1800755f6  mov     r15, rdx
0x1800755f9  mov     rsi, rcx
0x1800755fc  mov     r13, [rbp+140h+arg_30]
0x180075603  mov     rax, [rbp+140h+arg_38]
0x18007560a  mov     qword ptr [rsp+240h+var_1C8], rax
0x18007560f  lea     rdx, aDomodallaunch; "DoModalLaunch"
0x180075616  lea     rcx, [rbp+140h+var_190]; struct wil::details::IFailureCallback *
0x18007561a  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007561f  lea     rax, ??_7DoModalLaunch@LauncherServiceProvider@@6B@; const LauncherServiceProvider::DoModalLaunch::`vftable'
0x180075626  mov     [rbp+140h+var_190], rax
0x18007562a  lea     rcx, [rbp+140h+var_190]; this
0x18007562e  call    ?StartActivity@DoModalLaunch@LauncherServiceProvider@@QEAAXXZ; LauncherServiceProvider::DoModalLaunch::StartActivity(void)
0x180075633  nop
0x180075634  mov     rdi, [rbp+140h+arg_40]
0x18007563b  mov     [rsp+240h+var_1D0], rdi
0x180075640  lea     rcx, [rsp+240h+var_1D0]
0x180075645  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18007564a  nop
0x18007564b  mov     [rsp+240h+var_1E0], 0
0x180075654  mov     rax, [rdi]
0x180075657  mov     rbx, [rax]
0x18007565a  lea     rcx, [rsp+240h+var_1E0]
0x18007565f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075664  lea     r8, [rsp+240h+var_1E0]
0x180075669  lea     rdx, _GUID_35367f5c_ff56_4f2c_b59b_c05f7716b07c
0x180075670  mov     rcx, rdi
0x180075673  mov     rax, rbx
0x180075676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007567b  mov     ebx, eax
0x18007567d  test    eax, eax
0x18007567f  jns     short loc_1800756A1
0x180075681  mov     rcx, [rbp+148h]; this
0x180075688  mov     r9d, eax; char *
0x18007568b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.system.launc"...
0x180075692  mov     edx, 2Fh ; '/'; void *
0x180075697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007569c  jmp     loc_180075857
0x1800756a1  mov     rcx, [rsp+240h+var_1E0]
0x1800756a6  mov     ebx, 1
0x1800756ab  mov     rax, [rcx]
0x1800756ae  mov     r8d, ebx
0x1800756b1  mov     rdx, rsi
0x1800756b4  mov     rax, [rax+38h]
0x1800756b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756bd  mov     edi, eax
0x1800756bf  test    eax, eax
0x1800756c1  jns     short loc_1800756E3
0x1800756c3  mov     rcx, [rbp+148h]; this
0x1800756ca  mov     r9d, eax; char *
0x1800756cd  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.system.launc"...
0x1800756d4  lea     edx, [rbx+34h]; void *
0x1800756d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800756dc  mov     ebx, edi
0x1800756de  jmp     loc_180075857
0x1800756e3  mov     [rsp+240h+var_1D8], 0
0x1800756ec  lea     rcx, [rbp+140h+var_1B0]; string
0x1800756f0  call    ??$?0$0EC@@StringReference@Internal@Windows@@QEAA@AEAY0EC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[66])
0x1800756f5  lea     rdx, [rsp+240h+var_1D8]
0x1800756fa  mov     rcx, [rax]
0x1800756fd  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationActivationStatics@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationActivationStatics@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>)
0x180075702  mov     rcx, [rbp+148h]; this
0x180075709  test    eax, eax
0x18007570b  jns     short loc_180075722
0x18007570d  mov     r9d, eax; char *
0x180075710  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.system.launc"...
0x180075717  mov     edx, 38h ; '8'; void *
0x18007571c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075722  xor     ecx, ecx; string
0x180075724  call    cs:__imp_WindowsDeleteString
0x18007572a  mov     [rbp+140h+string], 0
0x180075732  xor     edx, edx; length
0x180075734  mov     rcx, r14; string
0x180075737  call    cs:__imp_WindowsGetStringRawBuffer
0x18007573d  mov     rsi, rax
0x180075740  xor     edx, edx; length
0x180075742  mov     rcx, r12; string
0x180075745  call    cs:__imp_WindowsGetStringRawBuffer
0x18007574b  mov     rdi, rax
0x18007574e  xor     edx, edx; length
0x180075750  mov     rcx, r15; string
0x180075753  call    cs:__imp_WindowsGetStringRawBuffer
0x180075759  lea     rcx, [rbp+140h+string]
0x18007575d  mov     [rsp+240h+var_218], rcx; HSTRING *
0x180075762  mov     r9b, bl; bool
0x180075765  mov     r8, rsi; unsigned __int16 *
0x180075768  mov     rdx, rdi; unsigned __int16 *
0x18007576b  mov     rcx, rax; unsigned __int16 *
0x18007576e  call    ?GetActivationInfo@@YAXPEBG00_NPEAPEAUHSTRING__@@2@Z; GetActivationInfo(ushort const *,ushort const *,ushort const *,bool,HSTRING__ * *,HSTRING__ * *)
0x180075773  xor     r12d, r12d
0x180075776  mov     [rsp+240h+var_1E8], r12
0x18007577b  mov     r14, [rsp+240h+var_1D8]
0x180075780  mov     rax, [r14]
0x180075783  mov     rsi, [rax+48h]
0x180075787  lea     rcx, [rsp+240h+var_1E8]
0x18007578c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075791  movups  xmm0, xmmword ptr [r13+0]
0x180075796  movdqu  xmmword ptr [rbp+140h+var_1B0], xmm0
0x18007579b  lea     rax, [rsp+240h+var_1E8]
0x1800757a0  mov     [rsp+240h+var_208], rax
0x1800757a5  mov     rdx, [rbp+140h+arg_58]
0x1800757ac  mov     [rsp+240h+var_210], rdx
0x1800757b1  mov     [rsp+240h+var_218], r12
0x1800757b6  mov     rax, qword ptr [rsp+240h+var_1C8]
0x1800757bb  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800757c0  lea     r9, [rbp+140h+var_1B0]
0x1800757c4  mov     r8, r15
0x1800757c7  mov     rdi, [rbp+140h+string]
0x1800757cb  mov     rdx, rdi
0x1800757ce  mov     rcx, r14
0x1800757d1  mov     rax, rsi
0x1800757d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757d9  mov     rcx, [rbp+148h]; this
0x1800757e0  test    eax, eax
0x1800757e2  jns     short loc_1800757F9
0x1800757e4  mov     r9d, eax; char *
0x1800757e7  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.system.launc"...
0x1800757ee  lea     edx, [r12+4Fh]; void *
0x1800757f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800757f9  mov     [rsp+240h+dwProcessId], r12d
0x1800757fe  mov     rcx, [rsp+240h+var_1E8]
0x180075803  mov     rax, [rcx]
0x180075806  lea     rdx, [rsp+240h+dwProcessId]
0x18007580b  mov     rax, [rax+30h]
0x18007580f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075814  mov     esi, eax
0x180075816  test    eax, eax
0x180075818  jns     short loc_18007587D
0x18007581a  mov     rcx, [rbp+148h]; this
0x180075821  mov     r9d, eax; char *
0x180075824  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.system.launc"...
0x18007582b  mov     edx, 52h ; 'R'; void *
0x180075830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075835  nop
0x180075836  lea     rcx, [rsp+240h+var_1E8]
0x18007583b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075840  nop
0x180075841  mov     rcx, rdi; string
0x180075844  call    cs:__imp_WindowsDeleteString
0x18007584a  nop
0x18007584b  lea     rcx, [rsp+240h+var_1D8]
0x180075850  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075855  mov     ebx, esi
0x180075857  lea     rcx, [rsp+240h+var_1E0]
0x18007585c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075861  nop
0x180075862  lea     rcx, [rsp+240h+var_1D0]
0x180075867  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007586c  nop
0x18007586d  lea     rcx, [rbp+140h+var_190]; this
0x180075871  call    ??1DoModalLaunch@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::DoModalLaunch::~DoModalLaunch(void)
0x180075876  mov     eax, ebx
0x180075878  jmp     loc_180075934
0x18007587d  lea     rdx, [rsp+240h+dwProcessId]
0x180075882  lea     rcx, [rbp+140h+var_190]
0x180075886  call    ??$ActivationComplete@AEAI@DoModalLaunch@LauncherServiceProvider@@QEAAXAEAI@Z; LauncherServiceProvider::DoModalLaunch::ActivationComplete<uint &>(uint &)
0x18007588b  mov     r8d, [rsp+240h+dwProcessId]; dwProcessId
0x180075890  xor     edx, edx; bInheritHandle
0x180075892  mov     ecx, ebx; dwDesiredAccess
0x180075894  call    cs:__imp_OpenProcess
0x18007589a  mov     rbx, rax
0x18007589d  mov     qword ptr [rsp+240h+var_1C8], rax
0x1800758a2  call    cs:__imp_GetLastError
0x1800758a8  test    eax, eax
0x1800758aa  jle     short loc_1800758B4
0x1800758ac  movzx   eax, ax
0x1800758af  or      eax, 80070000h
0x1800758b4  mov     rcx, [rbp+148h]; this
0x1800758bb  test    rbx, rbx
0x1800758be  jnz     short loc_1800758D2
0x1800758c0  mov     r9d, eax; char *
0x1800758c3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.system.launc"...
0x1800758ca  lea     edx, [rbx+56h]; void *
0x1800758cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800758d2  xor     edx, edx; uExitCode
0x1800758d4  mov     rcx, rbx; hProcess
0x1800758d7  call    cs:__imp_TerminateProcess
0x1800758dd  xor     edx, edx
0x1800758df  lea     rcx, [rbp+140h+var_190]
0x1800758e3  call    ?Stop@?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800758e8  lea     rcx, [rsp+240h+var_1C8]
0x1800758ed  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800758f2  nop
0x1800758f3  lea     rcx, [rsp+240h+var_1E8]
0x1800758f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800758fd  nop
0x1800758fe  mov     rcx, rdi; string
0x180075901  call    cs:__imp_WindowsDeleteString
0x180075907  nop
0x180075908  lea     rcx, [rsp+240h+var_1D8]
0x18007590d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075912  nop
0x180075913  lea     rcx, [rsp+240h+var_1E0]
0x180075918  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007591d  nop
0x18007591e  lea     rcx, [rsp+240h+var_1D0]
0x180075923  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075928  nop
0x180075929  lea     rcx, [rbp+140h+var_190]; this
0x18007592d  call    ??1DoModalLaunch@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::DoModalLaunch::~DoModalLaunch(void)
0x180075932  xor     eax, eax
0x180075934  mov     rcx, [rbp+140h+var_40]
0x18007593b  xor     rcx, rsp; StackCookie
0x18007593e  call    __security_check_cookie
0x180075943  mov     rbx, [rsp+240h+arg_10]
0x18007594b  add     rsp, 210h
0x180075952  pop     r15
0x180075954  pop     r14
0x180075956  pop     r13
0x180075958  pop     r12
0x18007595a  pop     rdi
0x18007595b  pop     rsi
0x18007595c  pop     rbp
0x18007595d  retn
```
