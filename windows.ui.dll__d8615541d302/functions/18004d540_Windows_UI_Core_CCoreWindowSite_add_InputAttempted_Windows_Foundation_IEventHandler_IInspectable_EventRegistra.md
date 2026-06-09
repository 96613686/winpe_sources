# Windows::UI::Core::CCoreWindowSite::add_InputAttempted(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x18004d540`
- end: `0x18004d6cd`
- name: `?add_InputAttempted@CCoreWindowSite@Core@UI@Windows@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@4@PEAUEventRegistrationToken@@@Z`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180014cd8`
- `0x18002b770`
- `0x180044a44`
- `0x18004d540`
- `0x1800543b4`
- `0x1800813d8`
- `0x1800877dc`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d62a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d6a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d62a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d6a2`
- `ext-ms-win-mininput-inputhost-l1-2-1!CreateInputSystemClientConnection` at `0x18004d5fd`
- `ext-ms-win-mininput-inputhost-l1-2-1!CreateInputSystemClientConnection` at `0x18004d5fd`

## string_xrefs

- `0x18004d5b2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x18004d612`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x18004d560`: `CoreWindowSite::add_InputAttempted`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::add_InputAttempted(
        Windows::UI::Core::CCoreWindowSite *this,
        __int64 a2,
        __int64 a3)
{
  int v6; // ebx
  int InputSystemClientConnection; // esi
  __int64 v8; // rdx
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-29h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v14[80]; // [rsp+40h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  unsigned int v16; // [rsp+C8h] [rbp+7Fh] BYREF

  CUITelemetry::WatchCurrentThread(v14, "CoreWindowSite::add_InputAttempted");
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 536);
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_4;
  }
  v6 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::ICoreAccelerators *,Windows::UI::Core::AcceleratorKeyEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
         (char *)this + 512,
         a2,
         *(_QWORD *)(*(_QWORD *)a2 + 24LL),
         a3);
  if ( v6 < 0 )
  {
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D1,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v6,
      v11);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_19;
  }
  if ( !*((_QWORD *)this + 68) )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 544);
    InputSystemClientConnection = CreateInputSystemClientConnection(*((_QWORD *)this + 70), (char *)this + 544);
    if ( InputSystemClientConnection < 0 )
    {
      v8 = 1239;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)InputSystemClientConnection,
        v11);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v6 = InputSystemClientConnection;
      goto LABEL_19;
    }
  }
  if ( !*((_QWORD *)this + 69) )
  {
    v16 = 0;
    InputSystemClientConnection = Windows::UI::Core::CCoreWindowSite::get_ComponentViewInstanceId(this, &v16);
    if ( InputSystemClientConnection < 0 )
    {
      v8 = 1248;
      goto LABEL_9;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, unsigned __int64))(**((_QWORD **)this + 68) + 24LL))(
           *((_QWORD *)this + 68),
           v13,
           v16,
           ((unsigned __int64)this + 88) & -(__int64)(this != 0));
    Microsoft::WRL::ComPtr<IInputAttemptedDeliveryClient>::operator=((char *)this + 552, v9);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v13);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v6 = 0;
LABEL_19:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004d540  mov     [rsp-8+arg_0], rbx
0x18004d545  mov     [rsp-8+arg_8], rsi
0x18004d54a  push    rbp
0x18004d54b  push    rdi
0x18004d54c  push    r14
0x18004d54e  lea     rbp, [rsp-47h]
0x18004d553  sub     rsp, 90h
0x18004d55a  mov     rbx, rdx
0x18004d55d  mov     rdi, rcx
0x18004d560  lea     rdx, aCorewindowsite; "CoreWindowSite::add_InputAttempted"
0x18004d567  mov     rsi, r8
0x18004d56a  lea     rcx, [rbp+57h+var_60]
0x18004d56e  call    ?WatchCurrentThread@CUITelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CUITelemetry::WatchCurrentThread(char const *)
0x18004d573  lea     rdx, [rdi+218h]
0x18004d57a  lea     rcx, [rbp+57h+SRWLock]
0x18004d57e  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18004d583  test    rbx, rbx
0x18004d586  jnz     short loc_18004D58F
0x18004d588  mov     ebx, 80070057h
0x18004d58d  jmp     short loc_18004D5AE
0x18004d58f  mov     r8, [rbx]
0x18004d592  lea     rcx, [rdi+200h]
0x18004d599  mov     r9, rsi
0x18004d59c  mov     rdx, rbx
0x18004d59f  mov     r8, [r8+18h]
0x18004d5a3  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAUICoreAccelerators@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAUICoreAccelerators@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::ICoreAccelerators *,Windows::UI::Core::AcceleratorKeyEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::UI::Core::ICoreAccelerators *,Windows::UI::Core::AcceleratorKeyEventArgs *> *,void *,EventRegistrationToken *)
0x18004d5a8  mov     ebx, eax
0x18004d5aa  test    eax, eax
0x18004d5ac  jns     short loc_18004D5DE
0x18004d5ae  mov     rcx, [rbp+5Fh]; this
0x18004d5b2  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004d5b9  mov     r9d, ebx; char *
0x18004d5bc  mov     edx, 4D1h; void *
0x18004d5c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5c6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004d5ca  test    rcx, rcx
0x18004d5cd  jz      loc_18004D6AA
0x18004d5d3  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d5d9  jmp     loc_18004D6AA
0x18004d5de  lea     rbx, [rdi+220h]
0x18004d5e5  cmp     qword ptr [rbx], 0
0x18004d5e9  jnz     short loc_18004D634
0x18004d5eb  mov     rcx, rbx
0x18004d5ee  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d5f3  mov     rcx, [rdi+230h]
0x18004d5fa  mov     rdx, rbx
0x18004d5fd  call    cs:__imp_CreateInputSystemClientConnection
0x18004d603  mov     esi, eax
0x18004d605  test    eax, eax
0x18004d607  jns     short loc_18004D634
0x18004d609  mov     edx, 4D7h; void *
0x18004d60e  mov     rcx, [rbp+5Fh]; this
0x18004d612  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004d619  mov     r9d, esi; char *
0x18004d61c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d621  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004d625  test    rcx, rcx
0x18004d628  jz      short loc_18004D630
0x18004d62a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d630  mov     ebx, esi
0x18004d632  jmp     short loc_18004D6AA
0x18004d634  lea     r14, [rdi+228h]
0x18004d63b  cmp     qword ptr [r14], 0
0x18004d63f  jnz     short loc_18004D699
0x18004d641  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x18004d645  mov     [rbp+57h+arg_18], 0
0x18004d64c  mov     rcx, rdi; this
0x18004d64f  call    ?get_ComponentViewInstanceId@CCoreWindowSite@Core@UI@Windows@@AEAAJPEAI@Z; Windows::UI::Core::CCoreWindowSite::get_ComponentViewInstanceId(uint *)
0x18004d654  mov     esi, eax
0x18004d656  test    eax, eax
0x18004d658  jns     short loc_18004D661
0x18004d65a  mov     edx, 4E0h
0x18004d65f  jmp     short loc_18004D60E
0x18004d661  mov     rcx, [rbx]
0x18004d664  lea     rax, [rdi+58h]
0x18004d668  mov     r8d, [rbp+57h+arg_18]
0x18004d66c  neg     rdi
0x18004d66f  sbb     r9, r9
0x18004d672  mov     rdx, [rcx]
0x18004d675  and     r9, rax
0x18004d678  mov     rax, [rdx+18h]
0x18004d67c  lea     rdx, [rbp+57h+var_68]
0x18004d680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d685  mov     rdx, rax
0x18004d688  mov     rcx, r14
0x18004d68b  call    ??4?$ComPtr@UIInputAttemptedDeliveryClient@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IInputAttemptedDeliveryClient>::operator=(Microsoft::WRL::ComPtr<IInputAttemptedDeliveryClient> &&)
0x18004d690  lea     rcx, [rbp+57h+var_68]
0x18004d694  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004d699  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004d69d  test    rcx, rcx
0x18004d6a0  jz      short loc_18004D6A8
0x18004d6a2  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d6a8  xor     ebx, ebx
0x18004d6aa  lea     rcx, [rbp+57h+var_60]; this
0x18004d6ae  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18004d6b3  lea     r11, [rsp+0A0h+var_10]
0x18004d6bb  mov     eax, ebx
0x18004d6bd  mov     rbx, [r11+20h]
0x18004d6c1  mov     rsi, [r11+28h]
0x18004d6c5  mov     rsp, r11
0x18004d6c8  pop     r14
0x18004d6ca  pop     rdi
0x18004d6cb  pop     rbp
0x18004d6cc  retn
```
