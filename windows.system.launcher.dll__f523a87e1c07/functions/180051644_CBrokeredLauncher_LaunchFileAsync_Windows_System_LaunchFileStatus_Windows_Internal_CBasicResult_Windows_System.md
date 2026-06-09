# CBrokeredLauncher::_LaunchFileAsync<Windows::System::LaunchFileStatus,Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4>>(Windows::System::ILauncherStatics *,Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *)

- ea: `0x180051644`
- end: `0x1800519c7`
- name: `??$_LaunchFileAsync@W4LaunchFileStatus@System@Windows@@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@3@@CBrokeredLauncher@@CA?AV?$ComPtr@U?$IAsyncOperation@W4LaunchFileStatus@System@Windows@@@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherStatics@System@Windows@@PEAUIStorageFile@Storage@6@PEAUILauncherOptions@56@PEAUITelemetryCorrelationVector@@@Z`
- size: `899`
- prototype: `_QWORD *__fastcall(_QWORD *, struct Windows::System::ILauncherStatics *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051420`
- `0x180051530`

## callees

- `0x18000f194`
- `0x180040918`
- `0x180042254`
- `0x18005042c`
- `0x180050784`
- `0x180050850`
- `0x180050e94`
- `0x180051644`
- `0x180051ae4`
- `0x180051b58`
- `0x180051bc8`
- `0x180053018`
- `0x1800530e4`
- `0x1800533e4`
- `0x18005363c`
- `0x180053844`
- `0x1800550d8`
- `0x18005591c`
- `0x18005a524`
- `0x1800726f8`
- `0x18008a030`
- `0x1800e1520`
- `0x1800e1f70`
- `0x1800e602c`
- `0x180105bec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800516c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800516ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005172d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005196d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005197f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800516c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800516ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005172d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005196d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005197f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051992`

## string_xrefs

- `0x18005174e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005191f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
_QWORD *__fastcall CBrokeredLauncher::_LaunchFileAsync<enum Windows::System::LaunchFileStatus,Windows::Internal::CBasicResult<enum Windows::System::LaunchFileStatus,4>>(
        _QWORD *a1,
        struct Windows::System::ILauncherStatics *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char **v8; // rax
  struct IUnknown *v9; // rdx
  __int64 v10; // r8
  bool *v11; // r9
  void *v12; // rbx
  unsigned __int16 *v13; // rdi
  unsigned __int16 **v14; // r8
  int PsmKeyFromProcessHandle; // eax
  void *v16; // rdx
  __int64 v17; // rcx
  void **v18; // r9
  signed int v19; // eax
  bool v20; // al
  void *v21; // rax
  __int64 v22; // rax
  int v23; // r8d
  int v24; // ebx
  int Buffer; // [rsp+20h] [rbp-E0h]
  int Buffera; // [rsp+20h] [rbp-E0h]
  bool v28[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[12]; // [rsp+90h] [rbp-70h] BYREF
  void *v33; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v35; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v36[4]; // [rsp+B8h] [rbp-48h] BYREF
  void *v37; // [rsp+C0h] [rbp-40h] BYREF
  HWND v38; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v40; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h] BYREF
  int v43; // [rsp+F0h] [rbp-10h]
  __int128 v44; // [rsp+F8h] [rbp-8h]
  _QWORD *v45; // [rsp+108h] [rbp+8h]
  _BYTE v46[336]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v47[42]; // [rsp+260h] [rbp+160h] BYREF
  int v48[108]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v41 = a3;
  v45 = a1;
  v34 = 0;
  v8 = (char **)TelemetryCorrelationVectorServiceProvider::Increment(&v29, a5);
  LauncherDesktopProvider::LaunchFiles::StartWithCorrelationVector<>((LauncherDesktopProvider::LaunchFiles *)v46, *v8);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
  LODWORD(v31) = 0;
  v35 = 0;
  v33 = 0;
  v28[0] = 0;
  *(_QWORD *)v36 = 0;
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(
    a2,
    (enum PROCESS_UICONTEXT *)&v31,
    &v35,
    &v33,
    v36,
    v28);
  v12 = 0;
  v37 = 0;
  v28[1] = 0;
  v38 = 0;
  v13 = *(unsigned __int16 **)v36;
  if ( v28[0] )
  {
    wil::GetProcessHandleForClientOfObject(v32, a2, 4096);
    CoTaskMemFree(0);
    PsmKeyFromProcessHandle = CallerIdentity::GetPsmKeyFromProcessHandle(*(CallerIdentity **)v32, &v37, v14);
    if ( PsmKeyFromProcessHandle < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A5,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)PsmKeyFromProcessHandle,
        Buffer);
    if ( !CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow() )
    {
      v29 = v13;
      LauncherDesktopProvider::LaunchFiles::LaunchAttemptedFromModernAppOnNonUIThread<unsigned short const *>(v46, &v29);
      CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(a2, &v28[1], &v38);
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v32);
    v12 = v37;
  }
  *(_DWORD *)v32 = 4 * CBrokeredLauncher::CallingProcessHasUserChoiceCapability(a2, v9, v10, v11);
  v28[2] = CBrokeredLauncher::IsCallingProcessLowIL(a2);
  if ( v28[0] )
  {
    LODWORD(v30) = 0;
    v19 = CheckAndGetCapability((enum WELL_KNOWN_SID_TYPE)v17, v16, (int *)&v30, v18);
    if ( v19 >= 0 )
      v19 = (_DWORD)v30 == 0 ? 0x80070005 : 0;
    v20 = v19 >= 0;
  }
  else
  {
    v20 = 1;
  }
  v28[3] = v20;
  v29 = v35;
  v35 = 0;
  v40 = v13;
  *(_QWORD *)v36 = 0;
  pv = v12;
  v37 = 0;
  v21 = v33;
  v33 = 0;
  v30 = (__int64)v21;
  LOBYTE(v17) = v28[0];
  v42 = CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(v17, a4);
  v43 = 7;
  v44 = 0;
  LauncherDesktopProvider::LaunchFiles::Split(v46, v47);
  *a1 = 0;
  v34 = 1;
  v22 = _lambda_1c837b4cf627ae89728bf991f02ea9b3_::_lambda_1c837b4cf627ae89728bf991f02ea9b3_(
          (int)v48,
          (int)&v29,
          (int)&v40,
          (int)&pv,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v28[3],
          (__int64)v28,
          (__int64)&v28[2],
          (__int64)&v28[1],
          (__int64)&v38,
          (__int64)v32,
          (struct Windows::Internal::AsyncWindowOperation *)&v42,
          (__int64)v47);
  *(_DWORD *)v32 = 1;
  *(_QWORD *)&v32[4] = 4;
  v24 = Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<enum Windows::System::LaunchFileStatus,4>,enum Windows::System::LaunchFileStatus,Windows::Internal::ComTaskPoolHandler,Windows::Storage::IStorageFile,Windows::System::ILauncherOptions,ITelemetryCorrelationVector,_lambda_4d7444325909abacca5c87fae169e0b5_>(
          (unsigned int)v32,
          (_DWORD)a1,
          v23,
          v41,
          a4,
          a5,
          v22);
  _lambda_1c837b4cf627ae89728bf991f02ea9b3_::~_lambda_1c837b4cf627ae89728bf991f02ea9b3_((_lambda_1c837b4cf627ae89728bf991f02ea9b3_ *)v48);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v46,
    (unsigned int)v24);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x505,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v24,
      Buffera);
  LauncherDesktopProvider::LaunchFiles::~LaunchFiles((LauncherDesktopProvider::LaunchFiles *)v47);
  Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation((Windows::Internal::AsyncWindowOperation *)&v42);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v30);
  CoTaskMemFree(pv);
  CoTaskMemFree(v40);
  CoTaskMemFree(v29);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v33);
  CoTaskMemFree(0);
  LauncherDesktopProvider::LaunchFiles::~LaunchFiles((LauncherDesktopProvider::LaunchFiles *)v46);
  return a1;
}

```

## disassembly

```asm
0x180051644  push    rbp
0x180051646  push    rbx
0x180051647  push    rsi
0x180051648  push    rdi
0x180051649  push    r12
0x18005164b  push    r13
0x18005164d  push    r14
0x18005164f  lea     rbp, [rsp-470h]
0x180051657  sub     rsp, 570h
0x18005165e  mov     rax, cs:__security_cookie
0x180051665  xor     rax, rsp
0x180051668  mov     [rbp+4A0h+var_40], rax
0x18005166f  mov     r13, r9
0x180051672  mov     [rbp+4A0h+var_4C0], r8
0x180051676  mov     rsi, rdx
0x180051679  mov     r14, rcx
0x18005167c  mov     [rbp+4A0h+var_498], rcx
0x180051680  mov     r12, [rbp+4A0h+arg_20]
0x180051687  xor     edi, edi
0x180051689  mov     [rbp+4A0h+var_4F8], edi
0x18005168c  mov     rdx, r12
0x18005168f  lea     rcx, [rsp+5A0h+var_528]
0x180051694  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180051699  mov     rdx, [rax]; char *
0x18005169c  lea     rcx, [rbp+4A0h+var_490]; this
0x1800516a0  call    ??$StartWithCorrelationVector@$$V@LaunchFiles@LauncherDesktopProvider@@SA?AV01@PEBD@Z; LauncherDesktopProvider::LaunchFiles::StartWithCorrelationVector<>(char const *)
0x1800516a5  nop
0x1800516a6  lea     rcx, [rsp+5A0h+var_528]
0x1800516ab  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800516b0  mov     dword ptr [rbp+4A0h+var_518], edi
0x1800516b3  mov     [rbp+4A0h+var_4F0], rdi
0x1800516b7  mov     [rbp+4A0h+var_500], rdi
0x1800516bb  mov     [rsp+5A0h+var_530], dil
0x1800516c0  mov     qword ptr [rbp+4A0h+var_4E8], rdi
0x1800516c4  xor     ecx, ecx; pv
0x1800516c6  call    cs:__imp_CoTaskMemFree
0x1800516cc  xor     ecx, ecx; pv
0x1800516ce  call    cs:__imp_CoTaskMemFree
0x1800516d4  lea     rax, [rsp+5A0h+var_530]
0x1800516d9  mov     [rsp+5A0h+var_578], rax; bool *
0x1800516de  lea     rax, [rbp+4A0h+var_4E8]
0x1800516e2  mov     qword ptr [rsp+5A0h+Buffer], rax; int
0x1800516e7  lea     r9, [rbp+4A0h+var_500]; void **
0x1800516eb  lea     r8, [rbp+4A0h+var_4F0]; unsigned __int16 **
0x1800516ef  lea     rdx, [rbp+4A0h+var_518]; enum PROCESS_UICONTEXT *
0x1800516f3  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x1800516f6  call    ?RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAW4PROCESS_UICONTEXT@@PEAPEAGPEAPEAX2PEA_N@Z; CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(Windows::System::ILauncherStatics *,PROCESS_UICONTEXT *,ushort * *,void * *,ushort * *,bool *)
0x1800516fb  mov     ebx, edi
0x1800516fd  mov     [rbp+4A0h+var_4E0], rbx
0x180051701  mov     [rsp+5A0h+var_530+1], dil
0x180051706  mov     [rbp+4A0h+var_4D8], rdi
0x18005170a  mov     rdi, qword ptr [rbp+4A0h+var_4E8]
0x18005170e  cmp     [rsp+5A0h+var_530], bl
0x180051712  jz      loc_18005179B
0x180051718  mov     r8d, 1000h
0x18005171e  mov     rdx, rsi
0x180051721  lea     rcx, [rbp+4A0h+var_510]
0x180051725  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x18005172a  nop
0x18005172b  xor     ecx, ecx; pv
0x18005172d  call    cs:__imp_CoTaskMemFree
0x180051733  lea     rdx, [rbp+4A0h+var_4E0]; void *
0x180051737  mov     rcx, [rbp+4A0h+var_510]; this
0x18005173b  call    ?GetPsmKeyFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPsmKeyFromProcessHandle(void *,ushort * *)
0x180051740  mov     rcx, [rbp+4A8h]; this
0x180051747  test    eax, eax
0x180051749  jns     short loc_180051760
0x18005174b  mov     r9d, eax; char *
0x18005174e  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180051755  mov     edx, 4A5h; void *
0x18005175a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051760  call    ?TryGetWindowIdOfCallerViaCoreWindow@CBrokeredLauncher@@CAKXZ; CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow(void)
0x180051765  test    eax, eax
0x180051767  jnz     short loc_18005178E
0x180051769  mov     [rsp+5A0h+var_528], rdi
0x18005176e  lea     rdx, [rsp+5A0h+var_528]
0x180051773  lea     rcx, [rbp+4A0h+var_490]
0x180051777  call    ??$LaunchAttemptedFromModernAppOnNonUIThread@PEBG@LaunchFiles@LauncherDesktopProvider@@QEAAX$$QEAPEBG@Z; LauncherDesktopProvider::LaunchFiles::LaunchAttemptedFromModernAppOnNonUIThread<ushort const *>(ushort const * &&)
0x18005177c  lea     r8, [rbp+4A0h+var_4D8]; HWND *
0x180051780  lea     rdx, [rsp+5A0h+var_530+1]; bool *
0x180051785  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180051788  call    ?ValidateOrGetQuirkEnabledCallerWindow@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEA_NPEAPEAUHWND__@@@Z; CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(Windows::System::ILauncherStatics *,bool *,HWND__ * *)
0x18005178d  nop
0x18005178e  lea     rcx, [rbp+4A0h+var_510]
0x180051792  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180051797  mov     rbx, [rbp+4A0h+var_4E0]
0x18005179b  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x18005179e  call    ?CallingProcessHasUserChoiceCapability@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::CallingProcessHasUserChoiceCapability(Windows::System::ILauncherStatics *)
0x1800517a3  movzx   eax, al
0x1800517a6  shl     eax, 2
0x1800517a9  mov     dword ptr [rbp+4A0h+var_510], eax
0x1800517ac  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x1800517af  call    ?IsCallingProcessLowIL@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::IsCallingProcessLowIL(Windows::System::ILauncherStatics *)
0x1800517b4  mov     [rsp+5A0h+var_530+2], al
0x1800517b8  xor     esi, esi
0x1800517ba  cmp     [rsp+5A0h+var_530], sil
0x1800517bf  jz      short loc_1800517E6
0x1800517c1  mov     dword ptr [rbp+4A0h+var_520], esi
0x1800517c4  lea     r8, [rbp+4A0h+var_520]; int *
0x1800517c8  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x1800517cd  test    eax, eax
0x1800517cf  js      short loc_1800517DF
0x1800517d1  mov     eax, dword ptr [rbp+4A0h+var_520]
0x1800517d4  neg     eax
0x1800517d6  sbb     eax, eax
0x1800517d8  not     eax
0x1800517da  and     eax, 80070005h
0x1800517df  shr     eax, 1Fh
0x1800517e2  xor     al, 1
0x1800517e4  jmp     short loc_1800517E8
0x1800517e6  mov     al, 1
0x1800517e8  mov     [rsp+5A0h+var_530+3], al
0x1800517ec  mov     rax, [rbp+4A0h+var_4F0]
0x1800517f0  mov     [rsp+5A0h+var_528], rax
0x1800517f5  mov     [rbp+4A0h+var_4F0], rsi
0x1800517f9  mov     [rbp+4A0h+var_4C8], rdi
0x1800517fd  mov     qword ptr [rbp+4A0h+var_4E8], rsi
0x180051801  mov     [rbp+4A0h+pv], rbx
0x180051805  mov     [rbp+4A0h+var_4E0], rsi
0x180051809  mov     rax, [rbp+4A0h+var_500]
0x18005180d  mov     [rbp+4A0h+var_500], rsi
0x180051811  mov     [rbp+4A0h+var_520], rax
0x180051815  mov     rdx, r13
0x180051818  mov     cl, [rsp+5A0h+var_530]
0x18005181c  call    ??$GetOwnerWindowFromLauncherOptionsIfNeeded@UILauncherOptions@System@Windows@@@CBrokeredLauncher@@CAPEAUHWND__@@_NPEAUILauncherOptions@System@Windows@@@Z; CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(bool,Windows::System::ILauncherOptions *)
0x180051821  mov     [rbp+4A0h+var_4B8], rax
0x180051825  mov     [rbp+4A0h+var_4B0], 7
0x18005182c  xorps   xmm0, xmm0
0x18005182f  movdqu  [rbp+4A0h+var_4A8], xmm0
0x180051834  lea     rdx, [rbp+4A0h+var_340]
0x18005183b  lea     rcx, [rbp+4A0h+var_490]
0x18005183f  call    ?Split@LaunchFiles@LauncherDesktopProvider@@QEAA?AV12@XZ; LauncherDesktopProvider::LaunchFiles::Split(void)
0x180051844  nop
0x180051845  mov     [r14], rsi
0x180051848  mov     [rbp+4A0h+var_4F8], 1
0x18005184f  lea     rax, [rbp+4A0h+var_340]
0x180051856  mov     [rsp+5A0h+var_538], rax; __int64
0x18005185b  lea     rax, [rbp+4A0h+var_4B8]
0x18005185f  mov     [rsp+5A0h+var_540], rax; struct Windows::Internal::AsyncWindowOperation *
0x180051864  lea     rax, [rbp+4A0h+var_510]
0x180051868  mov     [rsp+5A0h+var_548], rax; __int64
0x18005186d  lea     rax, [rbp+4A0h+var_4D8]
0x180051871  mov     [rsp+5A0h+var_550], rax; __int64
0x180051876  lea     rax, [rsp+5A0h+var_530+1]
0x18005187b  mov     [rsp+5A0h+var_558], rax; __int64
0x180051880  lea     rax, [rsp+5A0h+var_530+2]
0x180051885  mov     [rsp+5A0h+var_560], rax; __int64
0x18005188a  lea     rax, [rsp+5A0h+var_530]
0x18005188f  mov     [rsp+5A0h+var_568], rax; __int64
0x180051894  lea     rax, [rsp+5A0h+var_530+3]
0x180051899  mov     [rsp+5A0h+var_570], rax; __int64
0x18005189e  lea     rax, [rbp+4A0h+var_518]
0x1800518a2  mov     [rsp+5A0h+var_578], rax; __int64
0x1800518a7  lea     rax, [rbp+4A0h+var_520]
0x1800518ab  mov     qword ptr [rsp+5A0h+Buffer], rax; __int64
0x1800518b0  lea     r9, [rbp+4A0h+pv]; int
0x1800518b4  lea     r8, [rbp+4A0h+var_4C8]; int
0x1800518b8  lea     rdx, [rsp+5A0h+var_528]; int
0x1800518bd  lea     rcx, [rbp+4A0h+var_1F0]; int
0x1800518c4  call    ??0_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@QEAA@AEBV?$CCaptureByMoving@V?$CMemString@UCMemString_PolicyCoTaskMem@@@@@@00AEBV?$CCaptureByMoving@V?$CAutoHandle@PEAX@@@@AEBW4PROCESS_UICONTEXT@@AEB_N333AEBQEAUHWND__@@AEBW4LaunchHelperOptions@@AEBVAsyncWindowOperation@Internal@Windows@@AEBVLaunchFiles@LauncherDesktopProvider@@@Z; _lambda_1c837b4cf627ae89728bf991f02ea9b3_::_lambda_1c837b4cf627ae89728bf991f02ea9b3_(CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CAutoHandle<void *>> const &,PROCESS_UICONTEXT const &,bool const &,bool const &,bool const &,bool const &,HWND__ * const &,LaunchHelperOptions const &,Windows::Internal::AsyncWindowOperation const &,LauncherDesktopProvider::LaunchFiles const &)
0x1800518c9  nop
0x1800518ca  mov     dword ptr [rbp+4A0h+var_510], 1
0x1800518d1  mov     [rbp+4A0h+var_510+4], 4
0x1800518d9  mov     [rsp+5A0h+var_570], rax
0x1800518de  mov     [rsp+5A0h+var_578], r12
0x1800518e3  mov     qword ptr [rsp+5A0h+Buffer], r13; int
0x1800518e8  mov     r9, [rbp+4A0h+var_4C0]
0x1800518ec  mov     rdx, r14
0x1800518ef  lea     rcx, [rbp+4A0h+var_510]
0x1800518f3  call    ??$MakeStagedAsyncOperation@V?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@Windows@@W4LaunchFileStatus@System@3@VComTaskPoolHandler@23@UIStorageFile@Storage@3@UILauncherOptions@53@UITelemetryCorrelationVector@@V_lambda_4d7444325909abacca5c87fae169e0b5_@@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@W4LaunchFileStatus@System@Windows@@@Foundation@1@W4TrustLevel@@PEAUIStorageFile@Storage@1@PEAUILauncherOptions@System@1@PEAUITelemetryCorrelationVector@@$$QEAV_lambda_4d7444325909abacca5c87fae169e0b5_@@@Z; Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4>,Windows::System::LaunchFileStatus,Windows::Internal::ComTaskPoolHandler,Windows::Storage::IStorageFile,Windows::System::ILauncherOptions,ITelemetryCorrelationVector,_lambda_4d7444325909abacca5c87fae169e0b5_>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::System::LaunchFileStatus> * *,TrustLevel,Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,_lambda_4d7444325909abacca5c87fae169e0b5_ &&)
0x1800518f8  mov     ebx, eax
0x1800518fa  lea     rcx, [rbp+4A0h+var_1F0]; this
0x180051901  call    ??1_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@QEAA@XZ; _lambda_1c837b4cf627ae89728bf991f02ea9b3_::~_lambda_1c837b4cf627ae89728bf991f02ea9b3_(void)
0x180051906  mov     edx, ebx
0x180051908  lea     rcx, [rbp+4A0h+var_490]
0x18005190c  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180051911  mov     rcx, [rbp+4A8h]; this
0x180051918  test    ebx, ebx
0x18005191a  jns     short loc_180051931
0x18005191c  mov     r9d, ebx; char *
0x18005191f  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180051926  mov     edx, 505h; void *
0x18005192b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051931  lea     rcx, [rbp+4A0h+var_340]; this
0x180051938  call    ??1LaunchFiles@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchFiles::~LaunchFiles(void)
0x18005193d  nop
0x18005193e  lea     rcx, [rbp+4A0h+var_4B8]; this
0x180051942  call    ??1AsyncWindowOperation@Internal@Windows@@QEAA@XZ; Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation(void)
0x180051947  nop
0x180051948  lea     rcx, [rbp+4A0h+var_520]
0x18005194c  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180051951  nop
0x180051952  mov     rcx, [rbp+4A0h+pv]; pv
0x180051956  call    cs:__imp_CoTaskMemFree
0x18005195c  nop
0x18005195d  mov     rcx, [rbp+4A0h+var_4C8]; pv
0x180051961  call    cs:__imp_CoTaskMemFree
0x180051967  nop
0x180051968  mov     rcx, [rsp+5A0h+var_528]; pv
0x18005196d  call    cs:__imp_CoTaskMemFree
0x180051973  nop
0x180051974  xor     ecx, ecx; pv
0x180051976  call    cs:__imp_CoTaskMemFree
0x18005197c  nop
0x18005197d  xor     ecx, ecx; pv
0x18005197f  call    cs:__imp_CoTaskMemFree
0x180051985  nop
0x180051986  lea     rcx, [rbp+4A0h+var_500]
0x18005198a  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18005198f  nop
0x180051990  xor     ecx, ecx; pv
0x180051992  call    cs:__imp_CoTaskMemFree
0x180051998  nop
0x180051999  lea     rcx, [rbp+4A0h+var_490]; this
0x18005199d  call    ??1LaunchFiles@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchFiles::~LaunchFiles(void)
0x1800519a2  mov     rax, r14
0x1800519a5  mov     rcx, [rbp+4A0h+var_40]
0x1800519ac  xor     rcx, rsp; StackCookie
0x1800519af  call    __security_check_cookie
0x1800519b4  add     rsp, 570h
0x1800519bb  pop     r14
0x1800519bd  pop     r13
0x1800519bf  pop     r12
0x1800519c1  pop     rdi
0x1800519c2  pop     rsi
0x1800519c3  pop     rbx
0x1800519c4  pop     rbp
0x1800519c5  retn
```
