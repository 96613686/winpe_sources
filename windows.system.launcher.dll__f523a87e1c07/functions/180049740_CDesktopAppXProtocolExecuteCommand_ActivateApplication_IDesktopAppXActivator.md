# CDesktopAppXProtocolExecuteCommand::ActivateApplication(IDesktopAppXActivator *)

- ea: `0x180049740`
- end: `0x180049c32`
- name: `?ActivateApplication@CDesktopAppXProtocolExecuteCommand@@MEAAXPEAUIDesktopAppXActivator@@@Z`
- size: `1266`
- prototype: `void __fastcall(CDesktopAppXProtocolExecuteCommand *__hidden this, struct IDesktopAppXActivator *)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001eb04`
- `0x1800210f8`
- `0x180023044`
- `0x18002cec0`
- `0x180049698`
- `0x180049740`
- `0x180049c38`
- `0x18004ab78`
- `0x18004acdc`
- `0x18004d560`
- `0x1800550d8`
- `0x180055194`
- `0x1800551ec`
- `0x180055298`
- `0x180055490`
- `0x18005552c`
- `0x1800556fc`
- `0x18005591c`
- `0x180055ac8`
- `0x180069b08`
- `0x180069b90`
- `0x180073d68`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049c2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004992c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004992c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049bdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049bdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b99`

## string_xrefs

- `0x180049907`: `Windows.AppUriHandler`
- `0x1800497ce`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x180049881`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x18004996d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x1800499ba`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x180049a77`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x180049b72`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\desktopappxexecutecommand.cpp`
- `0x180049910`: `Windows.Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CDesktopAppXProtocolExecuteCommand::ActivateApplication(
        CDesktopAppXProtocolExecuteCommand *this,
        struct IDesktopAppXActivator *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  int v7; // eax
  _QWORD *v8; // r8
  __int64 v9; // rax
  const WCHAR *v10; // rsi
  int v11; // eax
  void *v12; // rbx
  __int64 (__fastcall *v13)(void *, GUID *, _QWORD **); // rdi
  int v14; // eax
  DesktopAppXExecuteCommandBase *v15; // rcx
  __int64 UserContextToken; // rax
  __int64 v17; // rdi
  _QWORD *v18; // r14
  __int64 v19; // r15
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  int v22; // eax
  __int64 (__fastcall *v23)(struct IDesktopAppXActivator *, PCWSTR, PCWSTR, _QWORD *); // r15
  int v24; // esi
  _QWORD *v25; // r14
  PCWSTR v26; // rbx
  PCWSTR v27; // rax
  int v28; // ebx
  _QWORD *v29; // rcx
  void *v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+28h] [rbp-E0h]
  _QWORD *v33; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+68h] [rbp-A0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp-98h] BYREF
  void *v37; // [rsp+78h] [rbp-90h] BYREF
  const WCHAR *v38; // [rsp+80h] [rbp-88h] BYREF
  HSTRING string[2]; // [rsp+88h] [rbp-80h] BYREF
  GUID v40; // [rsp+98h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v42[3]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 v43; // [rsp+C8h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-20h]
  void **v46; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v47[272]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v48[8]; // [rsp+210h] [rbp+108h] BYREF
  _BYTE v49[48]; // [rsp+218h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v46);
  v46 = &LauncherDesktopProvider::Execute::`vftable';
  LauncherDesktopProvider::Execute::StartActivity((LauncherDesktopProvider::Execute *)&v46);
  LODWORD(v35) = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 20) + 56LL))(*((_QWORD *)this + 20), &v35);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      (const char *)(unsigned int)v4,
      v32);
  if ( !(_DWORD)v35 )
  {
    v46 = &LauncherDesktopProvider::Execute::`vftable';
    goto LABEL_5;
  }
  v34 = 0;
  v5 = *((_QWORD *)this + 20);
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  v7 = v6(v5, 0, &v34);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A2,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      (const char *)(unsigned int)v7,
      v32);
  DesktopAppXExecuteCommandBase::GetUriStringFromShellItem(retaddr, v42, v34);
  if ( *((_BYTE *)this + 240) )
  {
    v8 = v42;
    if ( v43 > 7 )
      v8 = (_QWORD *)v42[0];
    v32 = 0;
    v9 = DesktopAppXExecuteCommandBase::SubstituteParameterTemplate(this, &hstringHeader, v8, v34);
    std::wstring::operator=(v42, v9);
    std::wstring::_Tidy_deallocate(&hstringHeader);
  }
  LaunchExecuteCommandBase::GetCallerPackageFamilyName(this, string);
  v38 = 0;
  v10 = 0;
  if ( *((_DWORD *)this + 26) == 1 )
  {
    v10 = L"Windows.Protocol";
    goto LABEL_16;
  }
  if ( *((_DWORD *)this + 26) == 2 )
  {
    v10 = L"Windows.AppUriHandler";
LABEL_16:
    v38 = v10;
  }
  v37 = 0;
  v33 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
  *(_QWORD *)&v40.Data1 = *((_QWORD *)this + 20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v11 = Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *,unsigned short const *>(&v37);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      (const char *)(unsigned int)v11,
      v32);
  v12 = v37;
  v13 = **(__int64 (__fastcall ***)(void *, GUID *, _QWORD **))v37;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v14 = v13(v12, &GUID_99fc44e3_ce9a_4284_bf04_76331d1b1788, &v33);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      (const char *)(unsigned int)v14,
      v32);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols>::GetImpl'::`2'::impl) )
    UserContextToken = TryGetUserContextToken(v15);
  else
    UserContextToken = DesktopAppXExecuteCommandBase::GetUserToken(v15);
  v17 = UserContextToken;
  v18 = v33;
  v19 = *v33;
  v45 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v10[v20] );
  if ( v20 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180049C31LL);
  }
  v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v10, v21, v20);
  v40 = GUID_NULL;
  LOBYTE(v32) = 0;
  v22 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _QWORD))(v19 + 48))(v18, v17, v45, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      (const char *)(unsigned int)v22,
      v32);
  *(_QWORD *)&v40.Data1 = WindowsGetStringRawBuffer(*((HSTRING *)this + 26), 0);
  StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
  LauncherDesktopProvider::Execute::ActivateTarget<unsigned short const *,unsigned short const * &,unsigned short const *>(
    &v46,
    &StringRawBuffer,
    &v38,
    &v40);
  v23 = *(__int64 (__fastcall **)(struct IDesktopAppXActivator *, PCWSTR, PCWSTR, _QWORD *))(*(_QWORD *)a2 + 40LL);
  v24 = *((_DWORD *)this + 56);
  v25 = v42;
  if ( v43 > 7 )
    v25 = (_QWORD *)v42[0];
  v26 = WindowsGetStringRawBuffer(*((HSTRING *)this + 27), 0);
  v27 = WindowsGetStringRawBuffer(*((HSTRING *)this + 26), 0);
  v28 = v23(a2, v27, v26, v25);
  LODWORD(StringRawBuffer) = v28;
  TelemetryCorrelationVectorServiceProvider::Increment(&pv, *((_QWORD *)this + 4));
  *(_QWORD *)&v40.Data1 = pv;
  LauncherDesktopProvider::Execute::ActivationResult<long &,unsigned short const * &,char *>(
    &v46,
    &StringRawBuffer,
    &v38,
    &v40);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\desktopappxexecutecommand.cpp",
      (const char *)(unsigned int)v28,
      v24);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v46, 0);
  if ( pv )
    CoTaskMemFree(pv);
  v29 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
  }
  v30 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  WindowsDeleteString(string[0]);
  string[0] = 0;
  std::wstring::_Tidy_deallocate(v42);
  v31 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v46 = &LauncherDesktopProvider::Execute::`vftable';
LABEL_5:
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v46);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v49);
  wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v48);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(v47);
}

```

## disassembly

```asm
0x180049740  mov     rax, rsp
0x180049743  mov     [rax+18h], rbx
0x180049747  push    rbp
0x180049748  push    rsi
0x180049749  push    rdi
0x18004974a  push    r12
0x18004974c  push    r13
0x18004974e  push    r14
0x180049750  push    r15
0x180049752  lea     rbp, [rax-198h]
0x180049759  sub     rsp, 260h
0x180049760  movaps  xmmword ptr [rax-48h], xmm6
0x180049764  mov     rax, cs:__security_cookie
0x18004976b  xor     rax, rsp
0x18004976e  mov     [rbp+190h+var_50], rax
0x180049775  mov     r12, rdx
0x180049778  mov     r13, rcx
0x18004977b  lea     rdx, aExecute; "Execute"
0x180049782  lea     rcx, [rbp+190h+var_1A0]; struct wil::details::IFailureCallback *
0x180049786  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004978b  lea     rbx, ??_7Execute@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::Execute::`vftable'
0x180049792  mov     [rbp+190h+var_1A0], rbx
0x180049796  lea     rcx, [rbp+190h+var_1A0]; this
0x18004979a  call    ?StartActivity@Execute@LauncherDesktopProvider@@QEAAXXZ; LauncherDesktopProvider::Execute::StartActivity(void)
0x18004979f  nop
0x1800497a0  xor     r14d, r14d
0x1800497a3  mov     dword ptr [rsp+290h+var_230], r14d
0x1800497a8  mov     rcx, [r13+0A0h]
0x1800497af  mov     rax, [rcx]
0x1800497b2  lea     rdx, [rsp+290h+var_230]
0x1800497b7  mov     rax, [rax+38h]
0x1800497bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497c0  mov     rcx, [rbp+198h]; this
0x1800497c7  test    eax, eax
0x1800497c9  jns     short loc_1800497E0
0x1800497cb  mov     r9d, eax; char *
0x1800497ce  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x1800497d5  mov     edx, 29Ah; void *
0x1800497da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800497e0  cmp     dword ptr [rsp+290h+var_230], r14d
0x1800497e5  jnz     short loc_180049844
0x1800497e7  mov     [rbp+190h+var_1A0], rbx
0x1800497eb  lea     rcx, [rbp+190h+var_1A0]
0x1800497ef  call    ?Destroy@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800497f4  lea     rcx, [rbp+190h+var_80]; this
0x1800497fb  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180049800  lea     rcx, [rbp+190h+var_88]
0x180049807  call    ?reset@?$shared_object@V?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18004980c  lea     rcx, [rbp+190h+var_198]
0x180049810  call    ??1?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180049815  mov     rcx, [rbp+190h+var_50]
0x18004981c  xor     rcx, rsp; StackCookie
0x18004981f  call    __security_check_cookie
0x180049824  lea     r11, [rsp+290h+var_30]
0x18004982c  mov     rbx, [r11+50h]
0x180049830  movaps  xmm6, xmmword ptr [r11-10h]
0x180049835  mov     rsp, r11
0x180049838  pop     r15
0x18004983a  pop     r14
0x18004983c  pop     r13
0x18004983e  pop     r12
0x180049840  pop     rdi
0x180049841  pop     rsi
0x180049842  pop     rbp
0x180049843  retn
0x180049844  mov     [rsp+290h+var_238], r14
0x180049849  mov     rdi, [r13+0A0h]
0x180049850  mov     rax, [rdi]
0x180049853  mov     rbx, [rax+40h]
0x180049857  lea     rcx, [rsp+290h+var_238]
0x18004985c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049861  lea     r8, [rsp+290h+var_238]
0x180049866  xor     edx, edx
0x180049868  mov     rcx, rdi
0x18004986b  mov     rax, rbx
0x18004986e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049873  mov     rcx, [rbp+198h]; this
0x18004987a  test    eax, eax
0x18004987c  jns     short loc_180049893
0x18004987e  mov     r9d, eax; char *
0x180049881  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x180049888  mov     edx, 2A2h; void *
0x18004988d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049893  mov     r8, [rsp+290h+var_238]
0x180049898  lea     rdx, [rbp+190h+var_1E8]
0x18004989c  call    ?GetUriStringFromShellItem@DesktopAppXExecuteCommandBase@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIShellItem@@@Z; DesktopAppXExecuteCommandBase::GetUriStringFromShellItem(IShellItem *)
0x1800498a1  nop
0x1800498a2  cmp     [r13+0F0h], r14b
0x1800498a9  jz      short loc_1800498E4
0x1800498ab  lea     r8, [rbp+190h+var_1E8]
0x1800498af  cmp     [rbp+190h+var_1D0], 7
0x1800498b4  cmova   r8, [rbp+190h+var_1E8]
0x1800498b9  mov     qword ptr [rsp+290h+var_270], r14; int
0x1800498be  mov     r9, [rsp+290h+var_238]
0x1800498c3  lea     rdx, [rbp+190h+hstringHeader]
0x1800498c7  mov     rcx, r13
0x1800498ca  call    ?SubstituteParameterTemplate@DesktopAppXExecuteCommandBase@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAUIShellItem@@0@Z; DesktopAppXExecuteCommandBase::SubstituteParameterTemplate(ushort const *,IShellItem *,ushort const *)
0x1800498cf  mov     rdx, rax
0x1800498d2  lea     rcx, [rbp+190h+var_1E8]
0x1800498d6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800498db  lea     rcx, [rbp+190h+hstringHeader]
0x1800498df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800498e4  lea     rdx, [rbp+190h+string]
0x1800498e8  mov     rcx, r13
0x1800498eb  call    ?GetCallerPackageFamilyName@LaunchExecuteCommandBase@@IEAA?AVHString@Wrappers@WRL@Microsoft@@XZ; LaunchExecuteCommandBase::GetCallerPackageFamilyName(void)
0x1800498f0  nop
0x1800498f1  mov     [rsp+290h+var_218], r14
0x1800498f6  mov     rsi, r14
0x1800498f9  mov     ecx, [r13+68h]
0x1800498fd  sub     ecx, 1
0x180049900  jz      short loc_180049910
0x180049902  cmp     ecx, 1
0x180049905  jnz     short loc_18004991C
0x180049907  lea     rsi, aWindowsAppurih; "Windows.AppUriHandler"
0x18004990e  jmp     short loc_180049917
0x180049910  lea     rsi, aWindowsProtoco; "Windows.Protocol"
0x180049917  mov     [rsp+290h+var_218], rsi
0x18004991c  mov     [rsp+290h+var_220], r14
0x180049921  mov     [rsp+290h+var_240], r14
0x180049926  xor     edx, edx; length
0x180049928  mov     rcx, [rbp+190h+string]; string
0x18004992c  call    cs:__imp_WindowsGetStringRawBuffer
0x180049932  mov     [rsp+290h+var_228], rax
0x180049937  mov     rax, [r13+0A0h]
0x18004993e  mov     qword ptr [rbp+190h+var_200], rax
0x180049942  lea     rcx, [rsp+290h+var_220]
0x180049947  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004994c  lea     r8, [rsp+290h+var_228]
0x180049951  lea     rdx, [rbp+190h+var_200]
0x180049955  lea     rcx, [rsp+290h+var_220]; void **
0x18004995a  call    ??$MakeAndInitialize@VCProtocolActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIShellItemArray@@PEBG@Details@WRL@Microsoft@@YAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@$$QEAPEAUIShellItemArray@@$$QEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *,ushort const *>(Windows::ApplicationModel::Activation::IActivatedEventArgs * *,IShellItemArray * &&,ushort const * &&)
0x18004995f  mov     rcx, [rbp+198h]; this
0x180049966  test    eax, eax
0x180049968  jns     short loc_18004997F
0x18004996a  mov     r9d, eax; char *
0x18004996d  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x180049974  mov     edx, 2BBh; void *
0x180049979  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004997f  mov     rbx, [rsp+290h+var_220]
0x180049984  mov     rax, [rbx]
0x180049987  mov     rdi, [rax]
0x18004998a  lea     rcx, [rsp+290h+var_240]
0x18004998f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049994  lea     r8, [rsp+290h+var_240]
0x180049999  lea     rdx, _GUID_99fc44e3_ce9a_4284_bf04_76331d1b1788
0x1800499a0  mov     rcx, rbx
0x1800499a3  mov     rax, rdi
0x1800499a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499ab  nop
0x1800499ac  mov     rcx, [rbp+198h]; this
0x1800499b3  test    eax, eax
0x1800499b5  jns     short loc_1800499CC
0x1800499b7  mov     r9d, eax; char *
0x1800499ba  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x1800499c1  mov     edx, 2BCh; void *
0x1800499c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800499cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols> `wil::Feature<__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols>::GetImpl(void)'::`2'::impl
0x1800499d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableOtsElevationToLaunchAppsViaProtocols>::__private_IsEnabled(void)
0x1800499d8  test    al, al
0x1800499da  jz      short loc_1800499E3
0x1800499dc  call    TryGetUserContextToken
0x1800499e1  jmp     short loc_1800499E8
0x1800499e3  call    ?GetUserToken@DesktopAppXExecuteCommandBase@@IEAA_KXZ; DesktopAppXExecuteCommandBase::GetUserToken(void)
0x1800499e8  mov     rdi, rax
0x1800499eb  mov     r14, [rsp+290h+var_240]
0x1800499f0  mov     r15, [r14]
0x1800499f3  xor     ecx, ecx
0x1800499f5  mov     [rbp+190h+var_1B0], rcx
0x1800499f9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800499fd  inc     rbx
0x180049a00  cmp     [rsi+rbx*2], cx
0x180049a04  jnz     short loc_1800499FD
0x180049a06  mov     eax, 0FFFFFFFFh
0x180049a0b  cmp     rbx, rax
0x180049a0e  ja      loc_180049C1C
0x180049a14  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180049a1b  mov     ecx, ebx; unsigned int
0x180049a1d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180049a22  mov     r9d, ebx; unsigned int
0x180049a25  mov     r8d, eax; unsigned int
0x180049a28  mov     rdx, rsi; sourceString
0x180049a2b  lea     rcx, [rbp+190h+hstringHeader]; hstringHeader
0x180049a2f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049a34  nop
0x180049a35  movdqu  [rbp+190h+var_200], xmm6
0x180049a3a  lea     rax, [rbp+190h+var_200]
0x180049a3e  mov     [rsp+290h+var_258], rax
0x180049a43  xor     ebx, ebx
0x180049a45  mov     [rsp+290h+var_260], rbx
0x180049a4a  mov     byte ptr [rsp+290h+var_268], 1
0x180049a4f  mov     byte ptr [rsp+290h+var_270], bl; int
0x180049a53  xor     r9d, r9d
0x180049a56  mov     r8, [rbp+190h+var_1B0]
0x180049a5a  mov     rdx, rdi
0x180049a5d  mov     rcx, r14
0x180049a60  mov     rax, [r15+30h]
0x180049a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a69  mov     rcx, [rbp+198h]; this
0x180049a70  test    eax, eax
0x180049a72  jns     short loc_180049A89
0x180049a74  mov     r9d, eax; char *
0x180049a77  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x180049a7e  mov     edx, 2C8h; void *
0x180049a83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049a89  xor     edx, edx; length
0x180049a8b  mov     rcx, [r13+0D0h]; string
0x180049a92  call    cs:__imp_WindowsGetStringRawBuffer
0x180049a98  mov     qword ptr [rbp+190h+var_200], rax
0x180049a9c  xor     edx, edx; length
0x180049a9e  mov     rcx, [rbp+190h+string]; string
0x180049aa2  call    cs:__imp_WindowsGetStringRawBuffer
0x180049aa8  mov     [rsp+290h+var_228], rax
0x180049aad  lea     r9, [rbp+190h+var_200]
0x180049ab1  lea     r8, [rsp+290h+var_218]
0x180049ab6  lea     rdx, [rsp+290h+var_228]
0x180049abb  lea     rcx, [rbp+190h+var_1A0]
0x180049abf  call    ??$ActivateTarget@PEBGAEAPEBGPEBG@Execute@LauncherDesktopProvider@@QEAAX$$QEAPEBGAEAPEBG0@Z; LauncherDesktopProvider::Execute::ActivateTarget<ushort const *,ushort const * &,ushort const *>(ushort const * &&,ushort const * &,ushort const * &&)
0x180049ac4  mov     rax, [r12]
0x180049ac8  mov     r15, [rax+28h]
0x180049acc  mov     rdi, [rsp+290h+var_240]
0x180049ad1  mov     esi, [r13+0E0h]
0x180049ad8  lea     r14, [rbp+190h+var_1E8]
0x180049adc  cmp     [rbp+190h+var_1D0], 7
0x180049ae1  cmova   r14, [rbp+190h+var_1E8]
0x180049ae6  xor     edx, edx; length
0x180049ae8  mov     rcx, [r13+0D8h]; string
0x180049aef  call    cs:__imp_WindowsGetStringRawBuffer
0x180049af5  mov     rbx, rax
0x180049af8  xor     edx, edx; length
0x180049afa  mov     rcx, [r13+0D0h]; string
0x180049b01  call    cs:__imp_WindowsGetStringRawBuffer
0x180049b07  xor     ecx, ecx
0x180049b09  mov     [rsp+290h+var_258], rcx
0x180049b0e  mov     [rsp+290h+var_260], rdi
0x180049b13  xor     edi, edi
0x180049b15  mov     dword ptr [rsp+290h+var_268], edi
0x180049b19  mov     [rsp+290h+var_270], esi; int
0x180049b1d  mov     r9, r14
0x180049b20  mov     r8, rbx
0x180049b23  mov     rdx, rax
0x180049b26  mov     rcx, r12
0x180049b29  mov     rax, r15
0x180049b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b31  mov     ebx, eax
0x180049b33  mov     dword ptr [rsp+290h+var_228], eax
0x180049b37  mov     rdx, [r13+20h]
0x180049b3b  lea     rcx, [rbp+190h+pv]
0x180049b3f  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180049b44  nop
0x180049b45  mov     rcx, [rbp+190h+pv]
0x180049b49  mov     qword ptr [rbp+190h+var_200], rcx
0x180049b4d  lea     r9, [rbp+190h+var_200]
0x180049b51  lea     r8, [rsp+290h+var_218]
0x180049b56  lea     rdx, [rsp+290h+var_228]
0x180049b5b  lea     rcx, [rbp+190h+var_1A0]
0x180049b5f  call    ??$ActivationResult@AEAJAEAPEBGPEAD@Execute@LauncherDesktopProvider@@QEAAXAEAJAEAPEBG$$QEAPEAD@Z; LauncherDesktopProvider::Execute::ActivationResult<long &,ushort const * &,char *>(long &,ushort const * &,char * &&)
0x180049b64  mov     rcx, [rbp+198h]; this
0x180049b6b  test    ebx, ebx
0x180049b6d  jns     short loc_180049B84
0x180049b6f  mov     r9d, ebx; char *
0x180049b72  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\windows.system.launc"...
0x180049b79  mov     edx, 2D6h; void *
0x180049b7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049b84  xor     edx, edx
0x180049b86  lea     rcx, [rbp+190h+var_1A0]
0x180049b8a  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180049b8f  nop
0x180049b90  mov     rcx, [rbp+190h+pv]; pv
0x180049b94  test    rcx, rcx
0x180049b97  jz      short loc_180049BA0
0x180049b99  call    cs:__imp_CoTaskMemFree
0x180049b9f  nop
0x180049ba0  mov     rcx, [rsp+290h+var_240]
0x180049ba5  test    rcx, rcx
0x180049ba8  jz      short loc_180049BBC
0x180049baa  mov     [rsp+290h+var_240], rdi
0x180049baf  mov     rax, [rcx]
0x180049bb2  mov     rax, [rax+10h]
0x180049bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bbb  nop
0x180049bbc  mov     rcx, [rsp+290h+var_220]
0x180049bc1  test    rcx, rcx
0x180049bc4  jz      short loc_180049BD8
0x180049bc6  mov     [rsp+290h+var_220], rdi
0x180049bcb  mov     rax, [rcx]
0x180049bce  mov     rax, [rax+10h]
0x180049bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bd7  nop
0x180049bd8  mov     rcx, [rbp+190h+string]; string
0x180049bdc  call    cs:__imp_WindowsDeleteString
0x180049be2  mov     [rbp+190h+string], rdi
0x180049be6  lea     rcx, [rbp+190h+var_1E8]
0x180049bea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049bef  nop
0x180049bf0  mov     rcx, [rsp+290h+var_238]
0x180049bf5  test    rcx, rcx
0x180049bf8  jz      short loc_180049C0C
0x180049bfa  mov     [rsp+290h+var_238], rdi
0x180049bff  mov     rax, [rcx]
0x180049c02  mov     rax, [rax+10h]
  ... truncated ...
```
