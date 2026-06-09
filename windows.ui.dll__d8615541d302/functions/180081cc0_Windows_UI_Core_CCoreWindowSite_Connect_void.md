# Windows::UI::Core::CCoreWindowSite::Connect(void)

- ea: `0x180081cc0`
- end: `0x180082453`
- name: `?Connect@CCoreWindowSite@Core@UI@Windows@@UEAAJXZ`
- size: `1939`
- prototype: `__int64 __fastcall(Windows::UI::Core::CCoreWindowSite *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x18000f048`
- `0x180014754`
- `0x180014e44`
- `0x18002b770`
- `0x18004afd8`
- `0x18005bb78`
- `0x18007faf0`
- `0x18007fb40`
- `0x18007fb90`
- `0x18007fdb8`
- `0x18007ff5c`
- `0x180080bd4`
- `0x1800812d0`
- `0x180081cc0`
- `0x180082eb0`
- `0x1800856a4`
- `0x1800877dc`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081d41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081dd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082417`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081d41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081dd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800823b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800823b4`

## string_xrefs

- `0x180081d6e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180081e0d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180081e76`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180081f29`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180081f85`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x18008203f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800820fc`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180082162`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800821d1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180082258`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800822e1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180082386`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800823cf`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::Connect(Windows::UI::Core::CCoreWindowSite *this)
{
  int ComponentViewInstanceId; // eax
  int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, char *); // rbx
  _QWORD *v9; // rax
  char *v10; // rcx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, char *); // rbx
  _QWORD *v14; // rax
  char *v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, char *); // rbx
  _QWORD *v18; // rax
  char *v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  struct Windows::UI::Core::ICoreWindow *v23; // rdi
  __int64 (__fastcall *v24)(struct Windows::UI::Core::ICoreWindow *, _QWORD *); // rbx
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  unsigned int v30; // [rsp+20h] [rbp-E0h] BYREF
  struct Windows::UI::Core::ICoreWindow *v31; // [rsp+28h] [rbp-D8h] BYREF
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  char *v35; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall *v37)(Windows::UI::Core::CCoreWindowSite *__hidden, struct Windows::UI::Core::ICoreWindow *, struct IInspectable *); // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  _QWORD v39[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v40[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &CUITelemetry::CoreWindowSiteConnect::`vftable';
  CUITelemetry::CoreWindowSiteConnect::StartActivity((CUITelemetry::CoreWindowSiteConnect *)v40, *((_BYTE *)this + 81));
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 128);
  if ( *((_BYTE *)this + 81) )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
LABEL_48:
    v3 = 0;
    goto LABEL_49;
  }
  v30 = 0;
  ComponentViewInstanceId = Windows::UI::Core::CCoreWindowSite::get_ComponentViewInstanceId(
                              (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
                              &v30);
  v3 = ComponentViewInstanceId;
  if ( ComponentViewInstanceId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)ComponentViewInstanceId,
      v30);
    goto LABEL_6;
  }
  CUITelemetry::CoreWindowSiteConnect::CoreWindowSiteConnectComponent<unsigned int &>(v40, &v30);
  v4 = *((_QWORD *)this + 23);
  if ( !v4 )
    goto LABEL_15;
  if ( v30 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(
           v4,
           ((unsigned __int64)this + 24) & ((unsigned __int128)-(__int128)((unsigned __int64)this - 16) >> 64));
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v5,
        v30);
      Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
        (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
        v30);
      goto LABEL_6;
    }
LABEL_15:
    v31 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
    if ( (unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread(&v31) )
    {
      v33 = 0;
      v6 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow2>(
             &v31,
             &v33);
      v3 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26B,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v6,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v7 = v33;
      v8 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v33 + 152LL);
      v37 = Windows::UI::Core::CCoreWindowSite::OnWindowMoved;
      v38 = 0;
      v9 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Windows::UI::Core::CCoreWindowSite,Windows::UI::Core::ICoreWindow *,IInspectable *>(
                       &v35,
                       (char *)this - 16,
                       &v37);
      v3 = v8(v7, *v9, (char *)this + 328);
      v10 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26D,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v3,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v34 = 0;
      v11 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow4>(
              &v31,
              &v34);
      v3 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26F,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v11,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v12 = v34;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v34 + 120LL);
      v37 = Windows::UI::Core::CCoreWindowSite::OnHostMoveSizeStarted;
      v38 = 0;
      v14 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Windows::UI::Core::CCoreWindowSite,Windows::UI::Core::ICoreWindow *,IInspectable *>(
                        &v35,
                        (char *)this - 16,
                        &v37);
      v3 = v13(v12, *v14, (char *)this + 336);
      v15 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x271,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v3,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v16 = v34;
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v34 + 136LL);
      v37 = Windows::UI::Core::CCoreWindowSite::OnHostMoveSizeCompleted;
      v38 = 0;
      v18 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Windows::UI::Core::CCoreWindowSite,Windows::UI::Core::ICoreWindow *,IInspectable *>(
                        &v35,
                        (char *)this - 16,
                        &v37);
      v3 = v17(v16, *v18, (char *)this + 344);
      v19 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x273,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v3,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v36[0] = 0;
      v20 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow5>(
              &v31,
              v36);
      v3 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x275,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v20,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v36);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      LOBYTE(v21) = 1;
      v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v36[0] + 56LL))(v36[0], v21);
      v3 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x276,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v22,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v36);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v39[0] = 0;
      v23 = v31;
      v24 = *(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreWindow *, _QWORD *))(*(_QWORD *)v31 + 72LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v39);
      v25 = v24(v23, v39);
      v3 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x279,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v25,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v39);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v36);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      v35 = (char *)this + 152;
      v26 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v35);
      v27 = Microsoft::WRL::AsWeak<Windows::Foundation::Private::IComponentSite>(v39[0], v26);
      v3 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27A,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)(unsigned int)v27,
          v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v39);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v36);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
        Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
          (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
          v30);
        goto LABEL_6;
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v39);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v36);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
    }
    else if ( *((_DWORD *)this + 22) != GetCurrentThreadId() )
    {
      v3 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x284,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)0x8000FFFFLL,
        v30);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
      Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
        (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
        v30);
LABEL_6:
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      goto LABEL_49;
    }
    v28 = (*(__int64 (__fastcall **)(Windows::UI::Core::CCoreWindowSite *, _QWORD))(*(_QWORD *)this + 80LL))(this, v30);
    v3 = v28;
    if ( v28 >= 0 )
    {
      *((_BYTE *)this + 81) = 1;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v40);
      goto LABEL_48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v28,
      v30);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
    Windows::UI::Core::CCoreWindowSite::DisconnectInternal(
      (Windows::UI::Core::CCoreWindowSite *)((char *)this - 16),
      v30);
    goto LABEL_6;
  }
  Windows::UI::Core::CCoreWindowSite::DisconnectInternal((Windows::UI::Core::CCoreWindowSite *)((char *)this - 16), 0);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = -2147467259;
LABEL_49:
  CUITelemetry::CoreWindowSiteConnect::~CoreWindowSiteConnect((CUITelemetry::CoreWindowSiteConnect *)v40);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180081cc0  push    rbp
0x180081cc2  push    rbx
0x180081cc3  push    rsi
0x180081cc4  push    rdi
0x180081cc5  push    r14
0x180081cc7  push    r15
0x180081cc9  lea     rbp, [rsp-0E8h]
0x180081cd1  sub     rsp, 1E8h
0x180081cd8  mov     rax, cs:__security_cookie
0x180081cdf  xor     rax, rsp
0x180081ce2  mov     [rbp+110h+var_40], rax
0x180081ce9  mov     r14, rcx
0x180081cec  lea     rdx, aCorewindowsite_24; "CoreWindowSiteConnect"
0x180081cf3  lea     rcx, [rbp+110h+var_190]; struct wil::details::IFailureCallback *
0x180081cf7  call    ??0?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180081cfc  lea     rax, ??_7CoreWindowSiteConnect@CUITelemetry@@6B@; const CUITelemetry::CoreWindowSiteConnect::`vftable'
0x180081d03  mov     [rbp+110h+var_190], rax
0x180081d07  mov     dl, [r14+51h]; bool
0x180081d0b  lea     rcx, [rbp+110h+var_190]; this
0x180081d0f  call    ?StartActivity@CoreWindowSiteConnect@CUITelemetry@@QEAAX_N@Z; CUITelemetry::CoreWindowSiteConnect::StartActivity(bool)
0x180081d14  nop
0x180081d15  lea     rsi, [r14-10h]
0x180081d19  lea     rdx, [r14+80h]
0x180081d20  lea     rcx, [rsp+210h+SRWLock]
0x180081d25  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180081d2a  xor     r15d, r15d
0x180081d2d  cmp     [rsi+61h], r15b
0x180081d31  jz      short loc_180081D4C
0x180081d33  mov     rcx, [rsp+210h+SRWLock]; SRWLock
0x180081d38  test    rcx, rcx
0x180081d3b  jz      loc_180082426
0x180081d41  call    cs:__imp_ReleaseSRWLockExclusive
0x180081d47  jmp     loc_180082426
0x180081d4c  mov     [rsp+210h+var_1F0], r15d; int
0x180081d51  lea     rdx, [rsp+210h+var_1F0]; unsigned int *
0x180081d56  mov     rcx, rsi; this
0x180081d59  call    ?get_ComponentViewInstanceId@CCoreWindowSite@Core@UI@Windows@@AEAAJPEAI@Z; Windows::UI::Core::CCoreWindowSite::get_ComponentViewInstanceId(uint *)
0x180081d5e  mov     ebx, eax
0x180081d60  test    eax, eax
0x180081d62  jns     short loc_180081D98
0x180081d64  mov     rcx, [rbp+118h]; this
0x180081d6b  mov     r9d, eax; char *
0x180081d6e  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180081d75  mov     edx, 1F2h; void *
0x180081d7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081d7f  mov     rcx, [rsp+210h+SRWLock]; SRWLock
0x180081d84  test    rcx, rcx
0x180081d87  jz      loc_180082429
0x180081d8d  call    cs:__imp_ReleaseSRWLockExclusive
0x180081d93  jmp     loc_180082429
0x180081d98  lea     rdx, [rsp+210h+var_1F0]
0x180081d9d  lea     rcx, [rbp+110h+var_190]
0x180081da1  call    ??$CoreWindowSiteConnectComponent@AEAI@CoreWindowSiteConnect@CUITelemetry@@QEAAXAEAI@Z; CUITelemetry::CoreWindowSiteConnect::CoreWindowSiteConnectComponent<uint &>(uint &)
0x180081da6  mov     rcx, [r14+0B8h]
0x180081dad  test    rcx, rcx
0x180081db0  jz      short loc_180081E31
0x180081db2  mov     r8d, [rsp+210h+var_1F0]
0x180081db7  test    r8d, r8d
0x180081dba  jnz     short loc_180081DE1
0x180081dbc  xor     edx, edx; unsigned int
0x180081dbe  mov     rcx, rsi; this
0x180081dc1  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x180081dc6  nop
0x180081dc7  mov     rcx, [rsp+210h+SRWLock]; SRWLock
0x180081dcc  test    rcx, rcx
0x180081dcf  jz      short loc_180081DD7
0x180081dd1  call    cs:__imp_ReleaseSRWLockExclusive
0x180081dd7  mov     ebx, 80004005h
0x180081ddc  jmp     loc_180082429
0x180081de1  mov     r10, [rcx]
0x180081de4  mov     rax, rsi
0x180081de7  lea     r9, [r14+18h]
0x180081deb  neg     rax
0x180081dee  sbb     rdx, rdx
0x180081df1  and     rdx, r9
0x180081df4  mov     rax, [r10+30h]
0x180081df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081dfd  mov     ebx, eax
0x180081dff  test    eax, eax
0x180081e01  jns     short loc_180081E31
0x180081e03  mov     rcx, [rbp+118h]; this
0x180081e0a  mov     r9d, eax; char *
0x180081e0d  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180081e14  mov     edx, 205h; void *
0x180081e19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081e1e  nop
0x180081e1f  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x180081e23  mov     rcx, rsi; this
0x180081e26  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x180081e2b  nop
0x180081e2c  jmp     loc_180081D7F
0x180081e31  mov     [rsp+210h+var_1E8], r15
0x180081e36  lea     rcx, [rsp+210h+var_1E8]
0x180081e3b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081e40  lea     rcx, [rsp+210h+var_1E8]; struct Windows::UI::Core::ICoreWindow **
0x180081e45  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x180081e4a  test    eax, eax
0x180081e4c  jz      loc_1800823B4
0x180081e52  mov     [rsp+210h+var_1D8], r15
0x180081e57  lea     rdx, [rsp+210h+var_1D8]
0x180081e5c  lea     rcx, [rsp+210h+var_1E8]
0x180081e61  call    ??$As@UIInternalCoreWindow2@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow2@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow2>>)
0x180081e66  mov     ebx, eax
0x180081e68  test    eax, eax
0x180081e6a  jns     short loc_180081EAE
0x180081e6c  mov     rcx, [rbp+118h]; this
0x180081e73  mov     r9d, eax; char *
0x180081e76  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180081e7d  mov     edx, 26Bh; void *
0x180081e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081e87  lea     rcx, [rsp+210h+var_1D8]
0x180081e8c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081e91  lea     rcx, [rsp+210h+var_1E8]
0x180081e96  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081e9b  nop
0x180081e9c  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x180081ea0  mov     rcx, rsi; this
0x180081ea3  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x180081ea8  nop
0x180081ea9  jmp     loc_180081D7F
0x180081eae  mov     rdi, [rsp+210h+var_1D8]
0x180081eb3  mov     rax, [rdi]
0x180081eb6  mov     rbx, [rax+98h]
0x180081ebd  lea     rax, ?OnWindowMoved@CCoreWindowSite@Core@UI@Windows@@IEAAJPEAUICoreWindow@234@PEAUIInspectable@@@Z; Windows::UI::Core::CCoreWindowSite::OnWindowMoved(Windows::UI::Core::ICoreWindow *,IInspectable *)
0x180081ec4  mov     [rsp+210h+var_1B0], rax
0x180081ec9  mov     [rsp+210h+var_1A8], r15d
0x180081ece  mov     edx, [rsp+210h+var_1A4]
0x180081ed2  mov     [rsp+210h+var_1A4], edx
0x180081ed6  lea     r8, [rsp+210h+var_1B0]
0x180081edb  mov     rdx, rsi
0x180081ede  lea     rcx, [rsp+210h+var_1C8]
0x180081ee3  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@VCCoreWindowSite@Core@UI@3@PEAUICoreWindow@563@PEAUIInspectable@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@@01@PEAVCCoreWindowSite@Core@UI@Windows@@P83456@EAAJPEAUICoreWindow@456@PEAUIInspectable@@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Windows::UI::Core::CCoreWindowSite,Windows::UI::Core::ICoreWindow *,IInspectable *>(Windows::UI::Core::CCoreWindowSite *,long (Windows::UI::Core::CCoreWindowSite::*)(Windows::UI::Core::ICoreWindow *,IInspectable *))
0x180081ee8  lea     r8, [r14+148h]
0x180081eef  mov     rdx, [rax]
0x180081ef2  mov     rcx, rdi
0x180081ef5  mov     rax, rbx
0x180081ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081efd  mov     ebx, eax
0x180081eff  mov     rcx, [rsp+210h+var_1C8]
0x180081f04  test    rcx, rcx
0x180081f07  jz      short loc_180081F1B
0x180081f09  mov     [rsp+210h+var_1C8], r15
0x180081f0e  mov     rax, [rcx]
0x180081f11  mov     rax, [rax+10h]
0x180081f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f1a  nop
0x180081f1b  test    ebx, ebx
0x180081f1d  jns     short loc_180081F61
0x180081f1f  mov     rcx, [rbp+118h]; this
0x180081f26  mov     r9d, ebx; char *
0x180081f29  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180081f30  mov     edx, 26Dh; void *
0x180081f35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081f3a  lea     rcx, [rsp+210h+var_1D8]
0x180081f3f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081f44  lea     rcx, [rsp+210h+var_1E8]
0x180081f49  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081f4e  nop
0x180081f4f  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x180081f53  mov     rcx, rsi; this
0x180081f56  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x180081f5b  nop
0x180081f5c  jmp     loc_180081D7F
0x180081f61  mov     [rsp+210h+var_1D0], r15
0x180081f66  lea     rdx, [rsp+210h+var_1D0]
0x180081f6b  lea     rcx, [rsp+210h+var_1E8]
0x180081f70  call    ??$As@UIInternalCoreWindow4@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow4@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow4>>)
0x180081f75  mov     ebx, eax
0x180081f77  test    eax, eax
0x180081f79  jns     short loc_180081FC7
0x180081f7b  mov     rcx, [rbp+118h]; this
0x180081f82  mov     r9d, eax; char *
0x180081f85  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180081f8c  mov     edx, 26Fh; void *
0x180081f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081f96  lea     rcx, [rsp+210h+var_1D0]
0x180081f9b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081fa0  lea     rcx, [rsp+210h+var_1D8]
0x180081fa5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081faa  lea     rcx, [rsp+210h+var_1E8]
0x180081faf  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180081fb4  nop
0x180081fb5  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x180081fb9  mov     rcx, rsi; this
0x180081fbc  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x180081fc1  nop
0x180081fc2  jmp     loc_180081D7F
0x180081fc7  mov     rdi, [rsp+210h+var_1D0]
0x180081fcc  mov     rax, [rdi]
0x180081fcf  mov     rbx, [rax+78h]
0x180081fd3  lea     rax, ?OnHostMoveSizeStarted@CCoreWindowSite@Core@UI@Windows@@IEAAJPEAUICoreWindow@234@PEAUIInspectable@@@Z; Windows::UI::Core::CCoreWindowSite::OnHostMoveSizeStarted(Windows::UI::Core::ICoreWindow *,IInspectable *)
0x180081fda  mov     [rsp+210h+var_1B0], rax
0x180081fdf  mov     [rsp+210h+var_1A8], r15d
0x180081fe4  mov     edx, [rsp+210h+var_1A4]
0x180081fe8  mov     [rsp+210h+var_1A4], edx
0x180081fec  lea     r8, [rsp+210h+var_1B0]
0x180081ff1  mov     rdx, rsi
0x180081ff4  lea     rcx, [rsp+210h+var_1C8]
0x180081ff9  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@VCCoreWindowSite@Core@UI@3@PEAUICoreWindow@563@PEAUIInspectable@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@@01@PEAVCCoreWindowSite@Core@UI@Windows@@P83456@EAAJPEAUICoreWindow@456@PEAUIInspectable@@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Windows::UI::Core::CCoreWindowSite,Windows::UI::Core::ICoreWindow *,IInspectable *>(Windows::UI::Core::CCoreWindowSite *,long (Windows::UI::Core::CCoreWindowSite::*)(Windows::UI::Core::ICoreWindow *,IInspectable *))
0x180081ffe  lea     r8, [r14+150h]
0x180082005  mov     rdx, [rax]
0x180082008  mov     rcx, rdi
0x18008200b  mov     rax, rbx
0x18008200e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082013  mov     ebx, eax
0x180082015  mov     rcx, [rsp+210h+var_1C8]
0x18008201a  test    rcx, rcx
0x18008201d  jz      short loc_180082031
0x18008201f  mov     [rsp+210h+var_1C8], r15
0x180082024  mov     rax, [rcx]
0x180082027  mov     rax, [rax+10h]
0x18008202b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082030  nop
0x180082031  test    ebx, ebx
0x180082033  jns     short loc_180082081
0x180082035  mov     rcx, [rbp+118h]; this
0x18008203c  mov     r9d, ebx; char *
0x18008203f  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180082046  mov     edx, 271h; void *
0x18008204b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082050  lea     rcx, [rsp+210h+var_1D0]
0x180082055  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008205a  lea     rcx, [rsp+210h+var_1D8]
0x18008205f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082064  lea     rcx, [rsp+210h+var_1E8]
0x180082069  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008206e  nop
0x18008206f  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x180082073  mov     rcx, rsi; this
0x180082076  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x18008207b  nop
0x18008207c  jmp     loc_180081D7F
0x180082081  mov     rdi, [rsp+210h+var_1D0]
0x180082086  mov     rax, [rdi]
0x180082089  mov     rbx, [rax+88h]
0x180082090  lea     rax, ?OnHostMoveSizeCompleted@CCoreWindowSite@Core@UI@Windows@@IEAAJPEAUICoreWindow@234@PEAUIInspectable@@@Z; Windows::UI::Core::CCoreWindowSite::OnHostMoveSizeCompleted(Windows::UI::Core::ICoreWindow *,IInspectable *)
0x180082097  mov     [rsp+210h+var_1B0], rax
0x18008209c  mov     [rsp+210h+var_1A8], r15d
0x1800820a1  mov     edx, [rsp+210h+var_1A4]
0x1800820a5  mov     [rsp+210h+var_1A4], edx
0x1800820a9  lea     r8, [rsp+210h+var_1B0]
0x1800820ae  mov     rdx, rsi
0x1800820b1  lea     rcx, [rsp+210h+var_1C8]
0x1800820b6  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@VCCoreWindowSite@Core@UI@3@PEAUICoreWindow@563@PEAUIInspectable@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@@01@PEAVCCoreWindowSite@Core@UI@Windows@@P83456@EAAJPEAUICoreWindow@456@PEAUIInspectable@@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Windows::UI::Core::CCoreWindowSite,Windows::UI::Core::ICoreWindow *,IInspectable *>(Windows::UI::Core::CCoreWindowSite *,long (Windows::UI::Core::CCoreWindowSite::*)(Windows::UI::Core::ICoreWindow *,IInspectable *))
0x1800820bb  lea     r8, [r14+158h]
0x1800820c2  mov     rdx, [rax]
0x1800820c5  mov     rcx, rdi
0x1800820c8  mov     rax, rbx
0x1800820cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800820d0  mov     ebx, eax
0x1800820d2  mov     rcx, [rsp+210h+var_1C8]
0x1800820d7  test    rcx, rcx
0x1800820da  jz      short loc_1800820EE
0x1800820dc  mov     [rsp+210h+var_1C8], r15
0x1800820e1  mov     rax, [rcx]
0x1800820e4  mov     rax, [rax+10h]
0x1800820e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800820ed  nop
0x1800820ee  test    ebx, ebx
0x1800820f0  jns     short loc_18008213E
0x1800820f2  mov     rcx, [rbp+118h]; this
0x1800820f9  mov     r9d, ebx; char *
0x1800820fc  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180082103  mov     edx, 273h; void *
0x180082108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008210d  lea     rcx, [rsp+210h+var_1D0]
0x180082112  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082117  lea     rcx, [rsp+210h+var_1D8]
0x18008211c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082121  lea     rcx, [rsp+210h+var_1E8]
0x180082126  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008212b  nop
0x18008212c  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x180082130  mov     rcx, rsi; this
0x180082133  call    ?DisconnectInternal@CCoreWindowSite@Core@UI@Windows@@AEAAJI@Z; Windows::UI::Core::CCoreWindowSite::DisconnectInternal(uint)
0x180082138  nop
0x180082139  jmp     loc_180081D7F
0x18008213e  mov     [rsp+210h+var_1C0], r15
0x180082143  lea     rdx, [rsp+210h+var_1C0]
0x180082148  lea     rcx, [rsp+210h+var_1E8]
0x18008214d  call    ??$As@UIInternalCoreWindow5@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow5@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow5>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow5>>)
0x180082152  mov     ebx, eax
0x180082154  test    eax, eax
0x180082156  jns     short loc_1800821AE
0x180082158  mov     rcx, [rbp+118h]; this
0x18008215f  mov     r9d, eax; char *
0x180082162  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180082169  mov     edx, 275h; void *
0x18008216e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082173  lea     rcx, [rsp+210h+var_1C0]
0x180082178  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008217d  lea     rcx, [rsp+210h+var_1D0]
0x180082182  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082187  lea     rcx, [rsp+210h+var_1D8]
0x18008218c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082191  lea     rcx, [rsp+210h+var_1E8]
0x180082196  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008219b  nop
0x18008219c  mov     edx, [rsp+210h+var_1F0]; unsigned int
0x1800821a0  mov     rcx, rsi; this
  ... truncated ...
```
