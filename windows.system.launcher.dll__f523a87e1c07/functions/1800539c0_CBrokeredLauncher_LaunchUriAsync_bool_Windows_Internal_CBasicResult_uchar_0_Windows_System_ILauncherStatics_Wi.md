# CBrokeredLauncher::_LaunchUriAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::System::ILauncherStatics *,Windows::Foundation::IUriRuntimeClass *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *)

- ea: `0x1800539c0`
- end: `0x180053e3f`
- name: `??$_LaunchUriAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@CBrokeredLauncher@@CA?AV?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherStatics@System@Windows@@PEAUIUriRuntimeClass@Foundation@6@PEAUILauncherOptions@56@PEAUITelemetryCorrelationVector@@@Z`
- size: `1151`
- prototype: `_QWORD *__fastcall(_QWORD *, struct Windows::System::ILauncherStatics *, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051ee0`
- `0x180053920`
- `0x18007cbf0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x1800210f8`
- `0x180040918`
- `0x180053018`
- `0x180053080`
- `0x1800530e4`
- `0x180053178`
- `0x180053200`
- `0x180053270`
- `0x1800533e4`
- `0x18005363c`
- `0x180053844`
- `0x1800539c0`
- `0x180054630`
- `0x180054710`
- `0x1800550d8`
- `0x180055194`
- `0x180055298`
- `0x180055490`
- `0x18005552c`
- `0x18005591c`
- `0x18005a524`
- `0x1800726f8`
- `0x18008a030`
- `0x1800e1608`
- `0x180105bec`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180053c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180053c0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053dbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053dbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053a68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053a68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053a26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053a26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053abf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053abf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dce`

## string_xrefs

- `0x180053a81`: `LaunchUri`
- `0x180053a4f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180053d2c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
_QWORD *__fastcall CBrokeredLauncher::_LaunchUriAsync<bool,Windows::Internal::CBasicResult<unsigned char,0>>(
        _QWORD *a1,
        struct Windows::System::ILauncherStatics *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  bool v8; // r12
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rdi
  const char *v12; // rbx
  void *v13; // rdx
  enum WELL_KNOWN_SID_TYPE v14; // ecx
  void **v15; // r9
  bool v16; // bl
  signed int v17; // r15d
  bool v18; // r15
  void *v19; // rdi
  unsigned __int16 *v20; // rbx
  LPVOID v21; // r14
  __int64 v22; // rcx
  DWORD ProcessId; // esi
  int v24; // r8d
  int v25; // ebx
  int Buffer; // [rsp+20h] [rbp-E0h]
  int Buffera; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+40h] [rbp-C0h] BYREF
  bool v30; // [rsp+41h] [rbp-BFh] BYREF
  bool IsCallingProcessLowIL; // [rsp+42h] [rbp-BEh]
  int v32[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v37; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v38[4]; // [rsp+78h] [rbp-88h] BYREF
  HWND v39; // [rsp+80h] [rbp-80h] BYREF
  int v40[2]; // [rsp+88h] [rbp-78h]
  HANDLE Process; // [rsp+90h] [rbp-70h] BYREF
  int v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 *v44; // [rsp+A8h] [rbp-58h]
  void *v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h] BYREF
  int v49; // [rsp+D0h] [rbp-30h]
  __int128 v50; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v51; // [rsp+E8h] [rbp-18h]
  DWORD v52; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v53; // [rsp+F8h] [rbp-8h]
  LPVOID v54; // [rsp+100h] [rbp+0h]
  LPVOID v55; // [rsp+108h] [rbp+8h] BYREF
  int v56; // [rsp+110h] [rbp+10h]
  bool v57; // [rsp+114h] [rbp+14h]
  _BYTE v58[40]; // [rsp+118h] [rbp+18h] BYREF
  HWND v59; // [rsp+140h] [rbp+40h]
  _QWORD v60[43]; // [rsp+148h] [rbp+48h] BYREF
  void **v61; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v62[272]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v63[8]; // [rsp+3B8h] [rbp+2B8h] BYREF
  _BYTE v64[48]; // [rsp+3C0h] [rbp+2C0h] BYREF
  void **v65; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v66[272]; // [rsp+3F8h] [rbp+2F8h] BYREF
  _BYTE v67[8]; // [rsp+508h] [rbp+408h] BYREF
  _BYTE v68[48]; // [rsp+510h] [rbp+410h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+498h]

  *(_QWORD *)v40 = a4;
  v47 = a3;
  v51 = a1;
  v46 = a5;
  v8 = 0;
  v36 = 0;
  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(a3, &string);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50D,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v10,
      Buffer);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = *(const char **)TelemetryCorrelationVectorServiceProvider::Increment(&pv, a5);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v61);
  v61 = &LauncherDesktopProvider::LaunchUri::`vftable';
  LauncherDesktopProvider::LaunchUri::StartActivityWithCorrelationVector(
    (LauncherDesktopProvider::LaunchUri *)&v61,
    v12,
    StringRawBuffer);
  if ( pv )
    CoTaskMemFree(pv);
  v33 = 0;
  v37 = 0;
  pv = 0;
  v29 = 0;
  *(_QWORD *)v38 = 0;
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(
    a2,
    (enum PROCESS_UICONTEXT *)&v33,
    &v37,
    &pv,
    v38,
    &v29);
  IsCallingProcessLowIL = CBrokeredLauncher::IsCallingProcessLowIL(a2);
  v16 = v29;
  if ( v29 )
  {
    v32[0] = 0;
    v17 = CheckAndGetCapability(v14, v13, v32, v15);
    if ( v17 >= 0 )
      v17 = v32[0] == 0 ? 0x80070005 : 0;
    v18 = v17 >= 0;
  }
  else
  {
    v18 = 1;
  }
  v30 = 0;
  v39 = 0;
  v19 = *(void **)v38;
  if ( v16 && !CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow() )
  {
    *(_QWORD *)v32 = v19;
    LauncherDesktopProvider::LaunchUri::LaunchAttemptedFromModernAppOnNonUIThread<unsigned short const *>(&v61, v32);
    CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(a2, &v30, &v39);
    v8 = v30;
  }
  wil::GetProcessHandleForClientOfObject(&Process, a2, 4096);
  v20 = v37;
  v44 = v37;
  v37 = 0;
  v45 = v19;
  *(_QWORD *)v38 = 0;
  v21 = pv;
  pv = 0;
  *(_QWORD *)v32 = v21;
  LOBYTE(v22) = v29;
  v48 = CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(
          v22,
          *(_QWORD *)v40);
  v49 = 7;
  v50 = 0;
  ProcessId = GetProcessId(Process);
  LauncherDesktopProvider::LaunchUri::Split(&v61, &v65);
  *a1 = 0;
  v36 = 1;
  v52 = ProcessId;
  v53 = v20;
  v44 = 0;
  v54 = v19;
  v45 = 0;
  *(_QWORD *)v32 = 0;
  v55 = v21;
  v56 = v33;
  v57 = v18;
  Windows::Internal::AsyncWindowOperation::AsyncWindowOperation(
    (Windows::Internal::AsyncWindowOperation *)v58,
    (const struct Windows::Internal::AsyncWindowOperation *)&v48);
  v58[32] = v29;
  v58[33] = IsCallingProcessLowIL;
  v58[34] = v8;
  v59 = v39;
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v60,
    &v65);
  v60[0] = &LauncherDesktopProvider::LaunchUri::`vftable';
  v42 = 1;
  v43 = 128;
  v25 = Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IUriRuntimeClass,Windows::System::ILauncherOptions,ITelemetryCorrelationVector,_lambda_12a93b8d7660d2cdca714be35ee02a8e_>(
          (unsigned int)&v42,
          (_DWORD)a1,
          v24,
          v47,
          *(__int64 *)v40,
          v46,
          (__int64)&v52);
  LauncherDesktopProvider::LaunchUri::~LaunchUri((LauncherDesktopProvider::LaunchUri *)v60);
  Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation((Windows::Internal::AsyncWindowOperation *)v58);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v55);
  CoTaskMemFree(v54);
  CoTaskMemFree(v53);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v61,
    (unsigned int)v25);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v25,
      Buffera);
  v65 = &LauncherDesktopProvider::LaunchUri::`vftable';
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v65);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v68);
  wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v67);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v50 + 8);
  if ( (_QWORD)v50 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50 + 16LL))(v50);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v32);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  if ( Process )
    CloseHandle(Process);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  v61 = &LauncherDesktopProvider::LaunchUri::`vftable';
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v61);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v64);
  wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v63);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(v62);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x1800539c0  push    rbp
0x1800539c2  push    rbx
0x1800539c3  push    rsi
0x1800539c4  push    rdi
0x1800539c5  push    r12
0x1800539c7  push    r13
0x1800539c9  push    r14
0x1800539cb  push    r15
0x1800539cd  lea     rbp, [rsp-458h]
0x1800539d5  sub     rsp, 558h
0x1800539dc  mov     rax, cs:__security_cookie
0x1800539e3  xor     rax, rsp
0x1800539e6  mov     [rbp+490h+var_50], rax
0x1800539ed  mov     qword ptr [rbp+490h+var_508], r9
0x1800539f1  mov     rdi, r8
0x1800539f4  mov     [rbp+490h+var_4D0], r8
0x1800539f8  mov     rsi, rdx
0x1800539fb  mov     r13, rcx
0x1800539fe  mov     [rbp+490h+var_4A8], rcx
0x180053a02  mov     r14, [rbp+490h+arg_20]
0x180053a09  mov     [rbp+490h+var_4D8], r14
0x180053a0d  xor     r12d, r12d
0x180053a10  mov     [rsp+590h+var_528], r12d
0x180053a15  mov     [rsp+590h+string], r12
0x180053a1a  mov     rax, [r8]
0x180053a1d  mov     rbx, [rax+88h]
0x180053a24  xor     ecx, ecx; string
0x180053a26  call    cs:__imp_WindowsDeleteString
0x180053a2c  mov     [rsp+590h+string], r12
0x180053a31  lea     rdx, [rsp+590h+string]
0x180053a36  mov     rcx, rdi
0x180053a39  mov     rax, rbx
0x180053a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a41  mov     rcx, [rbp+498h]; this
0x180053a48  test    eax, eax
0x180053a4a  jns     short loc_180053A61
0x180053a4c  mov     r9d, eax; char *
0x180053a4f  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180053a56  mov     edx, 50Dh; void *
0x180053a5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053a61  xor     edx, edx; length
0x180053a63  mov     rcx, [rsp+590h+string]; string
0x180053a68  call    cs:__imp_WindowsGetStringRawBuffer
0x180053a6e  mov     rdi, rax
0x180053a71  mov     rdx, r14
0x180053a74  lea     rcx, [rsp+590h+pv]
0x180053a79  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180053a7e  mov     rbx, [rax]
0x180053a81  lea     rdx, aLaunchuri_0; "LaunchUri"
0x180053a88  lea     rcx, [rbp+490h+var_2F0]; struct wil::details::IFailureCallback *
0x180053a8f  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180053a94  lea     rax, ??_7LaunchUri@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::LaunchUri::`vftable'
0x180053a9b  mov     [rbp+490h+var_2F0], rax
0x180053aa2  mov     r8, rdi; unsigned __int16 *
0x180053aa5  mov     rdx, rbx; char *
0x180053aa8  lea     rcx, [rbp+490h+var_2F0]; this
0x180053aaf  call    ?StartActivityWithCorrelationVector@LaunchUri@LauncherDesktopProvider@@QEAAXPEBDPEBG@Z; LauncherDesktopProvider::LaunchUri::StartActivityWithCorrelationVector(char const *,ushort const *)
0x180053ab4  nop
0x180053ab5  mov     rcx, [rsp+590h+pv]; pv
0x180053aba  test    rcx, rcx
0x180053abd  jz      short loc_180053AC5
0x180053abf  call    cs:__imp_CoTaskMemFree
0x180053ac5  mov     [rsp+590h+var_540], r12d
0x180053aca  mov     [rsp+590h+var_520], r12
0x180053acf  mov     [rsp+590h+pv], r12
0x180053ad4  mov     [rsp+590h+var_550], r12b
0x180053ad9  mov     qword ptr [rsp+590h+var_518], r12
0x180053ade  xor     ecx, ecx; pv
0x180053ae0  call    cs:__imp_CoTaskMemFree
0x180053ae6  xor     ecx, ecx; pv
0x180053ae8  call    cs:__imp_CoTaskMemFree
0x180053aee  lea     rax, [rsp+590h+var_550]
0x180053af3  mov     [rsp+590h+var_568], rax; bool *
0x180053af8  lea     rax, [rsp+590h+var_518]
0x180053afd  mov     qword ptr [rsp+590h+Buffer], rax; Buffer
0x180053b02  lea     r9, [rsp+590h+pv]; void **
0x180053b07  lea     r8, [rsp+590h+var_520]; unsigned __int16 **
0x180053b0c  lea     rdx, [rsp+590h+var_540]; enum PROCESS_UICONTEXT *
0x180053b11  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180053b14  call    ?RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAW4PROCESS_UICONTEXT@@PEAPEAGPEAPEAX2PEA_N@Z; CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(Windows::System::ILauncherStatics *,PROCESS_UICONTEXT *,ushort * *,void * *,ushort * *,bool *)
0x180053b19  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180053b1c  call    ?IsCallingProcessLowIL@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::IsCallingProcessLowIL(Windows::System::ILauncherStatics *)
0x180053b21  mov     [rsp+590h+var_54E], al
0x180053b25  mov     bl, [rsp+590h+var_550]
0x180053b29  test    bl, bl
0x180053b2b  jz      short loc_180053B60
0x180053b2d  mov     [rsp+590h+var_548], r12d
0x180053b32  lea     r8, [rsp+590h+var_548]; int *
0x180053b37  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x180053b3c  mov     r15d, eax
0x180053b3f  test    eax, eax
0x180053b41  js      short loc_180053B56
0x180053b43  mov     eax, [rsp+590h+var_548]
0x180053b47  neg     eax
0x180053b49  sbb     r15d, r15d
0x180053b4c  not     r15d
0x180053b4f  and     r15d, 80070005h
0x180053b56  shr     r15d, 1Fh
0x180053b5a  xor     r15b, 1
0x180053b5e  jmp     short loc_180053B63
0x180053b60  mov     r15b, 1
0x180053b63  mov     [rsp+590h+var_54F], r12b
0x180053b68  xor     r14d, r14d
0x180053b6b  mov     [rbp+490h+var_510], r14
0x180053b6f  mov     rdi, qword ptr [rsp+590h+var_518]
0x180053b74  test    bl, bl
0x180053b76  jz      short loc_180053BAD
0x180053b78  call    ?TryGetWindowIdOfCallerViaCoreWindow@CBrokeredLauncher@@CAKXZ; CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow(void)
0x180053b7d  test    eax, eax
0x180053b7f  jnz     short loc_180053BAD
0x180053b81  mov     qword ptr [rsp+590h+var_548], rdi
0x180053b86  lea     rdx, [rsp+590h+var_548]
0x180053b8b  lea     rcx, [rbp+490h+var_2F0]
0x180053b92  call    ??$LaunchAttemptedFromModernAppOnNonUIThread@PEBG@LaunchUri@LauncherDesktopProvider@@QEAAX$$QEAPEBG@Z; LauncherDesktopProvider::LaunchUri::LaunchAttemptedFromModernAppOnNonUIThread<ushort const *>(ushort const * &&)
0x180053b97  lea     r8, [rbp+490h+var_510]; HWND *
0x180053b9b  lea     rdx, [rsp+590h+var_54F]; bool *
0x180053ba0  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180053ba3  call    ?ValidateOrGetQuirkEnabledCallerWindow@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEA_NPEAPEAUHWND__@@@Z; CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(Windows::System::ILauncherStatics *,bool *,HWND__ * *)
0x180053ba8  mov     r12b, [rsp+590h+var_54F]
0x180053bad  mov     r8d, 1000h
0x180053bb3  mov     rdx, rsi
0x180053bb6  lea     rcx, [rbp+490h+Process]
0x180053bba  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x180053bbf  nop
0x180053bc0  mov     rbx, [rsp+590h+var_520]
0x180053bc5  mov     [rbp+490h+var_4E8], rbx
0x180053bc9  mov     [rsp+590h+var_520], r14
0x180053bce  mov     [rbp+490h+var_4E0], rdi
0x180053bd2  mov     qword ptr [rsp+590h+var_518], r14
0x180053bd7  mov     r14, [rsp+590h+pv]
0x180053bdc  mov     [rsp+590h+pv], 0
0x180053be5  mov     qword ptr [rsp+590h+var_548], r14
0x180053bea  mov     rdx, qword ptr [rbp+490h+var_508]
0x180053bee  mov     cl, [rsp+590h+var_550]
0x180053bf2  call    ??$GetOwnerWindowFromLauncherOptionsIfNeeded@UILauncherOptions@System@Windows@@@CBrokeredLauncher@@CAPEAUHWND__@@_NPEAUILauncherOptions@System@Windows@@@Z; CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(bool,Windows::System::ILauncherOptions *)
0x180053bf7  mov     [rbp+490h+var_4C8], rax
0x180053bfb  mov     [rbp+490h+var_4C0], 7
0x180053c02  xorps   xmm0, xmm0
0x180053c05  movdqu  [rbp+490h+var_4B8], xmm0
0x180053c0a  mov     rcx, [rbp+490h+Process]; Process
0x180053c0e  call    cs:__imp_GetProcessId
0x180053c14  mov     esi, eax
0x180053c16  lea     rdx, [rbp+490h+var_1A0]
0x180053c1d  lea     rcx, [rbp+490h+var_2F0]
0x180053c24  call    ?Split@LaunchUri@LauncherDesktopProvider@@QEAA?AV12@XZ; LauncherDesktopProvider::LaunchUri::Split(void)
0x180053c29  nop
0x180053c2a  mov     qword ptr [r13+0], 0
0x180053c32  mov     [rsp+590h+var_528], 1
0x180053c3a  mov     [rbp+490h+var_4A0], esi
0x180053c3d  mov     [rbp+490h+var_498], rbx
0x180053c41  xor     esi, esi
0x180053c43  mov     [rbp+490h+var_4E8], rsi
0x180053c47  mov     [rbp+490h+var_490], rdi
0x180053c4b  mov     [rbp+490h+var_4E0], rsi
0x180053c4f  mov     qword ptr [rsp+590h+var_548], rsi
0x180053c54  mov     [rbp+490h+var_488], r14
0x180053c58  mov     eax, [rsp+590h+var_540]
0x180053c5c  mov     [rbp+490h+var_480], eax
0x180053c5f  mov     [rbp+490h+var_47C], r15b
0x180053c63  lea     rdx, [rbp+490h+var_4C8]; struct Windows::Internal::AsyncWindowOperation *
0x180053c67  lea     rcx, [rbp+490h+var_478]; this
0x180053c6b  call    ??0AsyncWindowOperation@Internal@Windows@@QEAA@AEBV012@@Z; Windows::Internal::AsyncWindowOperation::AsyncWindowOperation(Windows::Internal::AsyncWindowOperation const &)
0x180053c70  mov     al, [rsp+590h+var_550]
0x180053c74  mov     [rbp+490h+var_458], al
0x180053c77  mov     al, [rsp+590h+var_54E]
0x180053c7b  mov     [rbp+490h+var_457], al
0x180053c7e  mov     [rbp+490h+var_456], r12b
0x180053c82  mov     rax, [rbp+490h+var_510]
0x180053c86  mov     [rbp+490h+var_450], rax
0x180053c8a  lea     rdx, [rbp+490h+var_1A0]
0x180053c91  lea     rcx, [rbp+490h+var_448]
0x180053c95  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180053c9a  lea     rdi, ??_7LaunchUri@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::LaunchUri::`vftable'
0x180053ca1  mov     [rbp+490h+var_448], rdi
0x180053ca5  mov     [rbp+490h+var_4F8], 1
0x180053cac  mov     [rbp+490h+var_4F4], 80h
0x180053cb4  lea     rax, [rbp+490h+var_4A0]
0x180053cb8  mov     [rsp+590h+var_560], rax
0x180053cbd  mov     rax, [rbp+490h+var_4D8]
0x180053cc1  mov     [rsp+590h+var_568], rax
0x180053cc6  mov     rax, qword ptr [rbp+490h+var_508]
0x180053cca  mov     qword ptr [rsp+590h+Buffer], rax; int
0x180053ccf  mov     r9, [rbp+490h+var_4D0]
0x180053cd3  mov     rdx, r13
0x180053cd6  lea     rcx, [rbp+490h+var_4F8]
0x180053cda  call    ??$MakeStagedAsyncOperation@V?$CBasicResult@E$0A@@Internal@Windows@@_NVComTaskPoolHandler@23@UIUriRuntimeClass@Foundation@3@UILauncherOptions@System@3@UITelemetryCorrelationVector@@V_lambda_12a93b8d7660d2cdca714be35ee02a8e_@@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@_N@Foundation@1@W4TrustLevel@@PEAUIUriRuntimeClass@41@PEAUILauncherOptions@System@1@PEAUITelemetryCorrelationVector@@$$QEAV_lambda_12a93b8d7660d2cdca714be35ee02a8e_@@@Z; Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<uchar,0>,bool,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IUriRuntimeClass,Windows::System::ILauncherOptions,ITelemetryCorrelationVector,_lambda_12a93b8d7660d2cdca714be35ee02a8e_>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<bool> * *,TrustLevel,Windows::Foundation::IUriRuntimeClass *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,_lambda_12a93b8d7660d2cdca714be35ee02a8e_ &&)
0x180053cdf  mov     ebx, eax
0x180053ce1  lea     rcx, [rbp+490h+var_448]; this
0x180053ce5  call    ??1LaunchUri@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchUri::~LaunchUri(void)
0x180053cea  lea     rcx, [rbp+490h+var_478]; this
0x180053cee  call    ??1AsyncWindowOperation@Internal@Windows@@QEAA@XZ; Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation(void)
0x180053cf3  lea     rcx, [rbp+490h+var_488]
0x180053cf7  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180053cfc  mov     rcx, [rbp+490h+var_490]; pv
0x180053d00  call    cs:__imp_CoTaskMemFree
0x180053d06  mov     rcx, [rbp+490h+var_498]; pv
0x180053d0a  call    cs:__imp_CoTaskMemFree
0x180053d10  mov     edx, ebx
0x180053d12  lea     rcx, [rbp+490h+var_2F0]
0x180053d19  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180053d1e  mov     rcx, [rbp+498h]; this
0x180053d25  test    ebx, ebx
0x180053d27  jns     short loc_180053D3E
0x180053d29  mov     r9d, ebx; char *
0x180053d2c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180053d33  mov     edx, 59Fh; void *
0x180053d38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053d3e  mov     [rbp+490h+var_1A0], rdi
0x180053d45  lea     rcx, [rbp+490h+var_1A0]
0x180053d4c  call    ?Destroy@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180053d51  lea     rcx, [rbp+490h+var_80]; this
0x180053d58  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180053d5d  lea     rcx, [rbp+490h+var_88]
0x180053d64  call    ?reset@?$shared_object@V?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180053d69  lea     rcx, [rbp+490h+var_198]
0x180053d70  call    ??1?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180053d75  nop
0x180053d76  lea     rcx, [rbp+490h+var_4B8+8]
0x180053d7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180053d7f  nop
0x180053d80  mov     rcx, qword ptr [rbp+490h+var_4B8]
0x180053d84  test    rcx, rcx
0x180053d87  jz      short loc_180053D96
0x180053d89  mov     rax, [rcx]
0x180053d8c  mov     rax, [rax+10h]
0x180053d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d95  nop
0x180053d96  lea     rcx, [rsp+590h+var_548]
0x180053d9b  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180053da0  nop
0x180053da1  xor     ecx, ecx; pv
0x180053da3  call    cs:__imp_CoTaskMemFree
0x180053da9  nop
0x180053daa  xor     ecx, ecx; pv
0x180053dac  call    cs:__imp_CoTaskMemFree
0x180053db2  nop
0x180053db3  mov     rcx, [rbp+490h+Process]; hObject
0x180053db7  test    rcx, rcx
0x180053dba  jz      short loc_180053DC3
0x180053dbc  call    cs:__imp_CloseHandle
0x180053dc2  nop
0x180053dc3  xor     ecx, ecx; pv
0x180053dc5  call    cs:__imp_CoTaskMemFree
0x180053dcb  nop
0x180053dcc  xor     ecx, ecx; pv
0x180053dce  call    cs:__imp_CoTaskMemFree
0x180053dd4  nop
0x180053dd5  mov     [rbp+490h+var_2F0], rdi
0x180053ddc  lea     rcx, [rbp+490h+var_2F0]
0x180053de3  call    ?Destroy@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180053de8  lea     rcx, [rbp+490h+var_1D0]; this
0x180053def  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180053df4  lea     rcx, [rbp+490h+var_1D8]
0x180053dfb  call    ?reset@?$shared_object@V?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180053e00  lea     rcx, [rbp+490h+var_2E8]
0x180053e07  call    ??1?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180053e0c  nop
0x180053e0d  mov     rcx, [rsp+590h+string]; string
0x180053e12  call    cs:__imp_WindowsDeleteString
0x180053e18  mov     rax, r13
0x180053e1b  mov     rcx, [rbp+490h+var_50]
0x180053e22  xor     rcx, rsp; StackCookie
0x180053e25  call    __security_check_cookie
0x180053e2a  add     rsp, 558h
0x180053e31  pop     r15
0x180053e33  pop     r14
0x180053e35  pop     r13
0x180053e37  pop     r12
0x180053e39  pop     rdi
0x180053e3a  pop     rsi
0x180053e3b  pop     rbx
0x180053e3c  pop     rbp
0x180053e3d  retn
```
