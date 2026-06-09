# UserManagerService::InitializeSvc(void)

- ea: `0x180072004`
- end: `0x18007228d`
- name: `?InitializeSvc@UserManagerService@@AEAAKXZ`
- size: `649`
- prototype: `unsigned int __fastcall(UserManagerService *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073fa0`

## callees

- `0x18000ce48`
- `0x1800179c0`
- `0x180046b24`
- `0x1800624bc`
- `0x18007008c`
- `0x180071f50`
- `0x180072004`
- `0x180073928`
- `0x180073b4c`
- `0x180075590`
- `0x1800758f0`
- `0x1800b4180`
- `0x1800b542c`
- `0x1800b68e4`
- `0x1800b7270`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072059`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072059`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800721cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800721cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800721e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800721f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800721e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800721f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800720ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800720ed`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180072023`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180072023`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180072258`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180072258`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18007224d`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18007224d`
- `ntdll!NtQuerySystemInformation` at `0x18007209f`
- `ntdll!NtQuerySystemInformation` at `0x18007209f`

## string_xrefs

- `0x1800721c4`: `LegacyUserManager.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserManagerService::InitializeSvc(UserManagerService *this)
{
  __int64 v2; // rcx
  int v3; // r14d
  HRESULT v4; // eax
  signed int v5; // ebx
  UserMgrSvcTraceLog *v6; // rcx
  char v7; // al
  int v8; // eax
  UserManagerTokenAndShellHandler *v9; // rcx
  int v10; // edi
  signed int v11; // eax
  struct UserManagerTokenAndShellHandler *v12; // rdx
  UserMgrCli *v13; // rcx
  bool v14; // cc
  UserManagerTokenAndShellHandler *v15; // rcx
  UserMgrCli *v16; // rcx
  UserManagerTokenAndShellHandler *v17; // rcx
  HMODULE Library; // rax
  __int64 v19; // rcx
  __int64 (*v20)(void); // rax
  __int64 v21; // rcx
  struct _RTL_CRITICAL_SECTION *SystemInformation; // [rsp+68h] [rbp+38h] BYREF
  int v24; // [rsp+70h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF

  v24 = 0;
  v3 = RoInitialize(1);
  if ( v3 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_33;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_33;
  LOWORD(SystemInformation) = 0;
  NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0);
  if ( (_BYTE)SystemInformation || NtCurrentPeb()->BeingDebugged )
  {
    v7 = 1;
    byte_180148172 = 1;
  }
  else
  {
    v7 = byte_180148172;
  }
  if ( v7 )
    UserMgrSvcTraceLog::Start(v6);
  v4 = Windows::Internal::Events::WatchdogEventCallMonitor::Initialize();
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_33;
  EnterCriticalSection(&stru_180148638);
  SystemInformation = &stru_180148638;
  v5 = 0;
  v8 = Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State;
  if ( !Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Context);
    v5 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Async::SuspendDispatchQueue,Windows::Internal::Async::SuspendDispatchQueue,>(&Context);
    if ( v5 < 0 )
    {
      Windows::Internal::Async::Details::HardenedAsyncMonitor::ProcessState::Shutdown((Windows::Internal::Async::Details::HardenedAsyncMonitor::ProcessState *)&Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State);
      goto LABEL_17;
    }
    v8 = Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State;
  }
  Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State = v8 + 1;
LABEL_17:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&SystemInformation);
  if ( v5 >= 0 )
  {
    g_asyncMonitorInitialized = 1;
  }
  else if ( v5 != -2147221164 )
  {
    v10 = (unsigned __int16)v5;
    if ( (v5 & 0x1FFF0000) != 0x70000 )
      v10 = v5;
    goto LABEL_35;
  }
  v11 = UserManagerTokenAndShellHandler::Initialize(v9, &v24);
  v10 = v11;
  v14 = v11 <= 0;
  if ( !v11 )
  {
    v4 = UserMgrCli::Initialize(v13, v12);
    v5 = v4;
    if ( v4 >= 0 )
    {
      UserManagerTokenAndShellHandler::RestoreStateAfterRestart(v15);
      v4 = UserMgrCli::RpcInitialize(v16);
      v5 = v4;
      if ( v4 >= 0 )
      {
        v11 = UserManagerTokenAndShellHandler::LaunchInitialProcessesAsNecessary(v17);
        v10 = v11;
        v14 = v11 <= 0;
        if ( v11 )
          goto LABEL_24;
        Library = LoadLibraryExW(L"LegacyUserManager.dll", 0, 0x800u);
        *((_QWORD *)this + 7) = Library;
        if ( !Library )
          goto LABEL_41;
        *((_QWORD *)this + 8) = GetProcAddress(Library, "InitializeLegacyUserManager");
        *((_QWORD *)this + 9) = GetProcAddress(*((HMODULE *)this + 7), "ShutdownLegacyUserManager");
        v20 = (__int64 (*)(void))*((_QWORD *)this + 8);
        if ( !v20 )
          goto LABEL_41;
        v4 = v20();
        v5 = v4;
        if ( v4 >= 0 )
          goto LABEL_41;
      }
    }
LABEL_33:
    v10 = (unsigned __int16)v5;
    if ( (v4 & 0x1FFF0000) != 0x70000 )
      v10 = v5;
    goto LABEL_35;
  }
LABEL_24:
  if ( v14 )
    v5 = v11;
  else
    v5 = (unsigned __int16)v11 | 0x80070000;
LABEL_35:
  Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(
    this,
    (unsigned int)v5);
  if ( v10 && v24 )
  {
    if ( v10 > 0 )
      v21 = (unsigned __int16)v10 | 0x80070000;
    else
      v21 = (unsigned int)v10;
    RoFailFastWithErrorContext(v21);
  }
LABEL_41:
  if ( v3 >= 0 )
    RoUninitialize();
  if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(v19, UMgrServiceInitResult, (unsigned int)v10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return 0;
}

```

## disassembly

```asm
0x180072004  push    rbp
0x180072006  push    rbx
0x180072007  push    rsi
0x180072008  push    rdi
0x180072009  push    r14
0x18007200b  mov     rbp, rsp
0x18007200e  sub     rsp, 30h
0x180072012  mov     rsi, rcx
0x180072015  mov     [rbp+arg_10], 0
0x18007201c  mov     edi, 1
0x180072021  mov     ecx, edi
0x180072023  call    cs:__imp_RoInitialize
0x180072029  mov     r14d, eax
0x18007202c  test    eax, eax
0x18007202e  jns     short loc_180072035
0x180072030  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072035  mov     [rbp+arg_18], 0
0x18007203d  lea     rax, [rbp+arg_18]
0x180072041  mov     [rsp+30h+ppv], rax; ppv
0x180072046  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007204d  mov     r8d, edi; dwClsContext
0x180072050  xor     edx, edx; pUnkOuter
0x180072052  lea     rcx, CLSID_GlobalOptions; rclsid
0x180072059  call    cs:__imp_CoCreateInstance
0x18007205f  mov     ebx, eax
0x180072061  test    eax, eax
0x180072063  js      loc_180072217
0x180072069  mov     rcx, [rbp+arg_18]
0x18007206d  mov     rax, [rcx]
0x180072070  mov     r8, rdi
0x180072073  mov     edx, 5
0x180072078  mov     rax, [rax+18h]
0x18007207c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072081  mov     ebx, eax
0x180072083  test    eax, eax
0x180072085  js      loc_180072217
0x18007208b  xor     eax, eax
0x18007208d  mov     word ptr [rbp+SystemInformation], ax
0x180072091  xor     r9d, r9d; ReturnLength
0x180072094  lea     r8d, [rax+2]; SystemInformationLength
0x180072098  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18007209c  lea     ecx, [rax+23h]; SystemInformationClass
0x18007209f  call    cs:__imp_NtQuerySystemInformation
0x1800720a5  cmp     byte ptr [rbp+SystemInformation], 0
0x1800720a9  jnz     short loc_1800720C2
0x1800720ab  mov     rax, gs:60h
0x1800720b4  cmp     byte ptr [rax+2], 0
0x1800720b8  jnz     short loc_1800720C2
0x1800720ba  mov     al, cs:byte_180148172
0x1800720c0  jmp     short loc_1800720CB
0x1800720c2  mov     al, dil
0x1800720c5  mov     cs:byte_180148172, al
0x1800720cb  test    al, al
0x1800720cd  jz      short loc_1800720D4
0x1800720cf  call    ?Start@UserMgrSvcTraceLog@@QEAAXXZ; UserMgrSvcTraceLog::Start(void)
0x1800720d4  call    ?Initialize@WatchdogEventCallMonitor@Events@Internal@Windows@@SAJXZ; Windows::Internal::Events::WatchdogEventCallMonitor::Initialize(void)
0x1800720d9  mov     ebx, eax
0x1800720db  test    eax, eax
0x1800720dd  js      loc_180072217
0x1800720e3  lea     rbx, stru_180148638
0x1800720ea  mov     rcx, rbx; lpCriticalSection
0x1800720ed  call    cs:__imp_EnterCriticalSection
0x1800720f3  mov     [rbp+SystemInformation], rbx
0x1800720f7  xor     ebx, ebx
0x1800720f9  mov     eax, cs:?s_State@HardenedAsyncMonitor@Details@Async@Internal@Windows@@0UProcessState@12345@A; Windows::Internal::Async::Details::HardenedAsyncMonitor::ProcessState Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State
0x1800720ff  test    eax, eax
0x180072101  jnz     short loc_180072135
0x180072103  lea     rcx, Context
0x18007210a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007210f  lea     rcx, Context
0x180072116  call    ??$MakeAndInitialize@VSuspendDispatchQueue@Async@Internal@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVSuspendDispatchQueue@Async@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Async::SuspendDispatchQueue,Windows::Internal::Async::SuspendDispatchQueue,>(Windows::Internal::Async::SuspendDispatchQueue * *)
0x18007211b  mov     ebx, eax
0x18007211d  test    eax, eax
0x18007211f  jns     short loc_18007212F
0x180072121  lea     rcx, ?s_State@HardenedAsyncMonitor@Details@Async@Internal@Windows@@0UProcessState@12345@A; this
0x180072128  call    ?Shutdown@ProcessState@HardenedAsyncMonitor@Details@Async@Internal@Windows@@QEAAXXZ; Windows::Internal::Async::Details::HardenedAsyncMonitor::ProcessState::Shutdown(void)
0x18007212d  jmp     short loc_18007213D
0x18007212f  mov     eax, cs:?s_State@HardenedAsyncMonitor@Details@Async@Internal@Windows@@0UProcessState@12345@A; Windows::Internal::Async::Details::HardenedAsyncMonitor::ProcessState Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State
0x180072135  add     eax, edi
0x180072137  mov     cs:?s_State@HardenedAsyncMonitor@Details@Async@Internal@Windows@@0UProcessState@12345@A, eax; Windows::Internal::Async::Details::HardenedAsyncMonitor::ProcessState Windows::Internal::Async::Details::HardenedAsyncMonitor::s_State
0x18007213d  lea     rcx, [rbp+SystemInformation]; this
0x180072141  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180072146  test    ebx, ebx
0x180072148  jns     short loc_180072169
0x18007214a  cmp     ebx, 80040154h
0x180072150  jz      short loc_180072170
0x180072152  mov     eax, ebx
0x180072154  and     eax, 1FFF0000h
0x180072159  movzx   edi, bx
0x18007215c  cmp     eax, 70000h
0x180072161  cmovnz  edi, ebx
0x180072164  jmp     loc_180072228
0x180072169  mov     cs:?g_asyncMonitorInitialized@@3_NA, dil; bool g_asyncMonitorInitialized
0x180072170  lea     rdx, [rbp+arg_10]; int *
0x180072174  call    ?Initialize@UserManagerTokenAndShellHandler@@QEAAKPEAH@Z; UserManagerTokenAndShellHandler::Initialize(int *)
0x180072179  mov     edi, eax
0x18007217b  test    eax, eax
0x18007217d  jz      short loc_180072196
0x18007217f  jg      short loc_180072188
0x180072181  mov     ebx, eax
0x180072183  jmp     loc_180072228
0x180072188  movzx   ebx, ax
0x18007218b  or      ebx, 80070000h
0x180072191  jmp     loc_180072228
0x180072196  call    ?Initialize@UserMgrCli@@QEAAJPEAVUserManagerTokenAndShellHandler@@@Z; UserMgrCli::Initialize(UserManagerTokenAndShellHandler *)
0x18007219b  mov     ebx, eax
0x18007219d  test    eax, eax
0x18007219f  js      short loc_180072217
0x1800721a1  call    ?RestoreStateAfterRestart@UserManagerTokenAndShellHandler@@QEAAXXZ; UserManagerTokenAndShellHandler::RestoreStateAfterRestart(void)
0x1800721a6  call    ?RpcInitialize@UserMgrCli@@QEAAJXZ; UserMgrCli::RpcInitialize(void)
0x1800721ab  mov     ebx, eax
0x1800721ad  test    eax, eax
0x1800721af  js      short loc_180072217
0x1800721b1  call    ?LaunchInitialProcessesAsNecessary@UserManagerTokenAndShellHandler@@QEAAKXZ; UserManagerTokenAndShellHandler::LaunchInitialProcessesAsNecessary(void)
0x1800721b6  mov     edi, eax
0x1800721b8  test    eax, eax
0x1800721ba  jnz     short loc_18007217F
0x1800721bc  xor     edx, edx; hFile
0x1800721be  mov     r8d, 800h; dwFlags
0x1800721c4  lea     rcx, aLegacyusermana; "LegacyUserManager.dll"
0x1800721cb  call    cs:__imp_LoadLibraryExW
0x1800721d1  mov     [rsi+38h], rax
0x1800721d5  test    rax, rax
0x1800721d8  jz      short loc_180072253
0x1800721da  lea     rdx, aInitializelega; "InitializeLegacyUserManager"
0x1800721e1  mov     rcx, rax; hModule
0x1800721e4  call    cs:__imp_GetProcAddress
0x1800721ea  mov     [rsi+40h], rax
0x1800721ee  lea     rdx, aShutdownlegacy; "ShutdownLegacyUserManager"
0x1800721f5  mov     rcx, [rsi+38h]; hModule
0x1800721f9  call    cs:__imp_GetProcAddress
0x1800721ff  mov     [rsi+48h], rax
0x180072203  mov     rax, [rsi+40h]
0x180072207  test    rax, rax
0x18007220a  jz      short loc_180072253
0x18007220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072211  mov     ebx, eax
0x180072213  test    eax, eax
0x180072215  jns     short loc_180072253
0x180072217  and     eax, 1FFF0000h
0x18007221c  movzx   edi, bx
0x18007221f  cmp     eax, 70000h
0x180072224  jz      short loc_180072228
0x180072226  mov     edi, ebx
0x180072228  mov     edx, ebx
0x18007222a  mov     rcx, rsi
0x18007222d  call    ?StopAsync@?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXJ@Z; Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(long)
0x180072232  test    edi, edi
0x180072234  jz      short loc_180072253
0x180072236  cmp     [rbp+arg_10], 0
0x18007223a  jz      short loc_180072253
0x18007223c  test    edi, edi
0x18007223e  jg      short loc_180072244
0x180072240  mov     ecx, edi
0x180072242  jmp     short loc_18007224D
0x180072244  movzx   ecx, di
0x180072247  or      ecx, 80070000h
0x18007224d  call    cs:__imp_RoFailFastWithErrorContext
0x180072253  test    r14d, r14d
0x180072256  js      short loc_18007225E
0x180072258  call    cs:__imp_RoUninitialize
0x18007225e  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 10h
0x180072265  jz      short loc_180072277
0x180072267  mov     r8d, edi
0x18007226a  lea     rdx, UMgrServiceInitResult
0x180072271  call    McTemplateU0q_EventWriteTransfer
0x180072276  nop
0x180072277  lea     rcx, [rbp+arg_18]
0x18007227b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072280  xor     eax, eax
0x180072282  add     rsp, 30h
0x180072286  pop     r14
0x180072288  pop     rdi
0x180072289  pop     rsi
0x18007228a  pop     rbx
0x18007228b  pop     rbp
0x18007228c  retn
```
