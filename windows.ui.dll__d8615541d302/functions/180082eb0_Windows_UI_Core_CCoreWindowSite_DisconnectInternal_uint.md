# Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)

- ea: `0x180082eb0`
- end: `0x1800831db`
- name: `?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z`
- size: `811`
- prototype: `int(Windows::UI::Core::CCoreWindowSite *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180081cc0`
- `0x180082e20`

## callees

- `0x1800038e0`
- `0x18000f048`
- `0x180014754`
- `0x18002b770`
- `0x18004ed78`
- `0x18005bb78`
- `0x18007faf0`
- `0x18007fb40`
- `0x18007fb90`
- `0x180080a08`
- `0x180080bd4`
- `0x1800812fc`
- `0x180082eb0`
- `0x180085790`
- `0x180088854`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082f4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008316e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082f4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008316e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180083107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180083107`

## string_xrefs

- `0x180082f50`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
        Windows::UI::Core::CCoreWindowSite *this,
        unsigned int a2)
{
  int v4; // edi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rbx
  int v12; // eax
  int v13; // ebx
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-E0h] BYREF
  struct Windows::UI::Core::ICoreWindow *v16; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v19[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v19);
  v19[0] = &CUITelemetry::CoreWindowSiteDisconnect::`vftable';
  CUITelemetry::CoreWindowSiteDisconnect::StartActivity((CUITelemetry::CoreWindowSiteDisconnect *)v19, a2);
  v4 = 0;
  *(_WORD *)((char *)this + 97) = 0;
  v5 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 184);
  v6 = (RTL_SRWLOCK *)*((_QWORD *)this + 22);
  if ( v6 )
  {
    *((_QWORD *)this + 22) = 0;
    v5 = v6;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    SRWLock = v5;
    v7 = Windows::Internal::ComTaskPool::QueueTask__lambda_d82e5e7068e60841e2f209492d472848___();
    v4 = v7;
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x388,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v7,
        (int)SRWLock);
  }
  v8 = *((_QWORD *)this + 25);
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 56LL))(v8);
    v4 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A0,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v9,
        (int)SRWLock);
  }
  v16 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  if ( (unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread(&v16) )
  {
    SRWLock = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow2>(
            &v16,
            &SRWLock);
    if ( v10 >= 0 )
    {
      v11 = (_QWORD *)((char *)this + 344);
      v12 = (*((__int64 (__fastcall **)(PSRWLOCK, _QWORD))SRWLock->Ptr + 20))(SRWLock, *((_QWORD *)this + 43));
      if ( v12 >= 0 )
      {
        v17 = 0;
        if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow4>(
                    &v16,
                    &v17) >= 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 128LL))(v17, *((_QWORD *)this + 44));
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 144LL))(v17, *((_QWORD *)this + 45));
        }
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v17);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3AB,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v12,
          (int)SRWLock);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v10,
        (int)SRWLock);
      v11 = (_QWORD *)((char *)this + 344);
    }
    v18 = 0;
    v4 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow5>(&v16, &v18);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 56LL))(v18, 0);
    *v11 = 0;
    *((_QWORD *)this + 44) = 0;
    *((_QWORD *)this + 45) = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&SRWLock);
  }
  else
  {
    v13 = *((_DWORD *)this + 26);
    if ( v13 != GetCurrentThreadId() )
    {
      v4 = -2147418113;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3CD,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)0x8000FFFFLL,
        (int)SRWLock);
    }
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 504);
  if ( *((_QWORD *)this + 51) )
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      (char *)this + 408,
      0);
  if ( *((_QWORD *)this + 53) )
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      (char *)this + 424,
      0);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 >= 0 )
  {
    wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DE,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v4,
      (int)SRWLock);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  CUITelemetry::CoreWindowSiteDisconnect::~CoreWindowSiteDisconnect((CUITelemetry::CoreWindowSiteDisconnect *)v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180082eb0  mov     [rsp-8+arg_10], rbx
0x180082eb5  push    rbp
0x180082eb6  push    rsi
0x180082eb7  push    rdi
0x180082eb8  push    r14
0x180082eba  push    r15
0x180082ebc  lea     rbp, [rsp-0A0h]
0x180082ec4  sub     rsp, 1A0h
0x180082ecb  mov     rax, cs:__security_cookie
0x180082ed2  xor     rax, rsp
0x180082ed5  mov     [rbp+0C0h+var_30], rax
0x180082edc  mov     ebx, edx
0x180082ede  mov     rsi, rcx
0x180082ee1  lea     rdx, aCorewindowsite_35; "CoreWindowSiteDisconnect"
0x180082ee8  lea     rcx, [rsp+1C0h+var_180]; struct wil::details::IFailureCallback *
0x180082eed  call    ??0?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180082ef2  lea     rax, ??_7CoreWindowSiteDisconnect@CUITelemetry@@6B@; const CUITelemetry::CoreWindowSiteDisconnect::`vftable'
0x180082ef9  mov     [rsp+1C0h+var_180], rax
0x180082efe  mov     edx, ebx; unsigned int
0x180082f00  lea     rcx, [rsp+1C0h+var_180]; this
0x180082f05  call    ?StartActivity@CoreWindowSiteDisconnect@CUITelemetry@@QEAAXI@Z; CUITelemetry::CoreWindowSiteDisconnect::StartActivity(uint)
0x180082f0a  nop
0x180082f0b  xor     r14d, r14d
0x180082f0e  mov     edi, r14d
0x180082f11  mov     [rsi+61h], r14w
0x180082f16  mov     ebx, r14d
0x180082f19  lea     rdx, [rsi+0B8h]
0x180082f20  lea     rcx, [rsp+1C0h+SRWLock]
0x180082f25  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180082f2a  mov     rax, [rsi+0B0h]
0x180082f31  test    rax, rax
0x180082f34  jz      short loc_180082F40
0x180082f36  mov     [rsi+0B0h], r14
0x180082f3d  mov     rbx, rax
0x180082f40  mov     rcx, [rsp+1C0h+SRWLock]; SRWLock
0x180082f45  test    rcx, rcx
0x180082f48  jz      short loc_180082F50
0x180082f4a  call    cs:__imp_ReleaseSRWLockExclusive
0x180082f50  lea     r15, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180082f57  test    rbx, rbx
0x180082f5a  jz      short loc_180082F88
0x180082f5c  mov     [rsp+1C0h+SRWLock], rbx; int
0x180082f61  lea     rdx, [rsp+1C0h+SRWLock]
0x180082f66  call    Windows__Internal__ComTaskPool__QueueTask__lambda_d82e5e7068e60841e2f209492d472848___
0x180082f6b  mov     edi, eax
0x180082f6d  mov     rcx, [rbp+0C8h]; this
0x180082f74  test    eax, eax
0x180082f76  jns     short loc_180082F88
0x180082f78  mov     r9d, eax; char *
0x180082f7b  mov     r8, r15; unsigned int
0x180082f7e  mov     edx, 388h; void *
0x180082f83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082f88  mov     rcx, [rsi+0C8h]
0x180082f8f  test    rcx, rcx
0x180082f92  jz      short loc_180082FBD
0x180082f94  mov     rax, [rcx]
0x180082f97  mov     rax, [rax+38h]
0x180082f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082fa0  mov     edi, eax
0x180082fa2  mov     rcx, [rbp+0C8h]; this
0x180082fa9  test    eax, eax
0x180082fab  jns     short loc_180082FBD
0x180082fad  mov     r9d, eax; char *
0x180082fb0  mov     r8, r15; unsigned int
0x180082fb3  mov     edx, 3A0h; void *
0x180082fb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082fbd  mov     [rsp+1C0h+var_198], r14
0x180082fc2  lea     rcx, [rsp+1C0h+var_198]
0x180082fc7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082fcc  lea     rcx, [rsp+1C0h+var_198]; struct Windows::UI::Core::ICoreWindow **
0x180082fd1  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x180082fd6  test    eax, eax
0x180082fd8  jz      loc_180083104
0x180082fde  mov     [rsp+1C0h+SRWLock], r14; int
0x180082fe3  lea     rdx, [rsp+1C0h+SRWLock]
0x180082fe8  lea     rcx, [rsp+1C0h+var_198]
0x180082fed  call    ??$As@UIInternalCoreWindow2@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow2@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow2>>)
0x180082ff2  mov     rcx, [rbp+0C8h]; this
0x180082ff9  test    eax, eax
0x180082ffb  jns     short loc_180083019
0x180082ffd  mov     r9d, eax; char *
0x180083000  mov     r8, r15; unsigned int
0x180083003  mov     edx, 3A8h; void *
0x180083008  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008300d  lea     rbx, [rsi+158h]
0x180083014  jmp     loc_1800830AD
0x180083019  mov     rcx, [rsp+1C0h+SRWLock]
0x18008301e  lea     rbx, [rsi+158h]
0x180083025  mov     rax, [rcx]
0x180083028  mov     rdx, [rbx]
0x18008302b  mov     rax, [rax+0A0h]
0x180083032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083037  mov     rcx, [rbp+0C8h]; this
0x18008303e  test    eax, eax
0x180083040  jns     short loc_180083054
0x180083042  mov     r9d, eax; char *
0x180083045  mov     r8, r15; unsigned int
0x180083048  mov     edx, 3ABh; void *
0x18008304d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083052  jmp     short loc_1800830AD
0x180083054  mov     [rsp+1C0h+var_190], r14
0x180083059  lea     rdx, [rsp+1C0h+var_190]
0x18008305e  lea     rcx, [rsp+1C0h+var_198]
0x180083063  call    ??$As@UIInternalCoreWindow4@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow4@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow4>>)
0x180083068  test    eax, eax
0x18008306a  js      short loc_1800830A3
0x18008306c  mov     rcx, [rsp+1C0h+var_190]
0x180083071  mov     rax, [rcx]
0x180083074  mov     rdx, [rsi+160h]
0x18008307b  mov     rax, [rax+80h]
0x180083082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083087  mov     rcx, [rsp+1C0h+var_190]
0x18008308c  mov     rax, [rcx]
0x18008308f  mov     rdx, [rsi+168h]
0x180083096  mov     rax, [rax+90h]
0x18008309d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800830a2  nop
0x1800830a3  lea     rcx, [rsp+1C0h+var_190]
0x1800830a8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800830ad  mov     [rsp+1C0h+var_188], r14
0x1800830b2  lea     rdx, [rsp+1C0h+var_188]
0x1800830b7  lea     rcx, [rsp+1C0h+var_198]
0x1800830bc  call    ??$As@UIInternalCoreWindow5@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow5@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow5>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow5>>)
0x1800830c1  mov     edi, eax
0x1800830c3  test    eax, eax
0x1800830c5  js      short loc_1800830DC
0x1800830c7  mov     rcx, [rsp+1C0h+var_188]
0x1800830cc  mov     rax, [rcx]
0x1800830cf  xor     edx, edx
0x1800830d1  mov     rax, [rax+38h]
0x1800830d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800830da  mov     edi, eax
0x1800830dc  mov     [rbx], r14
0x1800830df  mov     [rsi+160h], r14
0x1800830e6  mov     [rsi+168h], r14
0x1800830ed  lea     rcx, [rsp+1C0h+var_188]
0x1800830f2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800830f7  nop
0x1800830f8  lea     rcx, [rsp+1C0h+SRWLock]
0x1800830fd  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180083102  jmp     short loc_18008312D
0x180083104  mov     ebx, [rsi+68h]
0x180083107  call    cs:__imp_GetCurrentThreadId
0x18008310d  cmp     ebx, eax
0x18008310f  jz      short loc_18008312D
0x180083111  mov     rcx, [rbp+0C8h]; this
0x180083118  mov     edi, 8000FFFFh
0x18008311d  mov     r9d, edi; char *
0x180083120  mov     r8, r15; unsigned int
0x180083123  mov     edx, 3CDh; void *
0x180083128  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008312d  lea     rdx, [rsi+1F8h]
0x180083134  lea     rcx, [rsp+1C0h+SRWLock]
0x180083139  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18008313e  lea     rcx, [rsi+198h]
0x180083145  cmp     [rcx], r14
0x180083148  jz      short loc_180083151
0x18008314a  xor     edx, edx
0x18008314c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180083151  lea     rcx, [rsi+1A8h]
0x180083158  cmp     [rcx], r14
0x18008315b  jz      short loc_180083164
0x18008315d  xor     edx, edx
0x18008315f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180083164  mov     rcx, [rsp+1C0h+SRWLock]; SRWLock
0x180083169  test    rcx, rcx
0x18008316c  jz      short loc_180083174
0x18008316e  call    cs:__imp_ReleaseSRWLockExclusive
0x180083174  test    edi, edi
0x180083176  jns     short loc_180083191
0x180083178  mov     rcx, [rbp+0C8h]; this
0x18008317f  mov     r9d, edi; char *
0x180083182  mov     r8, r15; unsigned int
0x180083185  mov     edx, 3DEh; void *
0x18008318a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008318f  jmp     short loc_18008319E
0x180083191  lea     rcx, [rsp+1C0h+var_180]
0x180083196  call    ?Stop@?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18008319b  mov     edi, r14d
0x18008319e  lea     rcx, [rsp+1C0h+var_198]
0x1800831a3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800831a8  nop
0x1800831a9  lea     rcx, [rsp+1C0h+var_180]; this
0x1800831ae  call    ??1CoreWindowSiteDisconnect@CUITelemetry@@QEAA@XZ; CUITelemetry::CoreWindowSiteDisconnect::~CoreWindowSiteDisconnect(void)
0x1800831b3  mov     eax, edi
0x1800831b5  mov     rcx, [rbp+0C0h+var_30]
0x1800831bc  xor     rcx, rsp; StackCookie
0x1800831bf  call    __security_check_cookie
0x1800831c4  mov     rbx, [rsp+1C0h+arg_10]
0x1800831cc  add     rsp, 1A0h
0x1800831d3  pop     r15
0x1800831d5  pop     r14
0x1800831d7  pop     rdi
0x1800831d8  pop     rsi
0x1800831d9  pop     rbp
0x1800831da  retn
```
