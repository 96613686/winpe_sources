# DataModelService::OnStopping(int)

- ea: `0x18002db90`
- end: `0x18002dd5b`
- name: `?OnStopping@DataModelService@@UEAAJH@Z`
- size: `459`
- prototype: `__int64 __fastcall(DataModelService *__hidden this, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007760`
- `0x180008f0c`
- `0x18002db90`
- `0x18002dd64`
- `0x18002ddbc`
- `0x18002e070`
- `0x18002ed94`
- `0x18002f610`
- `0x18006db44`
- `0x180072ccc`
- `0x18007dd58`
- `0x180082bc4`
- `0x18009b1b0`
- `0x18012c7b0`

## import_xrefs

- `MessagingDataModel2!Messaging_MessagingOMStartupShutdown` at `0x18002dc6d`
- `MessagingDataModel2!Messaging_MessagingOMStartupShutdown` at `0x18002dc6d`
- `MessagingDataModel2!Messaging_ShutdownCloudServices` at `0x18002dd0f`
- `MessagingDataModel2!Messaging_ShutdownCloudServices` at `0x18002dd0f`
- `MessagingDataModel2!UnInitMessagingObjectModelModule` at `0x18002dc67`
- `MessagingDataModel2!UnInitMessagingObjectModelModule` at `0x18002dc67`
- `MessagingDataModel2!Messaging_ShutdownNotification` at `0x18002dc86`
- `MessagingDataModel2!Messaging_ShutdownNotification` at `0x18002dc86`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002dcf7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002dcf7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002dcc3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002dcc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dbb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dbb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd3b`
- `CEMAPI!MAPIUninitialize` at `0x18002dd2d`
- `CEMAPI!MAPIUninitialize` at `0x18002dd2d`

## string_xrefs

- `0x18002dc15`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\dll\datamodelserviceendpoint.cpp`

## pseudocode

```c
__int64 __fastcall DataModelService::OnStopping(DataModelService *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // r8
  DataModelService *v3; // rcx
  int v4; // eax
  __int64 v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // r8
  RcsServiceManager *v14; // rbx
  int v15; // eax
  __int64 v16; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-38h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-28h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      User_DataModel_Service_START,
      v2,
      1,
      v20);
  CleanupUDSGlobals();
  v4 = DataModelService::_PublishInitialized(v3, 0);
  if ( v4 < 0 )
    Log_HREvent_28((unsigned int)v4, 0, v5, 145);
  v6 = UnregisterEndpoint();
  v7 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\dll\\datamodelserviceendpoint.cpp",
      125);
    Log_HREvent_28(v7, 0, v8, 147);
  }
  TerminateDataSessions();
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Chat_DataModel_Service_START,
      v9,
      1,
      v20);
  UnInitMessagingObjectModelModule();
  v10 = Messaging_MessagingOMStartupShutdown();
  if ( v10 < 0 )
    Log_HREvent_28((unsigned int)v10, 0, v11, 155);
  v12 = Messaging_ShutdownNotification();
  if ( v12 < 0 )
    Log_HREvent_28((unsigned int)v12, 0, v13, 156);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
  v14 = (RcsServiceManager *)Context;
  if ( !Context )
  {
    v14 = (RcsServiceManager *)qword_18015DCE0;
    RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
    v20[0] = 0;
    InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(v20);
  }
  RcsServiceManager::Shutdown(v14);
  v15 = Messaging_ShutdownCloudServices();
  if ( v15 < 0 )
    Log_HREvent_28((unsigned int)v15, 0, v16, 160);
  lambda_dfc7c5fcb6ba966ed64c0f771fa6d09b_::operator()();
  MAPIUninitialize();
  lambda_ee41f08ba9088a9870334d71e577b63a_::operator()();
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x18002db90  mov     [rsp+arg_8], rbx
0x18002db95  push    rdi
0x18002db96  sub     rsp, 60h
0x18002db9a  mov     rax, cs:__security_cookie
0x18002dba1  xor     rax, rsp
0x18002dba4  mov     [rsp+68h+var_18], rax
0x18002dba9  lea     rdi, [rcx+0C0h]
0x18002dbb0  mov     rcx, rdi; lpCriticalSection
0x18002dbb3  call    cs:__imp_EnterCriticalSection
0x18002dbb9  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 1
0x18002dbc0  jz      short loc_18002DBE5
0x18002dbc2  lea     rax, [rsp+68h+var_28]
0x18002dbc7  mov     r9d, 1
0x18002dbcd  lea     rdx, User_DataModel_Service_START
0x18002dbd4  mov     [rsp+68h+var_48], rax
0x18002dbd9  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18002dbe0  call    McGenEventWrite_EventWriteTransfer
0x18002dbe5  call    CleanupUDSGlobals
0x18002dbea  xor     edx, edx; int
0x18002dbec  call    ?_PublishInitialized@DataModelService@@AEAAJH@Z; DataModelService::_PublishInitialized(int)
0x18002dbf1  test    eax, eax
0x18002dbf3  jns     short loc_18002DC04
0x18002dbf5  xor     edx, edx
0x18002dbf7  mov     r9d, 91h
0x18002dbfd  mov     ecx, eax
0x18002dbff  call    Log_HREvent_28
0x18002dc04  call    UnregisterEndpoint
0x18002dc09  mov     ebx, eax
0x18002dc0b  test    eax, eax
0x18002dc0d  jns     short loc_18002DC36
0x18002dc0f  mov     r9d, 7Dh ; '}'
0x18002dc15  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002dc1c  mov     ecx, eax
0x18002dc1e  lea     edx, [r9-7Ch]
0x18002dc22  call    Log_HREvent
0x18002dc27  xor     edx, edx
0x18002dc29  mov     r9d, 93h
0x18002dc2f  mov     ecx, ebx
0x18002dc31  call    Log_HREvent_28
0x18002dc36  call    ?TerminateDataSessions@@YAXXZ; TerminateDataSessions(void)
0x18002dc3b  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 1
0x18002dc42  jz      short loc_18002DC67
0x18002dc44  lea     rax, [rsp+68h+var_28]
0x18002dc49  mov     r9d, 1
0x18002dc4f  lea     rdx, Chat_DataModel_Service_START
0x18002dc56  mov     [rsp+68h+var_48], rax
0x18002dc5b  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18002dc62  call    McGenEventWrite_EventWriteTransfer
0x18002dc67  call    cs:__imp_UnInitMessagingObjectModelModule
0x18002dc6d  call    cs:__imp_Messaging_MessagingOMStartupShutdown
0x18002dc73  test    eax, eax
0x18002dc75  jns     short loc_18002DC86
0x18002dc77  xor     edx, edx
0x18002dc79  mov     r9d, 9Bh
0x18002dc7f  mov     ecx, eax
0x18002dc81  call    Log_HREvent_28
0x18002dc86  call    cs:__imp_Messaging_ShutdownNotification
0x18002dc8c  test    eax, eax
0x18002dc8e  jns     short loc_18002DC9F
0x18002dc90  xor     edx, edx
0x18002dc92  mov     r9d, 9Ch
0x18002dc98  mov     ecx, eax
0x18002dc9a  call    Log_HREvent_28
0x18002dc9f  lea     r9, [rsp+68h+Context]; lpContext
0x18002dca4  mov     [rsp+68h+fPending], 0
0x18002dcac  lea     r8, [rsp+68h+fPending]; fPending
0x18002dcb1  mov     [rsp+68h+Context], 0
0x18002dcba  xor     edx, edx; dwFlags
0x18002dcbc  lea     rcx, stru_18015DCD8; lpInitOnce
0x18002dcc3  call    cs:__imp_InitOnceBeginInitialize
0x18002dcc9  mov     rbx, [rsp+68h+Context]
0x18002dcce  test    rbx, rbx
0x18002dcd1  jnz     short loc_18002DD07
0x18002dcd3  lea     rbx, qword_18015DCE0
0x18002dcda  mov     rcx, rbx; this
0x18002dcdd  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x18002dce2  mov     r8, rbx; lpContext
0x18002dce5  mov     [rsp+68h+var_28], 0
0x18002dcee  xor     edx, edx; dwFlags
0x18002dcf0  lea     rcx, stru_18015DCD8; lpInitOnce
0x18002dcf7  call    cs:__imp_InitOnceComplete
0x18002dcfd  lea     rcx, [rsp+68h+var_28]
0x18002dd02  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002dd07  mov     rcx, rbx; this
0x18002dd0a  call    ?Shutdown@RcsServiceManager@@QEAAXXZ; RcsServiceManager::Shutdown(void)
0x18002dd0f  call    cs:__imp_Messaging_ShutdownCloudServices
0x18002dd15  test    eax, eax
0x18002dd17  jns     short loc_18002DD28
0x18002dd19  xor     edx, edx
0x18002dd1b  mov     r9d, 0A0h
0x18002dd21  mov     ecx, eax
0x18002dd23  call    Log_HREvent_28
0x18002dd28  call    _lambda_dfc7c5fcb6ba966ed64c0f771fa6d09b___operator__
0x18002dd2d  call    cs:__imp_MAPIUninitialize
0x18002dd33  call    _lambda_ee41f08ba9088a9870334d71e577b63a___operator__
0x18002dd38  mov     rcx, rdi; lpCriticalSection
0x18002dd3b  call    cs:__imp_LeaveCriticalSection
0x18002dd41  xor     eax, eax
0x18002dd43  mov     rcx, [rsp+68h+var_18]
0x18002dd48  xor     rcx, rsp; StackCookie
0x18002dd4b  call    __security_check_cookie
0x18002dd50  mov     rbx, [rsp+68h+arg_8]
0x18002dd55  add     rsp, 60h
0x18002dd59  pop     rdi
0x18002dd5a  retn
```
