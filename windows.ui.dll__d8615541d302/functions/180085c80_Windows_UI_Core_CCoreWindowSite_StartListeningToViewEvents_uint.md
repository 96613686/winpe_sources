# Windows::UI::Core::CCoreWindowSite::StartListeningToViewEvents(uint)

- ea: `0x180085c80`
- end: `0x180085f26`
- name: `?StartListeningToViewEvents@CCoreWindowSite@Core@UI@Windows@@UEAAJI@Z`
- size: `678`
- prototype: `int(Windows::UI::Core::CCoreWindowSite *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x18002b770`
- `0x180048ff4`
- `0x18005bb78`
- `0x18007fbe0`
- `0x180080bd4`
- `0x180081058`
- `0x1800813ac`
- `0x180085bd8`
- `0x180085c80`
- `0x180088854`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085ea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085ea8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085e53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085e67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085e7a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085e53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085e67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085e7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085dbd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085dd7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085df1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085dbd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085dd7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085df1`

## string_xrefs

- `0x180085ed3`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::StartListeningToViewEvents(
        Windows::UI::Core::CCoreWindowSite *this,
        unsigned int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  PTP_WAIT ThreadpoolWait; // rbx
  PTP_WAIT v10; // rdi
  PTP_WAIT v11; // rsi
  Windows::UI::Core::CCoreWindowSite *v12; // rdi
  PTP_WAIT *v13; // rbx
  int v15; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  Windows::UI::Core::CCoreWindowSite *v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v22[42]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v24; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v17 = this;
  wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v22);
  v22[0] = &CUITelemetry::StartListeningToViewEvents::`vftable';
  CUITelemetry::StartListeningToViewEvents::StartActivity((CUITelemetry::StartListeningToViewEvents *)v22, a2);
  v16 = 0;
  if ( !*((_QWORD *)this + 15) )
  {
    v5 = -2147418113;
    v6 = 2147549183LL;
    v7 = 1556;
    goto LABEL_10;
  }
  v4 = Microsoft::WRL::ComPtr<Windows::Internal::OneCore::ViewEventHandlers::ICoreCUIBroker>::As<IRetrieveViewCUIEventHandle>(
         (char *)this + 120,
         &v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 1552;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)v6,
      v15);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
    goto LABEL_11;
  }
  v23 = 0;
  v24 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *))(*(_QWORD *)v16 + 40LL))(v16, a2, 3, &v23);
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = (unsigned int)v8;
    v7 = 1560;
    goto LABEL_10;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 488);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 368,
    v23);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 376,
    *((_QWORD *)&v23 + 1));
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 384,
    v24);
  ThreadpoolWait = CreateThreadpoolWait(
                     lambda_1cfd3d0ce0681104adb03537076ff12e_::_lambda_invoker_cdecl_,
                     *((PVOID *)this + 22),
                     0);
  v10 = CreateThreadpoolWait(lambda_f105acca93f3cdc68200f3b3e75b3f7c_::_lambda_invoker_cdecl_, *((PVOID *)this + 22), 0);
  v11 = CreateThreadpoolWait(lambda_308459fe291f451c231b1fe1f73bb532_::_lambda_invoker_cdecl_, *((PVOID *)this + 22), 0);
  v20 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 392,
    ThreadpoolWait);
  v19 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 400,
    v10);
  v18 = 0;
  v12 = v17;
  v13 = (PTP_WAIT *)((char *)v17 + 408);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)v17 + 408,
    v11);
  SetThreadpoolWait(*((PTP_WAIT *)this + 49), *((HANDLE *)this + 46), 0);
  SetThreadpoolWait(*((PTP_WAIT *)this + 50), *((HANDLE *)this + 47), 0);
  SetThreadpoolWait(*v13, *((HANDLE *)v12 + 48), 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(&v20);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v22);
  v5 = 0;
LABEL_11:
  CUITelemetry::StartListeningToViewEvents::~StartListeningToViewEvents((CUITelemetry::StartListeningToViewEvents *)v22);
  return v5;
}

```

## disassembly

```asm
0x180085c80  mov     [rsp-8+arg_10], rbx
0x180085c85  push    rbp
0x180085c86  push    rsi
0x180085c87  push    rdi
0x180085c88  push    r12
0x180085c8a  push    r13
0x180085c8c  push    r14
0x180085c8e  push    r15
0x180085c90  lea     rbp, [rsp-0D0h]
0x180085c98  sub     rsp, 1D0h
0x180085c9f  mov     rax, cs:__security_cookie
0x180085ca6  xor     rax, rsp
0x180085ca9  mov     [rbp+100h+var_38], rax
0x180085cb0  mov     edi, edx
0x180085cb2  mov     r14, rcx
0x180085cb5  mov     [rsp+200h+var_1C8], rcx
0x180085cba  lea     rdx, aStartlistening; "StartListeningToViewEvents"
0x180085cc1  lea     rcx, [rsp+200h+var_1A0]; struct wil::details::IFailureCallback *
0x180085cc6  call    ??0?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180085ccb  lea     rax, ??_7StartListeningToViewEvents@CUITelemetry@@6B@; const CUITelemetry::StartListeningToViewEvents::`vftable'
0x180085cd2  mov     [rsp+200h+var_1A0], rax
0x180085cd7  mov     edx, edi; unsigned int
0x180085cd9  lea     rcx, [rsp+200h+var_1A0]; this
0x180085cde  call    ?StartActivity@StartListeningToViewEvents@CUITelemetry@@QEAAXI@Z; CUITelemetry::StartListeningToViewEvents::StartActivity(uint)
0x180085ce3  nop
0x180085ce4  lea     rcx, [r14+78h]
0x180085ce8  xor     r15d, r15d
0x180085ceb  mov     [rsp+200h+var_1D0], r15
0x180085cf0  cmp     [rcx], r15
0x180085cf3  jz      loc_180085EC6
0x180085cf9  lea     rdx, [rsp+200h+var_1D0]
0x180085cfe  call    ??$As@UIRetrieveViewCUIEventHandle@@@?$ComPtr@UICoreCUIBroker@ViewEventHandlers@OneCore@Internal@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIRetrieveViewCUIEventHandle@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Internal::OneCore::ViewEventHandlers::ICoreCUIBroker>::As<IRetrieveViewCUIEventHandle>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IRetrieveViewCUIEventHandle>>)
0x180085d03  mov     ebx, eax
0x180085d05  test    eax, eax
0x180085d07  jns     short loc_180085D16
0x180085d09  mov     r9d, eax
0x180085d0c  mov     edx, 610h
0x180085d11  jmp     loc_180085ED3
0x180085d16  xorps   xmm0, xmm0
0x180085d19  xor     eax, eax
0x180085d1b  movups  [rbp+100h+var_50], xmm0
0x180085d22  mov     [rbp+100h+var_40], rax
0x180085d29  mov     rcx, [rsp+200h+var_1D0]
0x180085d2e  mov     rax, [rcx]
0x180085d31  lea     r9, [rbp+100h+var_50]
0x180085d38  mov     r8d, 3
0x180085d3e  mov     edx, edi
0x180085d40  mov     rax, [rax+28h]
0x180085d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d49  mov     ebx, eax
0x180085d4b  test    eax, eax
0x180085d4d  jns     short loc_180085D5C
0x180085d4f  mov     r9d, eax
0x180085d52  mov     edx, 618h
0x180085d57  jmp     loc_180085ED3
0x180085d5c  lea     rdx, [r14+1E8h]
0x180085d63  lea     rcx, [rsp+200h+SRWLock]
0x180085d68  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180085d6d  lea     r12, [r14+170h]
0x180085d74  mov     rdx, qword ptr [rbp+100h+var_50]
0x180085d7b  mov     rcx, r12
0x180085d7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180085d83  lea     r13, [r14+178h]
0x180085d8a  mov     rdx, qword ptr [rbp+100h+var_50+8]
0x180085d91  mov     rcx, r13
0x180085d94  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180085d99  lea     rcx, [r14+180h]
0x180085da0  mov     rdx, [rbp+100h+var_40]
0x180085da7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180085dac  xor     r8d, r8d; pcbe
0x180085daf  mov     rdx, [r14+0B0h]; pv
0x180085db6  lea     rcx, _lambda_1cfd3d0ce0681104adb03537076ff12e____lambda_invoker_cdecl_; pfnwa
0x180085dbd  call    cs:__imp_CreateThreadpoolWait
0x180085dc3  mov     rbx, rax
0x180085dc6  xor     r8d, r8d; pcbe
0x180085dc9  mov     rdx, [r14+0B0h]; pv
0x180085dd0  lea     rcx, _lambda_f105acca93f3cdc68200f3b3e75b3f7c____lambda_invoker_cdecl_; pfnwa
0x180085dd7  call    cs:__imp_CreateThreadpoolWait
0x180085ddd  mov     rdi, rax
0x180085de0  xor     r8d, r8d; pcbe
0x180085de3  mov     rdx, [r14+0B0h]; pv
0x180085dea  lea     rcx, _lambda_308459fe291f451c231b1fe1f73bb532____lambda_invoker_cdecl_; pfnwa
0x180085df1  call    cs:__imp_CreateThreadpoolWait
0x180085df7  mov     rsi, rax
0x180085dfa  mov     [rsp+200h+var_1B0], r15
0x180085dff  lea     r15, [r14+188h]
0x180085e06  mov     rdx, rbx
0x180085e09  mov     rcx, r15
0x180085e0c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180085e11  mov     [rsp+200h+var_1B8], 0
0x180085e1a  mov     rdx, rdi
0x180085e1d  lea     rcx, [r14+190h]
0x180085e24  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180085e29  mov     [rsp+200h+var_1C0], 0
0x180085e32  mov     rdi, [rsp+200h+var_1C8]
0x180085e37  lea     rbx, [rdi+198h]
0x180085e3e  mov     rdx, rsi
0x180085e41  mov     rcx, rbx
0x180085e44  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180085e49  xor     r8d, r8d; pftTimeout
0x180085e4c  mov     rdx, [r12]; h
0x180085e50  mov     rcx, [r15]; pwa
0x180085e53  call    cs:__imp_SetThreadpoolWait
0x180085e59  xor     r8d, r8d; pftTimeout
0x180085e5c  mov     rdx, [r13+0]; h
0x180085e60  mov     rcx, [r14+190h]; pwa
0x180085e67  call    cs:__imp_SetThreadpoolWait
0x180085e6d  xor     r8d, r8d; pftTimeout
0x180085e70  mov     rdx, [rdi+180h]; h
0x180085e77  mov     rcx, [rbx]; pwa
0x180085e7a  call    cs:__imp_SetThreadpoolWait
0x180085e80  lea     rcx, [rsp+200h+var_1C0]
0x180085e85  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x180085e8a  lea     rcx, [rsp+200h+var_1B8]
0x180085e8f  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x180085e94  lea     rcx, [rsp+200h+var_1B0]
0x180085e99  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x180085e9e  mov     rcx, [rsp+200h+SRWLock]; SRWLock
0x180085ea3  test    rcx, rcx
0x180085ea6  jz      short loc_180085EAE
0x180085ea8  call    cs:__imp_ReleaseSRWLockExclusive
0x180085eae  lea     rcx, [rsp+200h+var_1D0]
0x180085eb3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085eb8  lea     rcx, [rsp+200h+var_1A0]
0x180085ebd  call    ?Stop@?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180085ec2  xor     ebx, ebx
0x180085ec4  jmp     short loc_180085EF0
0x180085ec6  mov     ebx, 8000FFFFh
0x180085ecb  mov     r9d, ebx; char *
0x180085ece  mov     edx, 614h; void *
0x180085ed3  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180085eda  mov     rcx, [rbp+108h]; this
0x180085ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085ee6  lea     rcx, [rsp+200h+var_1D0]
0x180085eeb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085ef0  lea     rcx, [rsp+200h+var_1A0]; this
0x180085ef5  call    ??1StartListeningToViewEvents@CUITelemetry@@QEAA@XZ; CUITelemetry::StartListeningToViewEvents::~StartListeningToViewEvents(void)
0x180085efa  mov     eax, ebx
0x180085efc  mov     rcx, [rbp+100h+var_38]
0x180085f03  xor     rcx, rsp; StackCookie
0x180085f06  call    __security_check_cookie
0x180085f0b  mov     rbx, [rsp+200h+arg_10]
0x180085f13  add     rsp, 1D0h
0x180085f1a  pop     r15
0x180085f1c  pop     r14
0x180085f1e  pop     r13
0x180085f20  pop     r12
0x180085f22  pop     rdi
0x180085f23  pop     rsi
0x180085f24  pop     rbp
0x180085f25  retn
```
