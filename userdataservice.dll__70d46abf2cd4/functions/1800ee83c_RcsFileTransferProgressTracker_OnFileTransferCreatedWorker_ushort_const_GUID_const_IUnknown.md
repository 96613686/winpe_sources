# RcsFileTransferProgressTracker::_OnFileTransferCreatedWorker(ushort const *,_GUID const &,IUnknown *)

- ea: `0x1800ee83c`
- end: `0x1800eead3`
- name: `?_OnFileTransferCreatedWorker@RcsFileTransferProgressTracker@@IEAAJPEBGAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(RcsFileTransferProgressTracker *__hidden this, const unsigned __int16 *, const struct _GUID *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ed810`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18006db44`
- `0x180072ccc`
- `0x180075f98`
- `0x18007cc84`
- `0x180090804`
- `0x1800a73a4`
- `0x1800ed0a0`
- `0x1800ee83c`
- `0x1800eebbc`
- `0x1800eef0c`
- `0x18010a674`
- `0x18010a724`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ee914`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ee914`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800ee8e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800ee8e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ee995`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ee995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ee9ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eea32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ee9ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eea32`

## string_xrefs

- `0x1800ee892`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`
- `0x1800ee93e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`
- `0x1800ee9a7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`
- `0x1800ee9db`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferProgressTracker::_OnFileTransferCreatedWorker(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        struct IUnknown *a4)
{
  __int64 *v8; // rax
  int ImsClient; // ebx
  __int64 v10; // r9
  RcsServiceManager *v12; // rbx
  __int64 v13; // r9
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r15
  WINBOOL fPending; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  struct Windows::Phone::Restricted::Cellular::Rcs::IImsClient *v21; // [rsp+40h] [rbp-20h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+48h] BYREF

  v20 = 0;
  if ( !a4 )
  {
    v21 = 0;
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
    v12 = (RcsServiceManager *)Context;
    if ( !Context )
    {
      v12 = (RcsServiceManager *)qword_18015DCE0;
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v23[0] = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(v23);
    }
    ImsClient = RcsServiceManager::GetImsClient(v12, a3, &v21);
    if ( ImsClient >= 0 )
    {
      v14 = tlx::replace<RcsChatAdapter,&void _RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)>(&v20);
      ImsClient = RcsFileTransferAdapter::CreateInstance(v21, a2, (struct RcsFileTransferAdapter **)v14);
      if ( ImsClient >= 0 )
      {
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v21);
        goto LABEL_16;
      }
      v13 = 281;
    }
    else
    {
      v13 = 274;
    }
    Log_HREvent(
      (unsigned int)ImsClient,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcsfiletransferprogresstracker.cpp",
      v13);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v21);
    goto LABEL_5;
  }
  v8 = tlx::replace<RcsChatAdapter,&void _RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)>(&v20);
  ImsClient = RcsFileTransferAdapter::CreateInstance(a4, (struct RcsFileTransferAdapter **)v8);
  if ( ImsClient < 0 )
  {
    v10 = 269;
LABEL_4:
    Log_HREvent(
      (unsigned int)ImsClient,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcsfiletransferprogresstracker.cpp",
      v10);
LABEL_5:
    if ( v20 )
      _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(v20);
    return (unsigned int)ImsClient;
  }
LABEL_16:
  EnterCriticalSection(this + 1);
  if ( LODWORD(this->SpinCount) )
    Log_AssertionEvent_2(
      v15,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcsfiletransferprogresstracker.cpp",
      288);
  Context = 0;
  ImsClient = RcsFileTransferProgressTracker::_GetFileTransferInfo(
                (RcsFileTransferProgressTracker *)this,
                a3,
                (struct RcsFileTransferProgressTracker::RcsFileTransferInfo **)&Context);
  if ( ImsClient < 0 )
  {
    v16 = 291;
    v17 = 1;
LABEL_20:
    Log_HREvent(
      (unsigned int)ImsClient,
      v17,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcsfiletransferprogresstracker.cpp",
      v16);
    LeaveCriticalSection(this + 1);
    goto LABEL_5;
  }
  v23[0] = v20;
  if ( !(unsigned __int8)utl::list<RcsEventNotification<RcsRemoteContactComposingNotificationArgs> *,utl::allocator<RcsEventNotification<RcsRemoteContactComposingNotificationArgs> *>>::push_back(
                           (char *)Context + 56,
                           v23) )
  {
    v16 = 294;
    v17 = 0;
    ImsClient = -2147024882;
    goto LABEL_20;
  }
  v18 = v20;
  v20 = 0;
  LeaveCriticalSection(this + 1);
  ImsClient = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v18 + 32LL))(v18, &this->OwningThread);
  if ( ImsClient < 0 )
  {
    v10 = 302;
    goto LABEL_4;
  }
  v24 = 0;
  ImsClient = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, &v24);
  if ( ImsClient < 0 )
  {
    v10 = 307;
    goto LABEL_4;
  }
  ImsClient = RcsFileTransferProgressTracker::_OnFileTransferStatusChangedWorker(this, a2, a3, v24);
  if ( ImsClient < 0 )
  {
    v10 = 309;
    goto LABEL_4;
  }
  if ( v20 )
    _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(v20);
  return 0;
}

```

## disassembly

```asm
0x1800ee83c  mov     [rsp-28h+arg_0], rbx
0x1800ee841  mov     [rsp-28h+arg_8], rsi
0x1800ee846  push    rbp
0x1800ee847  push    rdi
0x1800ee848  push    r12
0x1800ee84a  push    r14
0x1800ee84c  push    r15
0x1800ee84e  mov     rbp, rsp
0x1800ee851  sub     rsp, 60h
0x1800ee855  mov     [rbp+var_28], 0
0x1800ee85d  mov     rbx, r9
0x1800ee860  mov     r14, r8
0x1800ee863  mov     r12, rdx
0x1800ee866  mov     rdi, rcx
0x1800ee869  test    r9, r9
0x1800ee86c  jz      short loc_1800EE8BA
0x1800ee86e  lea     rcx, [rbp+var_28]
0x1800ee872  call    ??$replace@VRcsChatAdapter@@$1??$_RcsAdapterShutdownableDeleter@VRcsChatAdapter@@@@YAXPEAV1@@Z@tlx@@YAPEAPEAVRcsChatAdapter@@AEAV?$auto_ptr@VRcsChatAdapter@@$1??$_RcsAdapterShutdownableDeleter@VRcsChatAdapter@@@@YAXPEAV1@@Z@0@@Z; tlx::replace<RcsChatAdapter,&_RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)>(tlx::auto_ptr<RcsChatAdapter,&_RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)> &)
0x1800ee877  mov     rdx, rax; struct RcsFileTransferAdapter **
0x1800ee87a  mov     rcx, rbx; struct IUnknown *
0x1800ee87d  call    ?CreateInstance@RcsFileTransferAdapter@@SAJPEAUIUnknown@@PEAPEAV1@@Z; RcsFileTransferAdapter::CreateInstance(IUnknown *,RcsFileTransferAdapter * *)
0x1800ee882  mov     ebx, eax
0x1800ee884  test    eax, eax
0x1800ee886  jns     loc_1800EE98E
0x1800ee88c  mov     r9d, 10Dh
0x1800ee892  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ee899  mov     edx, 1
0x1800ee89e  mov     ecx, ebx
0x1800ee8a0  call    Log_HREvent
0x1800ee8a5  mov     rcx, [rbp+var_28]
0x1800ee8a9  test    rcx, rcx
0x1800ee8ac  jz      short loc_1800EE8B3
0x1800ee8ae  call    ??$_RcsAdapterShutdownableDeleter@VRcsServiceStatusAdapterImpl@@@@YAXPEAVRcsServiceStatusAdapterImpl@@@Z; _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(RcsServiceStatusAdapterImpl *)
0x1800ee8b3  mov     eax, ebx
0x1800ee8b5  jmp     loc_1800EEABA
0x1800ee8ba  lea     r9, [rbp+Context]; lpContext
0x1800ee8be  mov     [rbp+var_20], 0
0x1800ee8c6  lea     r8, [rbp+fPending]; fPending
0x1800ee8ca  mov     [rbp+fPending], 0
0x1800ee8d1  xor     edx, edx; dwFlags
0x1800ee8d3  mov     [rbp+Context], 0
0x1800ee8db  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800ee8e2  call    cs:__imp_InitOnceBeginInitialize
0x1800ee8e8  mov     rbx, [rbp+Context]
0x1800ee8ec  test    rbx, rbx
0x1800ee8ef  jnz     short loc_1800EE923
0x1800ee8f1  lea     rbx, qword_18015DCE0
0x1800ee8f8  mov     rcx, rbx; this
0x1800ee8fb  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800ee900  mov     r8, rbx; lpContext
0x1800ee903  mov     [rbp+var_10], 0
0x1800ee90b  xor     edx, edx; dwFlags
0x1800ee90d  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800ee914  call    cs:__imp_InitOnceComplete
0x1800ee91a  lea     rcx, [rbp+var_10]
0x1800ee91e  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800ee923  lea     r8, [rbp+var_20]; struct Windows::Phone::Restricted::Cellular::Rcs::IImsClient **
0x1800ee927  mov     rdx, r14; struct _GUID *
0x1800ee92a  mov     rcx, rbx; this
0x1800ee92d  call    ?GetImsClient@RcsServiceManager@@QEAAJAEBU_GUID@@PEAPEAUIImsClient@Rcs@Cellular@Restricted@Phone@Windows@@@Z; RcsServiceManager::GetImsClient(_GUID const &,Windows::Phone::Restricted::Cellular::Rcs::IImsClient * *)
0x1800ee932  mov     ebx, eax
0x1800ee934  test    eax, eax
0x1800ee936  jns     short loc_1800EE95F
0x1800ee938  mov     r9d, 112h
0x1800ee93e  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ee945  mov     edx, 1
0x1800ee94a  mov     ecx, ebx
0x1800ee94c  call    Log_HREvent
0x1800ee951  lea     rcx, [rbp+var_20]
0x1800ee955  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ee95a  jmp     loc_1800EE8A5
0x1800ee95f  lea     rcx, [rbp+var_28]
0x1800ee963  call    ??$replace@VRcsChatAdapter@@$1??$_RcsAdapterShutdownableDeleter@VRcsChatAdapter@@@@YAXPEAV1@@Z@tlx@@YAPEAPEAVRcsChatAdapter@@AEAV?$auto_ptr@VRcsChatAdapter@@$1??$_RcsAdapterShutdownableDeleter@VRcsChatAdapter@@@@YAXPEAV1@@Z@0@@Z; tlx::replace<RcsChatAdapter,&_RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)>(tlx::auto_ptr<RcsChatAdapter,&_RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)> &)
0x1800ee968  mov     rcx, [rbp+var_20]; struct Windows::Phone::Restricted::Cellular::Rcs::IImsClient *
0x1800ee96c  mov     r8, rax; struct RcsFileTransferAdapter **
0x1800ee96f  mov     rdx, r12; unsigned __int16 *
0x1800ee972  call    ?CreateInstance@RcsFileTransferAdapter@@SAJPEAUIImsClient@Rcs@Cellular@Restricted@Phone@Windows@@PEBGPEAPEAV1@@Z; RcsFileTransferAdapter::CreateInstance(Windows::Phone::Restricted::Cellular::Rcs::IImsClient *,ushort const *,RcsFileTransferAdapter * *)
0x1800ee977  mov     ebx, eax
0x1800ee979  test    eax, eax
0x1800ee97b  jns     short loc_1800EE985
0x1800ee97d  mov     r9d, 119h
0x1800ee983  jmp     short loc_1800EE93E
0x1800ee985  lea     rcx, [rbp+var_20]
0x1800ee989  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ee98e  lea     rsi, [rdi+28h]
0x1800ee992  mov     rcx, rsi; lpCriticalSection
0x1800ee995  call    cs:__imp_EnterCriticalSection
0x1800ee99b  cmp     dword ptr [rdi+20h], 0
0x1800ee99f  jz      short loc_1800EE9B3
0x1800ee9a1  mov     r8d, 120h
0x1800ee9a7  lea     rdx, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ee9ae  call    Log_AssertionEvent_2
0x1800ee9b3  lea     r8, [rbp+Context]; struct RcsFileTransferProgressTracker::RcsFileTransferInfo **
0x1800ee9b7  mov     [rbp+Context], 0
0x1800ee9bf  mov     rdx, r14; struct _GUID *
0x1800ee9c2  mov     rcx, rdi; this
0x1800ee9c5  call    ?_GetFileTransferInfo@RcsFileTransferProgressTracker@@AEAAJAEBU_GUID@@AEAPEAURcsFileTransferInfo@1@@Z; RcsFileTransferProgressTracker::_GetFileTransferInfo(_GUID const &,RcsFileTransferProgressTracker::RcsFileTransferInfo * &)
0x1800ee9ca  mov     ebx, eax
0x1800ee9cc  test    eax, eax
0x1800ee9ce  jns     short loc_1800EE9F7
0x1800ee9d0  mov     r9d, 123h
0x1800ee9d6  mov     edx, 1
0x1800ee9db  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ee9e2  mov     ecx, ebx
0x1800ee9e4  call    Log_HREvent
0x1800ee9e9  mov     rcx, rsi; lpCriticalSection
0x1800ee9ec  call    cs:__imp_LeaveCriticalSection
0x1800ee9f2  jmp     loc_1800EE8A5
0x1800ee9f7  mov     rax, [rbp+var_28]
0x1800ee9fb  lea     rdx, [rbp+var_10]
0x1800ee9ff  mov     rcx, [rbp+Context]
0x1800eea03  add     rcx, 38h ; '8'
0x1800eea07  mov     [rbp+var_10], rax
0x1800eea0b  call    ?push_back@?$list@PEAU?$RcsEventNotification@URcsRemoteContactComposingNotificationArgs@@@@V?$allocator@PEAU?$RcsEventNotification@URcsRemoteContactComposingNotificationArgs@@@@@utl@@@utl@@QEAA_NAEBQEAU?$RcsEventNotification@URcsRemoteContactComposingNotificationArgs@@@@@Z; utl::list<RcsEventNotification<RcsRemoteContactComposingNotificationArgs> *,utl::allocator<RcsEventNotification<RcsRemoteContactComposingNotificationArgs> *>>::push_back(RcsEventNotification<RcsRemoteContactComposingNotificationArgs> * const &)
0x1800eea10  test    al, al
0x1800eea12  jnz     short loc_1800EEA23
0x1800eea14  mov     r9d, 126h
0x1800eea1a  xor     edx, edx
0x1800eea1c  mov     ebx, 8007000Eh
0x1800eea21  jmp     short loc_1800EE9DB
0x1800eea23  mov     r15, [rbp+var_28]
0x1800eea27  mov     rcx, rsi; lpCriticalSection
0x1800eea2a  mov     [rbp+var_28], 0
0x1800eea32  call    cs:__imp_LeaveCriticalSection
0x1800eea38  mov     rax, [r15]
0x1800eea3b  lea     rdx, [rdi+10h]
0x1800eea3f  mov     rcx, r15
0x1800eea42  mov     rax, [rax+20h]
0x1800eea46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eea4b  mov     ebx, eax
0x1800eea4d  test    eax, eax
0x1800eea4f  jns     short loc_1800EEA5C
0x1800eea51  mov     r9d, 12Eh
0x1800eea57  jmp     loc_1800EE892
0x1800eea5c  mov     [rbp+arg_18], 0
0x1800eea63  lea     rdx, [rbp+arg_18]
0x1800eea67  mov     rax, [r15]
0x1800eea6a  mov     rcx, r15
0x1800eea6d  mov     rax, [rax+18h]
0x1800eea71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eea76  mov     ebx, eax
0x1800eea78  test    eax, eax
0x1800eea7a  jns     short loc_1800EEA87
0x1800eea7c  mov     r9d, 133h
0x1800eea82  jmp     loc_1800EE892
0x1800eea87  mov     r9d, [rbp+arg_18]
0x1800eea8b  mov     r8, r14
0x1800eea8e  mov     rdx, r12
0x1800eea91  mov     rcx, rdi
0x1800eea94  call    ?_OnFileTransferStatusChangedWorker@RcsFileTransferProgressTracker@@IEAAJPEBGAEBU_GUID@@W4RcsFileTransferStatusEx@@@Z; RcsFileTransferProgressTracker::_OnFileTransferStatusChangedWorker(ushort const *,_GUID const &,RcsFileTransferStatusEx)
0x1800eea99  mov     ebx, eax
0x1800eea9b  test    eax, eax
0x1800eea9d  jns     short loc_1800EEAAA
0x1800eea9f  mov     r9d, 135h
0x1800eeaa5  jmp     loc_1800EE892
0x1800eeaaa  mov     rcx, [rbp+var_28]
0x1800eeaae  test    rcx, rcx
0x1800eeab1  jz      short loc_1800EEAB8
0x1800eeab3  call    ??$_RcsAdapterShutdownableDeleter@VRcsServiceStatusAdapterImpl@@@@YAXPEAVRcsServiceStatusAdapterImpl@@@Z; _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(RcsServiceStatusAdapterImpl *)
0x1800eeab8  xor     eax, eax
0x1800eeaba  lea     r11, [rsp+60h+var_s0]
0x1800eeabf  mov     rbx, [r11+30h]
0x1800eeac3  mov     rsi, [r11+38h]
0x1800eeac7  mov     rsp, r11
0x1800eeaca  pop     r15
0x1800eeacc  pop     r14
0x1800eeace  pop     r12
0x1800eead0  pop     rdi
0x1800eead1  pop     rbp
0x1800eead2  retn
```
