# Windows::UI::Core::CCoreWindowSite::InvokeViewEvent(uint,Windows::UI::Core::CuiViewEventType)

- ea: `0x18005b9e0`
- end: `0x18005bb6f`
- name: `?InvokeViewEvent@CCoreWindowSite@Core@UI@Windows@@UEAAJIW4CuiViewEventType@234@@Z`
- size: `399`
- prototype: `int __high(unsigned int, enum Windows::UI::Core::CuiViewEventType)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014754`
- `0x180026e3c`
- `0x180035f5c`
- `0x18005b9e0`
- `0x18005bb78`
- `0x18005bc48`
- `0x180080bd4`
- `0x180081bd4`
- `0x1800839ac`
- `0x1800847a0`
- `0x180085aa0`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005bb2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005bb2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005bb1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005bb1f`

## string_xrefs

- `0x18005bac2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::InvokeViewEvent(_QWORD *a1, unsigned int a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct _TP_WAIT *v9; // rcx
  void *v10; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v13[42]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v13);
  v13[0] = &CUITelemetry::InvokeViewEvent::`vftable';
  CUITelemetry::InvokeViewEvent::StartActivity((CUITelemetry::InvokeViewEvent *)v13, a2);
  if ( a3 )
  {
    if ( a3 == 1 )
    {
      CUITelemetry::InvokeViewEvent::CloseEvent((CUITelemetry::InvokeViewEvent *)v13);
      v6 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(a1 + 55);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 1753;
        goto LABEL_9;
      }
    }
    else if ( a3 == 2 )
    {
      CUITelemetry::InvokeViewEvent::ModalDialogEvent((CUITelemetry::InvokeViewEvent *)v13);
      v6 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(a1 + 58);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 1761;
        goto LABEL_9;
      }
      Microsoft::WRL::Wrappers::SRWLock::LockShared(SRWLock, a1 + 61);
      v9 = (struct _TP_WAIT *)a1[51];
      if ( !v9 )
        goto LABEL_16;
      v10 = (void *)a1[48];
      goto LABEL_15;
    }
LABEL_18:
    wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v13);
    v7 = 0;
    goto LABEL_19;
  }
  CUITelemetry::InvokeViewEvent::ReadyEvent((CUITelemetry::InvokeViewEvent *)v13);
  v6 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(a1 + 52);
  v7 = v6;
  if ( v6 >= 0 )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockShared(SRWLock, a1 + 61);
    v9 = (struct _TP_WAIT *)a1[49];
    if ( !v9 )
      goto LABEL_16;
    v10 = (void *)a1[46];
LABEL_15:
    SetThreadpoolWait(v9, v10, 0);
LABEL_16:
    if ( SRWLock[0] )
      ReleaseSRWLockShared(SRWLock[0]);
    goto LABEL_18;
  }
  v8 = 1741;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
    (const char *)(unsigned int)v6,
    (int)SRWLock[0]);
LABEL_19:
  CUITelemetry::InvokeViewEvent::~InvokeViewEvent((CUITelemetry::InvokeViewEvent *)v13);
  return v7;
}

```

## disassembly

```asm
0x18005b9e0  mov     [rsp-8+arg_10], rbx
0x18005b9e5  push    rbp
0x18005b9e6  push    rsi
0x18005b9e7  push    rdi
0x18005b9e8  lea     rbp, [rsp-90h]
0x18005b9f0  sub     rsp, 190h
0x18005b9f7  mov     rax, cs:__security_cookie
0x18005b9fe  xor     rax, rsp
0x18005ba01  mov     [rbp+0A0h+var_20], rax
0x18005ba08  mov     esi, r8d
0x18005ba0b  mov     ebx, edx
0x18005ba0d  mov     rdi, rcx
0x18005ba10  lea     rdx, aInvokevieweven; "InvokeViewEvent"
0x18005ba17  lea     rcx, [rsp+1A0h+var_170]; struct wil::details::IFailureCallback *
0x18005ba1c  call    ??0?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005ba21  lea     rax, ??_7InvokeViewEvent@CUITelemetry@@6B@; const CUITelemetry::InvokeViewEvent::`vftable'
0x18005ba28  mov     [rsp+1A0h+var_170], rax
0x18005ba2d  mov     edx, ebx; unsigned int
0x18005ba2f  lea     rcx, [rsp+1A0h+var_170]; this
0x18005ba34  call    ?StartActivity@InvokeViewEvent@CUITelemetry@@QEAAXI@Z; CUITelemetry::InvokeViewEvent::StartActivity(uint)
0x18005ba39  nop
0x18005ba3a  test    esi, esi
0x18005ba3c  jnz     short loc_18005BA8E
0x18005ba3e  lea     rcx, [rsp+1A0h+var_170]; this
0x18005ba43  call    ?ReadyEvent@InvokeViewEvent@CUITelemetry@@QEAAXXZ; CUITelemetry::InvokeViewEvent::ReadyEvent(void)
0x18005ba48  lea     rcx, [rdi+1A0h]
0x18005ba4f  call    ??$InvokeAll@$$T$$T@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJ$$T0@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(std::nullptr_t,std::nullptr_t)
0x18005ba54  mov     ebx, eax
0x18005ba56  test    eax, eax
0x18005ba58  jns     short loc_18005BA61
0x18005ba5a  mov     edx, 6CDh
0x18005ba5f  jmp     short loc_18005BAB8
0x18005ba61  lea     rdx, [rdi+1E8h]
0x18005ba68  lea     rcx, [rsp+1A0h+SRWLock]
0x18005ba6d  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18005ba72  mov     rcx, [rdi+188h]
0x18005ba79  test    rcx, rcx
0x18005ba7c  jz      loc_18005BB25
0x18005ba82  mov     rdx, [rdi+170h]
0x18005ba89  jmp     loc_18005BB1C
0x18005ba8e  cmp     esi, 1
0x18005ba91  jnz     short loc_18005BAD0
0x18005ba93  lea     rcx, [rsp+1A0h+var_170]; this
0x18005ba98  call    ?CloseEvent@InvokeViewEvent@CUITelemetry@@QEAAXXZ; CUITelemetry::InvokeViewEvent::CloseEvent(void)
0x18005ba9d  lea     rcx, [rdi+1B8h]
0x18005baa4  call    ??$InvokeAll@$$T$$T@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJ$$T0@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(std::nullptr_t,std::nullptr_t)
0x18005baa9  mov     ebx, eax
0x18005baab  test    eax, eax
0x18005baad  jns     loc_18005BB35
0x18005bab3  mov     edx, 6D9h; void *
0x18005bab8  mov     rcx, [rbp+0A8h]; this
0x18005babf  mov     r9d, eax; char *
0x18005bac2  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005bac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bace  jmp     short loc_18005BB41
0x18005bad0  cmp     esi, 2
0x18005bad3  jnz     short loc_18005BB35
0x18005bad5  lea     rcx, [rsp+1A0h+var_170]; this
0x18005bada  call    ?ModalDialogEvent@InvokeViewEvent@CUITelemetry@@QEAAXXZ; CUITelemetry::InvokeViewEvent::ModalDialogEvent(void)
0x18005badf  lea     rcx, [rdi+1D0h]
0x18005bae6  call    ??$InvokeAll@$$T$$T@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJ$$T0@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(std::nullptr_t,std::nullptr_t)
0x18005baeb  mov     ebx, eax
0x18005baed  test    eax, eax
0x18005baef  jns     short loc_18005BAF8
0x18005baf1  mov     edx, 6E1h
0x18005baf6  jmp     short loc_18005BAB8
0x18005baf8  lea     rdx, [rdi+1E8h]
0x18005baff  lea     rcx, [rsp+1A0h+SRWLock]
0x18005bb04  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18005bb09  mov     rcx, [rdi+198h]; pwa
0x18005bb10  test    rcx, rcx
0x18005bb13  jz      short loc_18005BB25
0x18005bb15  mov     rdx, [rdi+180h]; h
0x18005bb1c  xor     r8d, r8d; pftTimeout
0x18005bb1f  call    cs:__imp_SetThreadpoolWait
0x18005bb25  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x18005bb2a  test    rcx, rcx
0x18005bb2d  jz      short loc_18005BB35
0x18005bb2f  call    cs:__imp_ReleaseSRWLockShared
0x18005bb35  lea     rcx, [rsp+1A0h+var_170]
0x18005bb3a  call    ?Stop@?$ActivityBase@VCUITelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CUITelemetry,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005bb3f  xor     ebx, ebx
0x18005bb41  lea     rcx, [rsp+1A0h+var_170]; this
0x18005bb46  call    ??1InvokeViewEvent@CUITelemetry@@QEAA@XZ; CUITelemetry::InvokeViewEvent::~InvokeViewEvent(void)
0x18005bb4b  mov     eax, ebx
0x18005bb4d  mov     rcx, [rbp+0A0h+var_20]
0x18005bb54  xor     rcx, rsp; StackCookie
0x18005bb57  call    __security_check_cookie
0x18005bb5c  mov     rbx, [rsp+1A0h+arg_10]
0x18005bb64  add     rsp, 190h
0x18005bb6b  pop     rdi
0x18005bb6c  pop     rsi
0x18005bb6d  pop     rbp
0x18005bb6e  retn
```
