# CBrokeredLauncher::_LaunchUriAsync<Windows::System::LaunchUriStatus,Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3>>(Windows::System::ILauncherStatics *,Windows::Foundation::IUriRuntimeClass *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *)

- ea: `0x18005101c`
- end: `0x180051415`
- name: `??$_LaunchUriAsync@W4LaunchUriStatus@System@Windows@@V?$CBasicResult@W4LaunchUriStatus@System@Windows@@$02@Internal@3@@CBrokeredLauncher@@CA?AV?$ComPtr@U?$IAsyncOperation@W4LaunchUriStatus@System@Windows@@@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherStatics@System@Windows@@PEAUIUriRuntimeClass@Foundation@6@PEAUILauncherOptions@56@PEAUITelemetryCorrelationVector@@@Z`
- size: `1017`
- prototype: `_QWORD *__fastcall(_QWORD *, struct Windows::System::ILauncherStatics *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180050d60`
- `0x180050f10`

## callees

- `0x18000f194`
- `0x180040918`
- `0x180042254`
- `0x18005042c`
- `0x180050e68`
- `0x18005101c`
- `0x180053018`
- `0x180053080`
- `0x1800530e4`
- `0x180053200`
- `0x180053270`
- `0x1800533e4`
- `0x18005363c`
- `0x180053800`
- `0x180053844`
- `0x1800545d8`
- `0x180054710`
- `0x1800550d8`
- `0x18005591c`
- `0x18005a524`
- `0x1800726f8`
- `0x18008a030`
- `0x18008dee8`
- `0x1800e07c0`
- `0x1800e1608`
- `0x180105bec`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180051248`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180051248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800510c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800510c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800513e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800513e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005111f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005139f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005111f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005139f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513cf`

## string_xrefs

- `0x1800510ac`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180051369`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
_QWORD *__fastcall CBrokeredLauncher::_LaunchUriAsync<enum Windows::System::LaunchUriStatus,Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>>(
        _QWORD *a1,
        struct Windows::System::ILauncherStatics *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  bool v8; // r13
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  char **v11; // rax
  void *v12; // rdx
  enum WELL_KNOWN_SID_TYPE v13; // ecx
  void **v14; // r9
  bool v15; // bl
  signed int v16; // r15d
  bool v17; // r15
  __int64 v18; // rdi
  unsigned __int16 *v19; // rbx
  void *v20; // r14
  __int64 v21; // rcx
  DWORD ProcessId; // esi
  void *v23; // rax
  __int64 v24; // rax
  int v25; // ebx
  int Buffer; // [rsp+20h] [rbp-E0h]
  int Buffera; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+30h] [rbp-D0h] BYREF
  bool v30; // [rsp+31h] [rbp-CFh] BYREF
  bool IsCallingProcessLowIL; // [rsp+32h] [rbp-CEh]
  int v32[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v33; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v34[4]; // [rsp+48h] [rbp-B8h] BYREF
  void *v35; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  void *v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  HWND v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h]
  HANDLE Process; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+B8h] [rbp-48h] BYREF
  int v49; // [rsp+C0h] [rbp-40h]
  __int128 v50; // [rsp+C8h] [rbp-38h]
  _QWORD *v51; // [rsp+D8h] [rbp-28h]
  DWORD v52; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v53; // [rsp+E8h] [rbp-18h]
  __int64 v54; // [rsp+F0h] [rbp-10h]
  void *v55; // [rsp+F8h] [rbp-8h]
  int v56; // [rsp+100h] [rbp+0h]
  bool v57; // [rsp+104h] [rbp+4h]
  _BYTE v58[40]; // [rsp+108h] [rbp+8h] BYREF
  HWND v59; // [rsp+130h] [rbp+30h]
  void **v60; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v61[336]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v62[336]; // [rsp+3E0h] [rbp+2E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+488h]

  v40 = a4;
  v47 = a3;
  v51 = a1;
  v46 = a5;
  v8 = 0;
  v38 = 0;
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
  *(_QWORD *)v34 = WindowsGetStringRawBuffer(string, 0);
  v11 = (char **)TelemetryCorrelationVectorServiceProvider::Increment(&v33, a5);
  LauncherDesktopProvider::LaunchUri::StartWithCorrelationVector<unsigned short const *>(
    (LauncherDesktopProvider::LaunchUri *)v61,
    *v11);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v33);
  LODWORD(v37) = 0;
  v33 = 0;
  v35 = 0;
  v29 = 0;
  *(_QWORD *)v34 = 0;
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(
    a2,
    (enum PROCESS_UICONTEXT *)&v37,
    &v33,
    &v35,
    v34,
    &v29);
  IsCallingProcessLowIL = CBrokeredLauncher::IsCallingProcessLowIL(a2);
  v15 = v29;
  if ( v29 )
  {
    v32[0] = 0;
    v16 = CheckAndGetCapability(v13, v12, v32, v14);
    if ( v16 >= 0 )
      v16 = v32[0] == 0 ? 0x80070005 : 0;
    v17 = v16 >= 0;
  }
  else
  {
    v17 = 1;
  }
  v30 = 0;
  v39 = 0;
  v18 = *(_QWORD *)v34;
  if ( v15 && !CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow() )
  {
    *(_QWORD *)v32 = v18;
    LauncherDesktopProvider::LaunchUri::LaunchAttemptedFromModernAppOnNonUIThread<unsigned short const *>(v61, v32);
    CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(a2, &v30, &v39);
    v8 = v30;
  }
  wil::GetProcessHandleForClientOfObject(&Process, a2, 4096);
  v19 = v33;
  v44 = v33;
  v33 = 0;
  v45 = v18;
  *(_QWORD *)v34 = 0;
  v20 = v35;
  v35 = 0;
  *(_QWORD *)v32 = v20;
  LOBYTE(v21) = v29;
  v48 = CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(v21, v40);
  v49 = 7;
  v50 = 0;
  ProcessId = GetProcessId(Process);
  LauncherDesktopProvider::LaunchUri::Split(v61, v62);
  *a1 = 0;
  v38 = 1;
  v52 = ProcessId;
  v53 = v19;
  v44 = 0;
  v54 = v18;
  v45 = 0;
  *(_QWORD *)v32 = 0;
  v55 = v20;
  v56 = (int)v37;
  v57 = v17;
  Windows::Internal::AsyncWindowOperation::AsyncWindowOperation(
    (Windows::Internal::AsyncWindowOperation *)v58,
    (const struct Windows::Internal::AsyncWindowOperation *)&v48);
  v58[32] = v29;
  v58[33] = IsCallingProcessLowIL;
  v58[34] = v8;
  v59 = v39;
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v60,
    v62);
  v60 = &LauncherDesktopProvider::LaunchUri::`vftable';
  v42 = 1;
  v43 = 128;
  v23 = operator new(0x1D8u, (const struct std::nothrow_t *)&std::nothrow);
  v37 = v23;
  if ( v23 )
    v24 = Windows::Internal::COperationLambdaVar<1,_lambda_34074e6b262c35511414209380769e3f_,Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>,Windows::Foundation::IUriRuntimeClass,Windows::System::ILauncherOptions,ITelemetryCorrelationVector>::COperationLambdaVar<1,_lambda_34074e6b262c35511414209380769e3f_,Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>,Windows::Foundation::IUriRuntimeClass,Windows::System::ILauncherOptions,ITelemetryCorrelationVector>(
            (__int64)v23,
            (__int64)&v52,
            v47,
            v40,
            v46);
  else
    v24 = 0;
  v25 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<enum Windows::System::LaunchUriStatus,3>,enum Windows::System::LaunchUriStatus,Windows::Internal::ComTaskPoolHandler>(
          &v42,
          a1,
          1,
          v24);
  _lambda_12a93b8d7660d2cdca714be35ee02a8e_::~_lambda_12a93b8d7660d2cdca714be35ee02a8e_((_lambda_12a93b8d7660d2cdca714be35ee02a8e_ *)&v52);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v61,
    (unsigned int)v25);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v25,
      Buffera);
  LauncherDesktopProvider::LaunchUri::~LaunchUri((LauncherDesktopProvider::LaunchUri *)v62);
  Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation((Windows::Internal::AsyncWindowOperation *)&v48);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v32);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  CoTaskMemFree(0);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v35);
  CoTaskMemFree(0);
  LauncherDesktopProvider::LaunchUri::~LaunchUri((LauncherDesktopProvider::LaunchUri *)v61);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x18005101c  push    rbp
0x18005101e  push    rbx
0x18005101f  push    rsi
0x180051020  push    rdi
0x180051021  push    r12
0x180051023  push    r13
0x180051025  push    r14
0x180051027  push    r15
0x180051029  lea     rbp, [rsp-448h]
0x180051031  sub     rsp, 548h
0x180051038  mov     rax, cs:__security_cookie
0x18005103f  xor     rax, rsp
0x180051042  mov     [rbp+480h+var_50], rax
0x180051049  mov     [rsp+580h+var_508], r9
0x18005104e  mov     rdi, r8
0x180051051  mov     [rbp+480h+var_4D0], r8
0x180051055  mov     rsi, rdx
0x180051058  mov     r12, rcx
0x18005105b  mov     [rbp+480h+var_4A8], rcx
0x18005105f  mov     r14, [rbp+480h+arg_20]
0x180051066  mov     [rbp+480h+var_4D8], r14
0x18005106a  xor     r13d, r13d
0x18005106d  mov     [rsp+580h+var_518], r13d
0x180051072  mov     [rsp+580h+string], r13
0x180051077  mov     rax, [r8]
0x18005107a  mov     rbx, [rax+88h]
0x180051081  xor     ecx, ecx; string
0x180051083  call    cs:__imp_WindowsDeleteString
0x180051089  mov     [rsp+580h+string], r13
0x18005108e  lea     rdx, [rsp+580h+string]
0x180051093  mov     rcx, rdi
0x180051096  mov     rax, rbx
0x180051099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005109e  mov     rcx, [rbp+488h]; this
0x1800510a5  test    eax, eax
0x1800510a7  jns     short loc_1800510BE
0x1800510a9  mov     r9d, eax; char *
0x1800510ac  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800510b3  mov     edx, 50Dh; void *
0x1800510b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800510be  xor     edx, edx; length
0x1800510c0  mov     rcx, [rsp+580h+string]; string
0x1800510c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800510cb  mov     qword ptr [rsp+580h+var_538], rax
0x1800510d0  mov     rdx, r14
0x1800510d3  lea     rcx, [rsp+580h+var_540]
0x1800510d8  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x1800510dd  lea     r8, [rsp+580h+var_538]
0x1800510e2  mov     rdx, [rax]; char *
0x1800510e5  lea     rcx, [rbp+480h+var_2F0]; this
0x1800510ec  call    ??$StartWithCorrelationVector@PEBG@LaunchUri@LauncherDesktopProvider@@SA?AV01@PEBD$$QEAPEBG@Z; LauncherDesktopProvider::LaunchUri::StartWithCorrelationVector<ushort const *>(char const *,ushort const * &&)
0x1800510f1  nop
0x1800510f2  lea     rcx, [rsp+580h+var_540]
0x1800510f7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800510fc  mov     dword ptr [rsp+580h+var_520], r13d
0x180051101  mov     [rsp+580h+var_540], r13
0x180051106  mov     [rsp+580h+var_530], r13
0x18005110b  mov     [rsp+580h+var_550], r13b
0x180051110  mov     qword ptr [rsp+580h+var_538], r13
0x180051115  xor     ecx, ecx; pv
0x180051117  call    cs:__imp_CoTaskMemFree
0x18005111d  xor     ecx, ecx; pv
0x18005111f  call    cs:__imp_CoTaskMemFree
0x180051125  lea     rax, [rsp+580h+var_550]
0x18005112a  mov     [rsp+580h+var_558], rax; bool *
0x18005112f  lea     rax, [rsp+580h+var_538]
0x180051134  mov     qword ptr [rsp+580h+Buffer], rax; int
0x180051139  lea     r9, [rsp+580h+var_530]; void **
0x18005113e  lea     r8, [rsp+580h+var_540]; unsigned __int16 **
0x180051143  lea     rdx, [rsp+580h+var_520]; enum PROCESS_UICONTEXT *
0x180051148  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x18005114b  call    ?RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAW4PROCESS_UICONTEXT@@PEAPEAGPEAPEAX2PEA_N@Z; CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(Windows::System::ILauncherStatics *,PROCESS_UICONTEXT *,ushort * *,void * *,ushort * *,bool *)
0x180051150  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180051153  call    ?IsCallingProcessLowIL@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::IsCallingProcessLowIL(Windows::System::ILauncherStatics *)
0x180051158  mov     [rsp+580h+var_54E], al
0x18005115c  mov     bl, [rsp+580h+var_550]
0x180051160  test    bl, bl
0x180051162  jz      short loc_180051197
0x180051164  mov     [rsp+580h+var_548], r13d
0x180051169  lea     r8, [rsp+580h+var_548]; int *
0x18005116e  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x180051173  mov     r15d, eax
0x180051176  test    eax, eax
0x180051178  js      short loc_18005118D
0x18005117a  mov     eax, [rsp+580h+var_548]
0x18005117e  neg     eax
0x180051180  sbb     r15d, r15d
0x180051183  not     r15d
0x180051186  and     r15d, 80070005h
0x18005118d  shr     r15d, 1Fh
0x180051191  xor     r15b, 1
0x180051195  jmp     short loc_18005119A
0x180051197  mov     r15b, 1
0x18005119a  mov     [rsp+580h+var_54F], r13b
0x18005119f  xor     r14d, r14d
0x1800511a2  mov     [rsp+580h+var_510], r14
0x1800511a7  mov     rdi, qword ptr [rsp+580h+var_538]
0x1800511ac  test    bl, bl
0x1800511ae  jz      short loc_1800511E6
0x1800511b0  call    ?TryGetWindowIdOfCallerViaCoreWindow@CBrokeredLauncher@@CAKXZ; CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow(void)
0x1800511b5  test    eax, eax
0x1800511b7  jnz     short loc_1800511E6
0x1800511b9  mov     qword ptr [rsp+580h+var_548], rdi
0x1800511be  lea     rdx, [rsp+580h+var_548]
0x1800511c3  lea     rcx, [rbp+480h+var_2F0]
0x1800511ca  call    ??$LaunchAttemptedFromModernAppOnNonUIThread@PEBG@LaunchUri@LauncherDesktopProvider@@QEAAX$$QEAPEBG@Z; LauncherDesktopProvider::LaunchUri::LaunchAttemptedFromModernAppOnNonUIThread<ushort const *>(ushort const * &&)
0x1800511cf  lea     r8, [rsp+580h+var_510]; HWND *
0x1800511d4  lea     rdx, [rsp+580h+var_54F]; bool *
0x1800511d9  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x1800511dc  call    ?ValidateOrGetQuirkEnabledCallerWindow@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEA_NPEAPEAUHWND__@@@Z; CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(Windows::System::ILauncherStatics *,bool *,HWND__ * *)
0x1800511e1  mov     r13b, [rsp+580h+var_54F]
0x1800511e6  mov     r8d, 1000h
0x1800511ec  mov     rdx, rsi
0x1800511ef  lea     rcx, [rbp+480h+Process]
0x1800511f3  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x1800511f8  nop
0x1800511f9  mov     rbx, [rsp+580h+var_540]
0x1800511fe  mov     [rbp+480h+var_4E8], rbx
0x180051202  mov     [rsp+580h+var_540], r14
0x180051207  mov     [rbp+480h+var_4E0], rdi
0x18005120b  mov     qword ptr [rsp+580h+var_538], r14
0x180051210  mov     r14, [rsp+580h+var_530]
0x180051215  mov     [rsp+580h+var_530], 0
0x18005121e  mov     qword ptr [rsp+580h+var_548], r14
0x180051223  mov     rdx, [rsp+580h+var_508]
0x180051228  mov     cl, [rsp+580h+var_550]
0x18005122c  call    ??$GetOwnerWindowFromLauncherOptionsIfNeeded@UILauncherOptions@System@Windows@@@CBrokeredLauncher@@CAPEAUHWND__@@_NPEAUILauncherOptions@System@Windows@@@Z; CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(bool,Windows::System::ILauncherOptions *)
0x180051231  mov     [rbp+480h+var_4C8], rax
0x180051235  mov     [rbp+480h+var_4C0], 7
0x18005123c  xorps   xmm0, xmm0
0x18005123f  movdqu  [rbp+480h+var_4B8], xmm0
0x180051244  mov     rcx, [rbp+480h+Process]; Process
0x180051248  call    cs:__imp_GetProcessId
0x18005124e  mov     esi, eax
0x180051250  lea     rdx, [rbp+480h+var_1A0]
0x180051257  lea     rcx, [rbp+480h+var_2F0]
0x18005125e  call    ?Split@LaunchUri@LauncherDesktopProvider@@QEAA?AV12@XZ; LauncherDesktopProvider::LaunchUri::Split(void)
0x180051263  nop
0x180051264  mov     qword ptr [r12], 0
0x18005126c  mov     [rsp+580h+var_518], 1
0x180051274  mov     [rbp+480h+var_4A0], esi
0x180051277  mov     [rbp+480h+var_498], rbx
0x18005127b  xor     esi, esi
0x18005127d  mov     [rbp+480h+var_4E8], rsi
0x180051281  mov     [rbp+480h+var_490], rdi
0x180051285  mov     [rbp+480h+var_4E0], rsi
0x180051289  mov     qword ptr [rsp+580h+var_548], rsi
0x18005128e  mov     [rbp+480h+var_488], r14
0x180051292  mov     eax, dword ptr [rsp+580h+var_520]
0x180051296  mov     [rbp+480h+var_480], eax
0x180051299  mov     [rbp+480h+var_47C], r15b
0x18005129d  lea     rdx, [rbp+480h+var_4C8]; struct Windows::Internal::AsyncWindowOperation *
0x1800512a1  lea     rcx, [rbp+480h+var_478]; this
0x1800512a5  call    ??0AsyncWindowOperation@Internal@Windows@@QEAA@AEBV012@@Z; Windows::Internal::AsyncWindowOperation::AsyncWindowOperation(Windows::Internal::AsyncWindowOperation const &)
0x1800512aa  mov     al, [rsp+580h+var_550]
0x1800512ae  mov     [rbp+480h+var_458], al
0x1800512b1  mov     al, [rsp+580h+var_54E]
0x1800512b5  mov     [rbp+480h+var_457], al
0x1800512b8  mov     [rbp+480h+var_456], r13b
0x1800512bc  mov     rax, [rsp+580h+var_510]
0x1800512c1  mov     [rbp+480h+var_450], rax
0x1800512c5  lea     rdx, [rbp+480h+var_1A0]
0x1800512cc  lea     rcx, [rbp+480h+var_448]
0x1800512d0  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800512d5  lea     rax, ??_7LaunchUri@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::LaunchUri::`vftable'
0x1800512dc  mov     [rbp+480h+var_448], rax
0x1800512e0  mov     [rbp+480h+var_4F8], 1
0x1800512e7  mov     [rbp+480h+var_4F4], 80h
0x1800512ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800512f6  mov     ecx, 1D8h; unsigned __int64
0x1800512fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051300  mov     [rsp+580h+var_520], rax
0x180051305  test    rax, rax
0x180051308  jz      short loc_18005132A
0x18005130a  mov     rcx, [rbp+480h+var_4D8]
0x18005130e  mov     qword ptr [rsp+580h+Buffer], rcx
0x180051313  mov     r9, [rsp+580h+var_508]
0x180051318  mov     r8, [rbp+480h+var_4D0]
0x18005131c  lea     rdx, [rbp+480h+var_4A0]
0x180051320  mov     rcx, rax
0x180051323  call    ??$?0V_lambda_34074e6b262c35511414209380769e3f_@@@?$COperationLambdaVar@$00V_lambda_34074e6b262c35511414209380769e3f_@@V?$CBasicResult@W4LaunchUriStatus@System@Windows@@$02@Internal@Windows@@UIUriRuntimeClass@Foundation@4@UILauncherOptions@System@4@UITelemetryCorrelationVector@@@Internal@Windows@@QEAA@$$QEAV_lambda_34074e6b262c35511414209380769e3f_@@PEAUIUriRuntimeClass@Foundation@2@PEAUILauncherOptions@System@2@PEAUITelemetryCorrelationVector@@@Z; Windows::Internal::COperationLambdaVar<1,_lambda_34074e6b262c35511414209380769e3f_,Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3>,Windows::Foundation::IUriRuntimeClass,Windows::System::ILauncherOptions,ITelemetryCorrelationVector>::COperationLambdaVar<1,_lambda_34074e6b262c35511414209380769e3f_,Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3>,Windows::Foundation::IUriRuntimeClass,Windows::System::ILauncherOptions,ITelemetryCorrelationVector>(_lambda_34074e6b262c35511414209380769e3f_ &&,Windows::Foundation::IUriRuntimeClass *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *)
0x180051328  jmp     short loc_18005132D
0x18005132a  mov     rax, rsi
0x18005132d  mov     r9, rax
0x180051330  mov     r8d, 1
0x180051336  mov     rdx, r12
0x180051339  lea     rcx, [rbp+480h+var_4F8]
0x18005133d  call    ??$MakeAsyncOperationHelper@V?$CBasicResult@W4LaunchUriStatus@System@Windows@@$02@Internal@Windows@@W4LaunchUriStatus@System@3@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@W4LaunchUriStatus@System@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4LaunchUriStatus@System@Windows@@$02@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3>,Windows::System::LaunchUriStatus,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriStatus> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3>> *)
0x180051342  mov     ebx, eax
0x180051344  lea     rcx, [rbp+480h+var_4A0]; this
0x180051348  call    ??1_lambda_12a93b8d7660d2cdca714be35ee02a8e_@@QEAA@XZ; _lambda_12a93b8d7660d2cdca714be35ee02a8e_::~_lambda_12a93b8d7660d2cdca714be35ee02a8e_(void)
0x18005134d  mov     edx, ebx
0x18005134f  lea     rcx, [rbp+480h+var_2F0]
0x180051356  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005135b  mov     rcx, [rbp+488h]; this
0x180051362  test    ebx, ebx
0x180051364  jns     short loc_18005137B
0x180051366  mov     r9d, ebx; char *
0x180051369  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180051370  mov     edx, 59Fh; void *
0x180051375  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005137b  lea     rcx, [rbp+480h+var_1A0]; this
0x180051382  call    ??1LaunchUri@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchUri::~LaunchUri(void)
0x180051387  nop
0x180051388  lea     rcx, [rbp+480h+var_4C8]; this
0x18005138c  call    ??1AsyncWindowOperation@Internal@Windows@@QEAA@XZ; Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation(void)
0x180051391  nop
0x180051392  lea     rcx, [rsp+580h+var_548]
0x180051397  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18005139c  nop
0x18005139d  xor     ecx, ecx; pv
0x18005139f  call    cs:__imp_CoTaskMemFree
0x1800513a5  nop
0x1800513a6  xor     ecx, ecx; pv
0x1800513a8  call    cs:__imp_CoTaskMemFree
0x1800513ae  nop
0x1800513af  lea     rcx, [rbp+480h+Process]
0x1800513b3  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800513b8  nop
0x1800513b9  xor     ecx, ecx; pv
0x1800513bb  call    cs:__imp_CoTaskMemFree
0x1800513c1  nop
0x1800513c2  lea     rcx, [rsp+580h+var_530]
0x1800513c7  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800513cc  nop
0x1800513cd  xor     ecx, ecx; pv
0x1800513cf  call    cs:__imp_CoTaskMemFree
0x1800513d5  nop
0x1800513d6  lea     rcx, [rbp+480h+var_2F0]; this
0x1800513dd  call    ??1LaunchUri@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchUri::~LaunchUri(void)
0x1800513e2  nop
0x1800513e3  mov     rcx, [rsp+580h+string]; string
0x1800513e8  call    cs:__imp_WindowsDeleteString
0x1800513ee  mov     rax, r12
0x1800513f1  mov     rcx, [rbp+480h+var_50]
0x1800513f8  xor     rcx, rsp; StackCookie
0x1800513fb  call    __security_check_cookie
0x180051400  add     rsp, 548h
0x180051407  pop     r15
0x180051409  pop     r14
0x18005140b  pop     r13
0x18005140d  pop     r12
0x18005140f  pop     rdi
0x180051410  pop     rsi
0x180051411  pop     rbx
0x180051412  pop     rbp
0x180051413  retn
```
