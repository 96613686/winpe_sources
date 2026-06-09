# Windows::UI::Core::CCoreWindowSite::InvokeNavigationFocusEventHandlers(Windows::UI::Core::INavigationFocusEventArgs *)

- ea: `0x18004e9a0`
- end: `0x18004ecc1`
- name: `?InvokeNavigationFocusEventHandlers@CCoreWindowSite@Core@UI@Windows@@UEAAJPEAUINavigationFocusEventArgs@234@@Z`
- size: `801`
- prototype: `__int64 __fastcall(Windows::UI::Core::CCoreWindowSite *__hidden this, struct Windows::UI::Core::INavigationFocusEventArgs *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x1800053d0`
- `0x18000f048`
- `0x180014754`
- `0x180017a90`
- `0x18002b770`
- `0x180044a44`
- `0x18004e5cc`
- `0x18004e9a0`
- `0x18004ed78`
- `0x1800543b4`
- `0x18007fc30`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ea24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ea69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ea24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ea69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ec19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ec19`

## string_xrefs

- `0x18004eab2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x18004eafd`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::InvokeNavigationFocusEventHandlers(
        Windows::UI::Core::CCoreWindowSite *this,
        struct Windows::UI::Core::INavigationFocusEventArgs *a2)
{
  char *v4; // rdi
  __int64 v5; // rbx
  int v6; // ebx
  __int64 v7; // rsi
  bool v8; // bl
  PSRWLOCK v9; // rbx
  __int64 (__fastcall *v10)(PSRWLOCK, GUID *, _QWORD *); // rdi
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  __int64 v15; // r8
  int v16; // edi
  int v17; // eax
  int v19; // [rsp+20h] [rbp-89h] BYREF
  PSRWLOCK v20; // [rsp+28h] [rbp-81h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-79h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-69h] BYREF
  char *v23; // [rsp+50h] [rbp-59h] BYREF
  __int128 v24; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v25[80]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v26; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  CUITelemetry::WatchCurrentThread(v25, "CoreWindowSite::InvokeNavigationFocusEventHandler");
  if ( !a2 )
    goto LABEL_31;
  v4 = (char *)this + 232;
  if ( !*((_QWORD *)this + 29) )
    goto LABEL_31;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 240);
  if ( *(_QWORD *)v4 )
    v5 = (__int64)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) - *(_QWORD *)(*(_QWORD *)v4 + 16LL)) >> 3;
  else
    v5 = 0;
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( !v5 )
    goto LABEL_31;
  *(_QWORD *)&v24 = a2;
  v23 = (char *)this - 40;
  v6 = 0;
  v22[0] = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v20, (char *)this + 240);
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(v22, (char *)this + 232);
  if ( v20 )
    ReleaseSRWLockExclusive(v20);
  v7 = v22[0];
  if ( v22[0] )
  {
    v22[0] = &v23;
    v22[1] = &v24;
    v6 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_20f494fe0baa1532db1c50100a579e9f_,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
           v22,
           v7,
           (char *)this + 232);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v7);
  }
  if ( v6 >= 0 )
  {
    LOBYTE(v19) = 0;
    (*(void (__fastcall **)(struct Windows::UI::Core::INavigationFocusEventArgs *, int *))(*(_QWORD *)a2 + 64LL))(
      a2,
      &v19);
    v26 = 0;
    (*(void (__fastcall **)(struct Windows::UI::Core::INavigationFocusEventArgs *, __int128 *))(*(_QWORD *)a2 + 80LL))(
      a2,
      &v26);
    v8 = 0;
    if ( (_BYTE)v19 )
    {
      v20 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
      if ( (unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread((struct Windows::UI::Core::ICoreWindow **)&v20) )
      {
        v22[0] = 0;
        v9 = v20;
        v10 = *(__int64 (__fastcall **)(PSRWLOCK, GUID *, _QWORD *))v20->Ptr;
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v22);
        v11 = v10(v9, &GUID_5f882a05_d594_48bc_9a5a_fd3b9ce90390, v22);
        v6 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5CC,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
            (const char *)(unsigned int)v11,
            v19);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v22);
LABEL_19:
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
          goto LABEL_32;
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v22[0] + 72LL))(v22[0]);
        v13 = v12;
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5CE,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
            (const char *)(unsigned int)v12,
            v19);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v22);
        v8 = v13 >= 0;
      }
      else if ( *((_DWORD *)this + 16) != GetCurrentThreadId() )
      {
        v6 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D9,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
          (const char *)0x8000FFFFLL,
          v19);
        goto LABEL_19;
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
    }
    SRWLock[0] = 0;
    v14 = Microsoft::WRL::ComPtr<Windows::UI::Core::ITextInputProducerSite>::As<ITextInputProducerSiteInternal>(
            (char *)this + 160,
            SRWLock);
    v16 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DF,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v14,
        v19);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(SRWLock);
      v6 = v16;
      goto LABEL_32;
    }
    v24 = v26;
    LOBYTE(v15) = v8;
    v17 = (*((__int64 (__fastcall **)(PSRWLOCK, __int128 *, __int64))SRWLock[0]->Ptr + 7))(SRWLock[0], &v24, v15);
    v6 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E0,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v17,
        v19);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(SRWLock);
      goto LABEL_32;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(SRWLock);
LABEL_31:
    v6 = 0;
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5BD,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
    (const char *)(unsigned int)v6,
    v19);
LABEL_32:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004e9a0  mov     [rsp-8+arg_10], rbx
0x18004e9a5  push    rbp
0x18004e9a6  push    rsi
0x18004e9a7  push    rdi
0x18004e9a8  push    r14
0x18004e9aa  push    r15
0x18004e9ac  lea     rbp, [rsp-37h]
0x18004e9b1  sub     rsp, 0E0h
0x18004e9b8  mov     rax, cs:__security_cookie
0x18004e9bf  xor     rax, rsp
0x18004e9c2  mov     [rbp+57h+var_30], rax
0x18004e9c6  mov     r15, rdx
0x18004e9c9  mov     r14, rcx
0x18004e9cc  lea     rdx, aCorewindowsite_37; "CoreWindowSite::InvokeNavigationFocusEv"...
0x18004e9d3  lea     rcx, [rbp+57h+var_90]
0x18004e9d7  call    ?WatchCurrentThread@CUITelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CUITelemetry::WatchCurrentThread(char const *)
0x18004e9dc  test    r15, r15
0x18004e9df  jz      loc_18004EC91
0x18004e9e5  lea     rdi, [r14+0E8h]
0x18004e9ec  cmp     qword ptr [rdi], 0
0x18004e9f0  jz      loc_18004EC91
0x18004e9f6  lea     rdx, [rdi+8]
0x18004e9fa  lea     rcx, [rbp+57h+SRWLock]
0x18004e9fe  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18004ea03  mov     rax, [rdi]
0x18004ea06  test    rax, rax
0x18004ea09  jnz     short loc_18004EA0F
0x18004ea0b  xor     ebx, ebx
0x18004ea0d  jmp     short loc_18004EA1B
0x18004ea0f  mov     rbx, [rax+18h]
0x18004ea13  sub     rbx, [rax+10h]
0x18004ea17  sar     rbx, 3
0x18004ea1b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004ea1f  test    rcx, rcx
0x18004ea22  jz      short loc_18004EA2A
0x18004ea24  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ea2a  test    rbx, rbx
0x18004ea2d  jz      loc_18004EC91
0x18004ea33  mov     qword ptr [rbp+57h+var_A0], r15
0x18004ea37  lea     rax, [r14-28h]
0x18004ea3b  mov     [rbp+57h+var_B0], rax
0x18004ea3f  xor     ebx, ebx
0x18004ea41  mov     [rbp+57h+var_C0], rbx
0x18004ea45  lea     rdx, [rdi+8]
0x18004ea49  lea     rcx, [rsp+100h+var_D8]
0x18004ea4e  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18004ea53  mov     rdx, rdi
0x18004ea56  lea     rcx, [rbp+57h+var_C0]
0x18004ea5a  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x18004ea5f  mov     rcx, [rsp+100h+var_D8]; SRWLock
0x18004ea64  test    rcx, rcx
0x18004ea67  jz      short loc_18004EA6F
0x18004ea69  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ea6f  mov     rsi, [rbp+57h+var_C0]
0x18004ea73  test    rsi, rsi
0x18004ea76  jz      short loc_18004EAA7
0x18004ea78  lea     rax, [rbp+57h+var_B0]
0x18004ea7c  mov     [rbp+57h+var_C0], rax
0x18004ea80  lea     rax, [rbp+57h+var_A0]
0x18004ea84  mov     [rbp+57h+var_B8], rax
0x18004ea88  mov     r8, rdi
0x18004ea8b  mov     rdx, rsi
0x18004ea8e  lea     rcx, [rbp+57h+var_C0]
0x18004ea92  call    ??$InvokeDelegates@V_lambda_20f494fe0baa1532db1c50100a579e9f_@@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowOcclusionChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_20f494fe0baa1532db1c50100a579e9f_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowOcclusionChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_20f494fe0baa1532db1c50100a579e9f_,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_20f494fe0baa1532db1c50100a579e9f_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18004ea97  mov     ebx, eax
0x18004ea99  test    rsi, rsi
0x18004ea9c  jz      short loc_18004EAA7
0x18004ea9e  mov     rcx, rsi
0x18004eaa1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18004eaa6  nop
0x18004eaa7  test    ebx, ebx
0x18004eaa9  jns     short loc_18004EAC8
0x18004eaab  mov     rcx, [rbp+5Fh]; this
0x18004eaaf  mov     r9d, ebx; char *
0x18004eab2  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004eab9  mov     edx, 5BDh; void *
0x18004eabe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eac3  jmp     loc_18004EC93
0x18004eac8  mov     byte ptr [rsp+100h+var_E0], 0; int
0x18004eacd  mov     rax, [r15]
0x18004ead0  lea     rdx, [rsp+100h+var_E0]
0x18004ead5  mov     rcx, r15
0x18004ead8  mov     rax, [rax+40h]
0x18004eadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eae1  xorps   xmm0, xmm0
0x18004eae4  movups  [rbp+57h+var_40], xmm0
0x18004eae8  mov     rax, [r15]
0x18004eaeb  lea     rdx, [rbp+57h+var_40]
0x18004eaef  mov     rcx, r15
0x18004eaf2  mov     rax, [rax+50h]
0x18004eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eafb  xor     bl, bl
0x18004eafd  lea     rsi, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004eb04  cmp     byte ptr [rsp+100h+var_E0], bl
0x18004eb08  jz      loc_18004EBDA
0x18004eb0e  mov     [rsp+100h+var_D8], 0
0x18004eb17  lea     rcx, [rsp+100h+var_D8]
0x18004eb1c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004eb21  lea     rcx, [rsp+100h+var_D8]; struct Windows::UI::Core::ICoreWindow **
0x18004eb26  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x18004eb2b  test    eax, eax
0x18004eb2d  jz      loc_18004EC19
0x18004eb33  mov     [rbp+57h+var_C0], 0
0x18004eb3b  mov     rbx, [rsp+100h+var_D8]
0x18004eb40  mov     rax, [rbx]
0x18004eb43  mov     rdi, [rax]
0x18004eb46  lea     rcx, [rbp+57h+var_C0]
0x18004eb4a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004eb4f  lea     r8, [rbp+57h+var_C0]
0x18004eb53  lea     rdx, _GUID_5f882a05_d594_48bc_9a5a_fd3b9ce90390
0x18004eb5a  mov     rcx, rbx
0x18004eb5d  mov     rax, rdi
0x18004eb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb65  mov     ebx, eax
0x18004eb67  test    eax, eax
0x18004eb69  jns     short loc_18004EB97
0x18004eb6b  mov     rcx, [rbp+5Fh]; this
0x18004eb6f  mov     r9d, eax; char *
0x18004eb72  mov     r8, rsi; unsigned int
0x18004eb75  mov     edx, 5CCh; void *
0x18004eb7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb7f  lea     rcx, [rbp+57h+var_C0]
0x18004eb83  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004eb88  lea     rcx, [rsp+100h+var_D8]
0x18004eb8d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004eb92  jmp     loc_18004EC93
0x18004eb97  mov     rcx, [rbp+57h+var_C0]
0x18004eb9b  mov     rax, [rcx]
0x18004eb9e  mov     rax, [rax+48h]
0x18004eba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eba7  mov     ebx, eax
0x18004eba9  test    eax, eax
0x18004ebab  jns     short loc_18004EBC1
0x18004ebad  mov     rcx, [rbp+5Fh]; this
0x18004ebb1  mov     r9d, eax; char *
0x18004ebb4  mov     r8, rsi; unsigned int
0x18004ebb7  mov     edx, 5CEh; void *
0x18004ebbc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ebc1  lea     rcx, [rbp+57h+var_C0]
0x18004ebc5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004ebca  shr     ebx, 1Fh
0x18004ebcd  xor     bl, 1
0x18004ebd0  lea     rcx, [rsp+100h+var_D8]
0x18004ebd5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004ebda  mov     [rbp+57h+SRWLock], 0
0x18004ebe2  lea     rcx, [r14+0A0h]
0x18004ebe9  lea     rdx, [rbp+57h+SRWLock]
0x18004ebed  call    ??$As@UITextInputProducerSiteInternal@@@?$ComPtr@UITextInputProducerSite@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UITextInputProducerSiteInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ITextInputProducerSite>::As<ITextInputProducerSiteInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITextInputProducerSiteInternal>>)
0x18004ebf2  mov     edi, eax
0x18004ebf4  test    eax, eax
0x18004ebf6  jns     short loc_18004EC43
0x18004ebf8  mov     rcx, [rbp+5Fh]; this
0x18004ebfc  mov     r9d, eax; char *
0x18004ebff  mov     r8, rsi; unsigned int
0x18004ec02  mov     edx, 5DFh; void *
0x18004ec07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec0c  lea     rcx, [rbp+57h+SRWLock]
0x18004ec10  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004ec15  mov     ebx, edi
0x18004ec17  jmp     short loc_18004EC93
0x18004ec19  call    cs:__imp_GetCurrentThreadId
0x18004ec1f  cmp     [r14+40h], eax
0x18004ec23  jz      short loc_18004EBD0
0x18004ec25  mov     rcx, [rbp+5Fh]; this
0x18004ec29  mov     ebx, 8000FFFFh
0x18004ec2e  mov     r9d, ebx; char *
0x18004ec31  mov     r8, rsi; unsigned int
0x18004ec34  mov     edx, 5D9h; void *
0x18004ec39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec3e  jmp     loc_18004EB88
0x18004ec43  mov     rcx, [rbp+57h+SRWLock]
0x18004ec47  movaps  xmm0, [rbp+57h+var_40]
0x18004ec4b  movdqa  [rbp+57h+var_A0], xmm0
0x18004ec50  mov     rax, [rcx]
0x18004ec53  mov     r8b, bl
0x18004ec56  lea     rdx, [rbp+57h+var_A0]
0x18004ec5a  mov     rax, [rax+38h]
0x18004ec5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec63  mov     ebx, eax
0x18004ec65  test    eax, eax
0x18004ec67  jns     short loc_18004EC88
0x18004ec69  mov     rcx, [rbp+5Fh]; this
0x18004ec6d  mov     r9d, eax; char *
0x18004ec70  mov     r8, rsi; unsigned int
0x18004ec73  mov     edx, 5E0h; void *
0x18004ec78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec7d  lea     rcx, [rbp+57h+SRWLock]
0x18004ec81  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004ec86  jmp     short loc_18004EC93
0x18004ec88  lea     rcx, [rbp+57h+SRWLock]
0x18004ec8c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004ec91  xor     ebx, ebx
0x18004ec93  lea     rcx, [rbp+57h+var_90]; this
0x18004ec97  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18004ec9c  mov     eax, ebx
0x18004ec9e  mov     rcx, [rbp+57h+var_30]
0x18004eca2  xor     rcx, rsp; StackCookie
0x18004eca5  call    __security_check_cookie
0x18004ecaa  mov     rbx, [rsp+100h+arg_10]
0x18004ecb2  add     rsp, 0E0h
0x18004ecb9  pop     r15
0x18004ecbb  pop     r14
0x18004ecbd  pop     rdi
0x18004ecbe  pop     rsi
0x18004ecbf  pop     rbp
0x18004ecc0  retn
```
