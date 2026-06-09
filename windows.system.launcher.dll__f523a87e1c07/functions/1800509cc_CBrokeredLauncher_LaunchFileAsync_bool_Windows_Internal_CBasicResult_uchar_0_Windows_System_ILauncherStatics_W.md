# CBrokeredLauncher::_LaunchFileAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::System::ILauncherStatics *,Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *)

- ea: `0x1800509cc`
- end: `0x180050d4f`
- name: `??$_LaunchFileAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@CBrokeredLauncher@@CA?AV?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherStatics@System@Windows@@PEAUIStorageFile@Storage@6@PEAUILauncherOptions@56@PEAUITelemetryCorrelationVector@@@Z`
- size: `899`
- prototype: `_QWORD *__fastcall(_QWORD *, struct Windows::System::ILauncherStatics *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180050610`
- `0x180050920`

## callees

- `0x18000f194`
- `0x180040918`
- `0x180042254`
- `0x18005042c`
- `0x180050784`
- `0x1800507d4`
- `0x180050850`
- `0x1800509cc`
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

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050d07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050d1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050d07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050d1a`

## string_xrefs

- `0x180050ad6`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180050ca7`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
_QWORD *__fastcall CBrokeredLauncher::_LaunchFileAsync<bool,Windows::Internal::CBasicResult<unsigned char,0>>(
        _QWORD *a1,
        struct Windows::System::ILauncherStatics *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char **v8; // rax
  void *v9; // rbx
  unsigned __int16 *v10; // rdi
  unsigned __int16 **v11; // r8
  int PsmKeyFromProcessHandle; // eax
  void *v13; // rdx
  __int64 v14; // rcx
  void **v15; // r9
  signed int v16; // eax
  bool v17; // al
  void *v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  int v21; // ebx
  int Buffer; // [rsp+20h] [rbp-E0h]
  int Buffera; // [rsp+20h] [rbp-E0h]
  bool v25[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v29[12]; // [rsp+90h] [rbp-70h] BYREF
  void *v30; // [rsp+A0h] [rbp-60h] BYREF
  int v31; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v32; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v33[4]; // [rsp+B8h] [rbp-48h] BYREF
  void *v34; // [rsp+C0h] [rbp-40h] BYREF
  HWND v35; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v37; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h] BYREF
  int v40; // [rsp+F0h] [rbp-10h]
  __int128 v41; // [rsp+F8h] [rbp-8h]
  _QWORD *v42; // [rsp+108h] [rbp+8h]
  _BYTE v43[336]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v44[42]; // [rsp+260h] [rbp+160h] BYREF
  int v45[108]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v38 = a3;
  v42 = a1;
  v31 = 0;
  v8 = (char **)TelemetryCorrelationVectorServiceProvider::Increment(&v26, a5);
  LauncherDesktopProvider::LaunchFiles::StartWithCorrelationVector<>((LauncherDesktopProvider::LaunchFiles *)v43, *v8);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v26);
  LODWORD(v28) = 0;
  v32 = 0;
  v30 = 0;
  v25[0] = 0;
  *(_QWORD *)v33 = 0;
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(
    a2,
    (enum PROCESS_UICONTEXT *)&v28,
    &v32,
    &v30,
    v33,
    v25);
  v9 = 0;
  v34 = 0;
  v25[1] = 0;
  v35 = 0;
  v10 = *(unsigned __int16 **)v33;
  if ( v25[0] )
  {
    wil::GetProcessHandleForClientOfObject(v29, a2, 4096);
    CoTaskMemFree(0);
    PsmKeyFromProcessHandle = CallerIdentity::GetPsmKeyFromProcessHandle(*(CallerIdentity **)v29, &v34, v11);
    if ( PsmKeyFromProcessHandle < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A5,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)PsmKeyFromProcessHandle,
        Buffer);
    if ( !CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow() )
    {
      v26 = v10;
      LauncherDesktopProvider::LaunchFiles::LaunchAttemptedFromModernAppOnNonUIThread<unsigned short const *>(v43, &v26);
      CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(a2, &v25[1], &v35);
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v29);
    v9 = v34;
  }
  *(_DWORD *)v29 = 4 * CBrokeredLauncher::CallingProcessHasUserChoiceCapability(a2);
  v25[2] = CBrokeredLauncher::IsCallingProcessLowIL(a2);
  if ( v25[0] )
  {
    LODWORD(v27) = 0;
    v16 = CheckAndGetCapability((enum WELL_KNOWN_SID_TYPE)v14, v13, (int *)&v27, v15);
    if ( v16 >= 0 )
      v16 = (_DWORD)v27 == 0 ? 0x80070005 : 0;
    v17 = v16 >= 0;
  }
  else
  {
    v17 = 1;
  }
  v25[3] = v17;
  v26 = v32;
  v32 = 0;
  v37 = v10;
  *(_QWORD *)v33 = 0;
  pv = v9;
  v34 = 0;
  v18 = v30;
  v30 = 0;
  v27 = (__int64)v18;
  LOBYTE(v14) = v25[0];
  v39 = CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(v14, a4);
  v40 = 7;
  v41 = 0;
  LauncherDesktopProvider::LaunchFiles::Split(v43, v44);
  *a1 = 0;
  v31 = 1;
  v19 = _lambda_1c837b4cf627ae89728bf991f02ea9b3_::_lambda_1c837b4cf627ae89728bf991f02ea9b3_(
          (int)v45,
          (int)&v26,
          (int)&v37,
          (int)&pv,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v25[3],
          (__int64)v25,
          (__int64)&v25[2],
          (__int64)&v25[1],
          (__int64)&v35,
          (__int64)v29,
          (struct Windows::Internal::AsyncWindowOperation *)&v39,
          (__int64)v44);
  *(_DWORD *)v29 = 1;
  *(_QWORD *)&v29[4] = 4;
  v21 = Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler,Windows::Storage::IStorageFile,Windows::System::ILauncherOptions,ITelemetryCorrelationVector,_lambda_1c837b4cf627ae89728bf991f02ea9b3_>(
          (unsigned int)v29,
          (_DWORD)a1,
          v20,
          v38,
          a4,
          a5,
          v19);
  _lambda_1c837b4cf627ae89728bf991f02ea9b3_::~_lambda_1c837b4cf627ae89728bf991f02ea9b3_((_lambda_1c837b4cf627ae89728bf991f02ea9b3_ *)v45);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v43,
    (unsigned int)v21);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x505,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v21,
      Buffera);
  LauncherDesktopProvider::LaunchFiles::~LaunchFiles((LauncherDesktopProvider::LaunchFiles *)v44);
  Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation((Windows::Internal::AsyncWindowOperation *)&v39);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v27);
  CoTaskMemFree(pv);
  CoTaskMemFree(v37);
  CoTaskMemFree(v26);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v30);
  CoTaskMemFree(0);
  LauncherDesktopProvider::LaunchFiles::~LaunchFiles((LauncherDesktopProvider::LaunchFiles *)v43);
  return a1;
}

```

## disassembly

```asm
0x1800509cc  push    rbp
0x1800509ce  push    rbx
0x1800509cf  push    rsi
0x1800509d0  push    rdi
0x1800509d1  push    r12
0x1800509d3  push    r13
0x1800509d5  push    r14
0x1800509d7  lea     rbp, [rsp-470h]
0x1800509df  sub     rsp, 570h
0x1800509e6  mov     rax, cs:__security_cookie
0x1800509ed  xor     rax, rsp
0x1800509f0  mov     [rbp+4A0h+var_40], rax
0x1800509f7  mov     r13, r9
0x1800509fa  mov     [rbp+4A0h+var_4C0], r8
0x1800509fe  mov     rsi, rdx
0x180050a01  mov     r14, rcx
0x180050a04  mov     [rbp+4A0h+var_498], rcx
0x180050a08  mov     r12, [rbp+4A0h+arg_20]
0x180050a0f  xor     edi, edi
0x180050a11  mov     [rbp+4A0h+var_4F8], edi
0x180050a14  mov     rdx, r12
0x180050a17  lea     rcx, [rsp+5A0h+var_528]
0x180050a1c  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180050a21  mov     rdx, [rax]; char *
0x180050a24  lea     rcx, [rbp+4A0h+var_490]; this
0x180050a28  call    ??$StartWithCorrelationVector@$$V@LaunchFiles@LauncherDesktopProvider@@SA?AV01@PEBD@Z; LauncherDesktopProvider::LaunchFiles::StartWithCorrelationVector<>(char const *)
0x180050a2d  nop
0x180050a2e  lea     rcx, [rsp+5A0h+var_528]
0x180050a33  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180050a38  mov     dword ptr [rbp+4A0h+var_518], edi
0x180050a3b  mov     [rbp+4A0h+var_4F0], rdi
0x180050a3f  mov     [rbp+4A0h+var_500], rdi
0x180050a43  mov     [rsp+5A0h+var_530], dil
0x180050a48  mov     qword ptr [rbp+4A0h+var_4E8], rdi
0x180050a4c  xor     ecx, ecx; pv
0x180050a4e  call    cs:__imp_CoTaskMemFree
0x180050a54  xor     ecx, ecx; pv
0x180050a56  call    cs:__imp_CoTaskMemFree
0x180050a5c  lea     rax, [rsp+5A0h+var_530]
0x180050a61  mov     [rsp+5A0h+var_578], rax; bool *
0x180050a66  lea     rax, [rbp+4A0h+var_4E8]
0x180050a6a  mov     qword ptr [rsp+5A0h+Buffer], rax; int
0x180050a6f  lea     r9, [rbp+4A0h+var_500]; void **
0x180050a73  lea     r8, [rbp+4A0h+var_4F0]; unsigned __int16 **
0x180050a77  lea     rdx, [rbp+4A0h+var_518]; enum PROCESS_UICONTEXT *
0x180050a7b  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180050a7e  call    ?RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAW4PROCESS_UICONTEXT@@PEAPEAGPEAPEAX2PEA_N@Z; CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(Windows::System::ILauncherStatics *,PROCESS_UICONTEXT *,ushort * *,void * *,ushort * *,bool *)
0x180050a83  mov     ebx, edi
0x180050a85  mov     [rbp+4A0h+var_4E0], rbx
0x180050a89  mov     [rsp+5A0h+var_530+1], dil
0x180050a8e  mov     [rbp+4A0h+var_4D8], rdi
0x180050a92  mov     rdi, qword ptr [rbp+4A0h+var_4E8]
0x180050a96  cmp     [rsp+5A0h+var_530], bl
0x180050a9a  jz      loc_180050B23
0x180050aa0  mov     r8d, 1000h
0x180050aa6  mov     rdx, rsi
0x180050aa9  lea     rcx, [rbp+4A0h+var_510]
0x180050aad  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x180050ab2  nop
0x180050ab3  xor     ecx, ecx; pv
0x180050ab5  call    cs:__imp_CoTaskMemFree
0x180050abb  lea     rdx, [rbp+4A0h+var_4E0]; void *
0x180050abf  mov     rcx, [rbp+4A0h+var_510]; this
0x180050ac3  call    ?GetPsmKeyFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPsmKeyFromProcessHandle(void *,ushort * *)
0x180050ac8  mov     rcx, [rbp+4A8h]; this
0x180050acf  test    eax, eax
0x180050ad1  jns     short loc_180050AE8
0x180050ad3  mov     r9d, eax; char *
0x180050ad6  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180050add  mov     edx, 4A5h; void *
0x180050ae2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050ae8  call    ?TryGetWindowIdOfCallerViaCoreWindow@CBrokeredLauncher@@CAKXZ; CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow(void)
0x180050aed  test    eax, eax
0x180050aef  jnz     short loc_180050B16
0x180050af1  mov     [rsp+5A0h+var_528], rdi
0x180050af6  lea     rdx, [rsp+5A0h+var_528]
0x180050afb  lea     rcx, [rbp+4A0h+var_490]
0x180050aff  call    ??$LaunchAttemptedFromModernAppOnNonUIThread@PEBG@LaunchFiles@LauncherDesktopProvider@@QEAAX$$QEAPEBG@Z; LauncherDesktopProvider::LaunchFiles::LaunchAttemptedFromModernAppOnNonUIThread<ushort const *>(ushort const * &&)
0x180050b04  lea     r8, [rbp+4A0h+var_4D8]; HWND *
0x180050b08  lea     rdx, [rsp+5A0h+var_530+1]; bool *
0x180050b0d  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180050b10  call    ?ValidateOrGetQuirkEnabledCallerWindow@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEA_NPEAPEAUHWND__@@@Z; CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(Windows::System::ILauncherStatics *,bool *,HWND__ * *)
0x180050b15  nop
0x180050b16  lea     rcx, [rbp+4A0h+var_510]
0x180050b1a  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050b1f  mov     rbx, [rbp+4A0h+var_4E0]
0x180050b23  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180050b26  call    ?CallingProcessHasUserChoiceCapability@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::CallingProcessHasUserChoiceCapability(Windows::System::ILauncherStatics *)
0x180050b2b  movzx   eax, al
0x180050b2e  shl     eax, 2
0x180050b31  mov     dword ptr [rbp+4A0h+var_510], eax
0x180050b34  mov     rcx, rsi; struct Windows::System::ILauncherStatics *
0x180050b37  call    ?IsCallingProcessLowIL@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::IsCallingProcessLowIL(Windows::System::ILauncherStatics *)
0x180050b3c  mov     [rsp+5A0h+var_530+2], al
0x180050b40  xor     esi, esi
0x180050b42  cmp     [rsp+5A0h+var_530], sil
0x180050b47  jz      short loc_180050B6E
0x180050b49  mov     dword ptr [rbp+4A0h+var_520], esi
0x180050b4c  lea     r8, [rbp+4A0h+var_520]; int *
0x180050b50  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x180050b55  test    eax, eax
0x180050b57  js      short loc_180050B67
0x180050b59  mov     eax, dword ptr [rbp+4A0h+var_520]
0x180050b5c  neg     eax
0x180050b5e  sbb     eax, eax
0x180050b60  not     eax
0x180050b62  and     eax, 80070005h
0x180050b67  shr     eax, 1Fh
0x180050b6a  xor     al, 1
0x180050b6c  jmp     short loc_180050B70
0x180050b6e  mov     al, 1
0x180050b70  mov     [rsp+5A0h+var_530+3], al
0x180050b74  mov     rax, [rbp+4A0h+var_4F0]
0x180050b78  mov     [rsp+5A0h+var_528], rax
0x180050b7d  mov     [rbp+4A0h+var_4F0], rsi
0x180050b81  mov     [rbp+4A0h+var_4C8], rdi
0x180050b85  mov     qword ptr [rbp+4A0h+var_4E8], rsi
0x180050b89  mov     [rbp+4A0h+pv], rbx
0x180050b8d  mov     [rbp+4A0h+var_4E0], rsi
0x180050b91  mov     rax, [rbp+4A0h+var_500]
0x180050b95  mov     [rbp+4A0h+var_500], rsi
0x180050b99  mov     [rbp+4A0h+var_520], rax
0x180050b9d  mov     rdx, r13
0x180050ba0  mov     cl, [rsp+5A0h+var_530]
0x180050ba4  call    ??$GetOwnerWindowFromLauncherOptionsIfNeeded@UILauncherOptions@System@Windows@@@CBrokeredLauncher@@CAPEAUHWND__@@_NPEAUILauncherOptions@System@Windows@@@Z; CBrokeredLauncher::GetOwnerWindowFromLauncherOptionsIfNeeded<Windows::System::ILauncherOptions>(bool,Windows::System::ILauncherOptions *)
0x180050ba9  mov     [rbp+4A0h+var_4B8], rax
0x180050bad  mov     [rbp+4A0h+var_4B0], 7
0x180050bb4  xorps   xmm0, xmm0
0x180050bb7  movdqu  [rbp+4A0h+var_4A8], xmm0
0x180050bbc  lea     rdx, [rbp+4A0h+var_340]
0x180050bc3  lea     rcx, [rbp+4A0h+var_490]
0x180050bc7  call    ?Split@LaunchFiles@LauncherDesktopProvider@@QEAA?AV12@XZ; LauncherDesktopProvider::LaunchFiles::Split(void)
0x180050bcc  nop
0x180050bcd  mov     [r14], rsi
0x180050bd0  mov     [rbp+4A0h+var_4F8], 1
0x180050bd7  lea     rax, [rbp+4A0h+var_340]
0x180050bde  mov     [rsp+5A0h+var_538], rax; __int64
0x180050be3  lea     rax, [rbp+4A0h+var_4B8]
0x180050be7  mov     [rsp+5A0h+var_540], rax; struct Windows::Internal::AsyncWindowOperation *
0x180050bec  lea     rax, [rbp+4A0h+var_510]
0x180050bf0  mov     [rsp+5A0h+var_548], rax; __int64
0x180050bf5  lea     rax, [rbp+4A0h+var_4D8]
0x180050bf9  mov     [rsp+5A0h+var_550], rax; __int64
0x180050bfe  lea     rax, [rsp+5A0h+var_530+1]
0x180050c03  mov     [rsp+5A0h+var_558], rax; __int64
0x180050c08  lea     rax, [rsp+5A0h+var_530+2]
0x180050c0d  mov     [rsp+5A0h+var_560], rax; __int64
0x180050c12  lea     rax, [rsp+5A0h+var_530]
0x180050c17  mov     [rsp+5A0h+var_568], rax; __int64
0x180050c1c  lea     rax, [rsp+5A0h+var_530+3]
0x180050c21  mov     [rsp+5A0h+var_570], rax; __int64
0x180050c26  lea     rax, [rbp+4A0h+var_518]
0x180050c2a  mov     [rsp+5A0h+var_578], rax; __int64
0x180050c2f  lea     rax, [rbp+4A0h+var_520]
0x180050c33  mov     qword ptr [rsp+5A0h+Buffer], rax; __int64
0x180050c38  lea     r9, [rbp+4A0h+pv]; int
0x180050c3c  lea     r8, [rbp+4A0h+var_4C8]; int
0x180050c40  lea     rdx, [rsp+5A0h+var_528]; int
0x180050c45  lea     rcx, [rbp+4A0h+var_1F0]; int
0x180050c4c  call    ??0_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@QEAA@AEBV?$CCaptureByMoving@V?$CMemString@UCMemString_PolicyCoTaskMem@@@@@@00AEBV?$CCaptureByMoving@V?$CAutoHandle@PEAX@@@@AEBW4PROCESS_UICONTEXT@@AEB_N333AEBQEAUHWND__@@AEBW4LaunchHelperOptions@@AEBVAsyncWindowOperation@Internal@Windows@@AEBVLaunchFiles@LauncherDesktopProvider@@@Z; _lambda_1c837b4cf627ae89728bf991f02ea9b3_::_lambda_1c837b4cf627ae89728bf991f02ea9b3_(CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CAutoHandle<void *>> const &,PROCESS_UICONTEXT const &,bool const &,bool const &,bool const &,bool const &,HWND__ * const &,LaunchHelperOptions const &,Windows::Internal::AsyncWindowOperation const &,LauncherDesktopProvider::LaunchFiles const &)
0x180050c51  nop
0x180050c52  mov     dword ptr [rbp+4A0h+var_510], 1
0x180050c59  mov     [rbp+4A0h+var_510+4], 4
0x180050c61  mov     [rsp+5A0h+var_570], rax
0x180050c66  mov     [rsp+5A0h+var_578], r12
0x180050c6b  mov     qword ptr [rsp+5A0h+Buffer], r13; int
0x180050c70  mov     r9, [rbp+4A0h+var_4C0]
0x180050c74  mov     rdx, r14
0x180050c77  lea     rcx, [rbp+4A0h+var_510]
0x180050c7b  call    ??$MakeStagedAsyncOperation@V?$CBasicResult@E$0A@@Internal@Windows@@_NVComTaskPoolHandler@23@UIStorageFile@Storage@3@UILauncherOptions@System@3@UITelemetryCorrelationVector@@V_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@_N@Foundation@1@W4TrustLevel@@PEAUIStorageFile@Storage@1@PEAUILauncherOptions@System@1@PEAUITelemetryCorrelationVector@@$$QEAV_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@@Z; Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<uchar,0>,bool,Windows::Internal::ComTaskPoolHandler,Windows::Storage::IStorageFile,Windows::System::ILauncherOptions,ITelemetryCorrelationVector,_lambda_1c837b4cf627ae89728bf991f02ea9b3_>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<bool> * *,TrustLevel,Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,_lambda_1c837b4cf627ae89728bf991f02ea9b3_ &&)
0x180050c80  mov     ebx, eax
0x180050c82  lea     rcx, [rbp+4A0h+var_1F0]; this
0x180050c89  call    ??1_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@QEAA@XZ; _lambda_1c837b4cf627ae89728bf991f02ea9b3_::~_lambda_1c837b4cf627ae89728bf991f02ea9b3_(void)
0x180050c8e  mov     edx, ebx
0x180050c90  lea     rcx, [rbp+4A0h+var_490]
0x180050c94  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180050c99  mov     rcx, [rbp+4A8h]; this
0x180050ca0  test    ebx, ebx
0x180050ca2  jns     short loc_180050CB9
0x180050ca4  mov     r9d, ebx; char *
0x180050ca7  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180050cae  mov     edx, 505h; void *
0x180050cb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050cb9  lea     rcx, [rbp+4A0h+var_340]; this
0x180050cc0  call    ??1LaunchFiles@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchFiles::~LaunchFiles(void)
0x180050cc5  nop
0x180050cc6  lea     rcx, [rbp+4A0h+var_4B8]; this
0x180050cca  call    ??1AsyncWindowOperation@Internal@Windows@@QEAA@XZ; Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation(void)
0x180050ccf  nop
0x180050cd0  lea     rcx, [rbp+4A0h+var_520]
0x180050cd4  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180050cd9  nop
0x180050cda  mov     rcx, [rbp+4A0h+pv]; pv
0x180050cde  call    cs:__imp_CoTaskMemFree
0x180050ce4  nop
0x180050ce5  mov     rcx, [rbp+4A0h+var_4C8]; pv
0x180050ce9  call    cs:__imp_CoTaskMemFree
0x180050cef  nop
0x180050cf0  mov     rcx, [rsp+5A0h+var_528]; pv
0x180050cf5  call    cs:__imp_CoTaskMemFree
0x180050cfb  nop
0x180050cfc  xor     ecx, ecx; pv
0x180050cfe  call    cs:__imp_CoTaskMemFree
0x180050d04  nop
0x180050d05  xor     ecx, ecx; pv
0x180050d07  call    cs:__imp_CoTaskMemFree
0x180050d0d  nop
0x180050d0e  lea     rcx, [rbp+4A0h+var_500]
0x180050d12  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180050d17  nop
0x180050d18  xor     ecx, ecx; pv
0x180050d1a  call    cs:__imp_CoTaskMemFree
0x180050d20  nop
0x180050d21  lea     rcx, [rbp+4A0h+var_490]; this
0x180050d25  call    ??1LaunchFiles@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchFiles::~LaunchFiles(void)
0x180050d2a  mov     rax, r14
0x180050d2d  mov     rcx, [rbp+4A0h+var_40]
0x180050d34  xor     rcx, rsp; StackCookie
0x180050d37  call    __security_check_cookie
0x180050d3c  add     rsp, 570h
0x180050d43  pop     r14
0x180050d45  pop     r13
0x180050d47  pop     r12
0x180050d49  pop     rdi
0x180050d4a  pop     rsi
0x180050d4b  pop     rbx
0x180050d4c  pop     rbp
0x180050d4d  retn
```
