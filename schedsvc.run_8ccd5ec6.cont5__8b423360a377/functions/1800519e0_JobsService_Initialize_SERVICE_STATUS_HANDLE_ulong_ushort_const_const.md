# JobsService::Initialize(SERVICE_STATUS_HANDLE__ *,ulong,ushort const * const *)

- ea: `0x1800519e0`
- end: `0x1800521c6`
- name: `?Initialize@JobsService@@UEAAHPEAUSERVICE_STATUS_HANDLE__@@KPEBQEBG@Z`
- size: `2022`
- prototype: `__int64 __fastcall(JobsService *__hidden this, struct SERVICE_STATUS_HANDLE__ *, unsigned int, const unsigned __int16 *const *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180027910`
- `0x18002f814`
- `0x1800502c4`
- `0x1800519e0`
- `0x1800527d0`
- `0x180052888`
- `0x180054d98`
- `0x180055b44`
- `0x180056954`
- `0x18005c2f4`
- `0x18005cbec`
- `0x18005cdb8`
- `0x18005d02c`
- `0x180060d70`
- `0x180065fd4`
- `0x180067cdc`
- `0x1800693b4`
- `0x18006b718`
- `0x18006be1c`
- `0x18006dbc4`
- `0x18006e8e4`
- `0x180072fa0`
- `0x180077974`
- `0x18007ac40`

## import_xrefs

- `msvcrt!srand` at `0x180051a15`
- `msvcrt!srand` at `0x180051a15`
- `UBPM!UbpmInitialize` at `0x180052044`
- `UBPM!UbpmInitialize` at `0x180052044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051d6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051a07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051a07`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180051ad6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180051ad6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051c10`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051c58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051ca4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051d3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051c10`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051c58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051ca4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051d3d`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180051b91`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180051b91`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180051ffc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180051ffc`
- `ntdll!EtwEventRegister` at `0x180051afd`
- `ntdll!EtwEventRegister` at `0x180051afd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180051e70`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180051e70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051fd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051fd9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051e54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051e54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180051a21`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180051a21`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180051a73`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180051a73`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180051ce9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180051ce9`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180051e90`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180051e90`

## string_xrefs

- `0x180051bb8`: `CreateWaitableTimer`
- `0x180051c34`: `CreateEvent (Stop)`
- `0x180051c7c`: `CreateEvent (TimeChanged)`
- `0x180051ccb`: `CreateEvent (Shutdown)`
- `0x180051ebf`: `JobStore::CreateCommonJobStore`
- `0x180051fc8`: `DisableDownlevelCompatibilityPlugin`
- `0x180051a6c`: `%SystemRoot%\SYSTEM32\cmd.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall JobsService::Initialize(
        JobsService *this,
        struct SERVICE_STATUS_HANDLE__ *a2,
        __int64 a3,
        const unsigned __int16 *const *a4)
{
  DWORD TickCount; // eax
  __int64 result; // rax
  signed int LastError; // eax
  signed int v9; // edi
  char *v10; // rax
  EventManager *v11; // rsi
  unsigned int v12; // eax
  EventManager *v13; // rcx
  signed int v14; // edi
  Auditor *v15; // rax
  Auditor *v16; // rcx
  HANDLE WaitableTimer; // rax
  DWORD v18; // eax
  EventManager *v19; // rcx
  unsigned int v20; // eax
  void *v21; // r9
  signed int v22; // edi
  HANDLE EventW; // rax
  DWORD v24; // eax
  EventManager *v25; // rcx
  HANDLE v26; // rax
  DWORD v27; // eax
  EventManager *v28; // rcx
  DWORD v29; // eax
  EventManager *v30; // rcx
  HRESULT v31; // eax
  void *v32; // r9
  HANDLE v33; // rax
  __int64 v34; // rcx
  signed int v35; // eax
  signed int v36; // eax
  EventManager *v37; // rcx
  signed int v38; // eax
  void *v39; // r9
  signed int CommonJobStore; // eax
  EventManager *v41; // rcx
  Scheduler *v42; // rax
  Scheduler *v43; // rax
  EventTrapMap *v44; // rax
  EventTrapMap *v45; // rax
  PseudoEventTrap *v46; // rax
  Idolater *v47; // rcx
  void *v48; // r9
  PseudoEventTrap *v49; // rax
  signed int v50; // eax
  signed int v51; // eax
  void *v52; // r9
  signed int v53; // eax
  JobsService *v54; // rcx
  int started; // edi
  struct _GUID *dwOptions; // [rsp+20h] [rbp-68h]
  struct _GUID *dwOptionsa; // [rsp+20h] [rbp-68h]
  const struct _GUID *dwOptionsb; // [rsp+20h] [rbp-68h]
  const struct _GUID *samDesired; // [rsp+28h] [rbp-60h]
  const struct _GUID *samDesireda; // [rsp+28h] [rbp-60h]
  DWORD pcbData[2]; // [rsp+50h] [rbp-38h] BYREF
  HKEY v62; // [rsp+58h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-28h] BYREF
  unsigned int pvData; // [rsp+90h] [rbp+8h] BYREF

  phkResult = 0;
  v62 = 0;
  pvData = 0;
  TickCount = GetTickCount();
  srand(TickCount);
  result = (__int64)CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 32) = result;
  if ( !result )
    return result;
  *((_QWORD *)this + 25) = result;
  *((_QWORD *)this + 26) = 0;
  JobsService::DetectBootStart(this);
  ModuleTracker::Reset((struct ModuleList *)&ModuleTracker::init);
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\SYSTEM32\\cmd.exe", &CmdExe::m_buffer, 0x105u) )
  {
    v9 = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_9;
  }
  InitExtensions();
LABEL_9:
  pvData = v9;
  dword_1800C04C8 = v9;
  v10 = (char *)operator new(0x30u);
  v11 = (EventManager *)v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v10 + 8), 0, 0);
  }
  else
  {
    v11 = 0;
  }
  g_pEventManager = v11;
  v12 = EtwEventRegister(TASKSCHED, 0, 0, v11);
  v14 = v12;
  if ( !*(_QWORD *)v11 || v12 )
  {
    EventManager::LogIt(v13, L"EventRegister error", v12);
    *(_QWORD *)v11 = 0;
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
  }
  else
  {
    v14 = 0;
  }
  pvData = v14;
  dword_1800C03A8 = v14;
  v15 = (Auditor *)operator new(0x28u);
  if ( v15 )
  {
    *(_QWORD *)v15 = 0;
    *((_QWORD *)v15 + 1) = 0;
    *((_QWORD *)v15 + 2) = 0;
    *((_QWORD *)v15 + 3) = 0;
    *((_QWORD *)v15 + 4) = 0;
  }
  else
  {
    v15 = 0;
  }
  g_pAuditor = v15;
  pvData = Auditor::StartupAuditing(v16);
  dword_1800C04B8 = pvData;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 18) = WaitableTimer;
  if ( WaitableTimer )
  {
    v20 = ItSrvInitialize();
    v22 = v20;
    if ( v20 )
    {
      EventManager::EvtReport(g_pEventManager, &SCHEDULE_SERVICE_IDLE_SERVICE_INIT_ERROR, v20, v21, dwOptions);
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
    }
    dword_1800C0398 = v22;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 14) = EventW;
    if ( EventW )
    {
      v26 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 15) = v26;
      if ( v26 )
      {
        g_hShutdownEvent = CreateEventW(0, 1, 0, 0);
        if ( g_hShutdownEvent )
        {
          v31 = CoInitializeEx(0, 0);
          pvData = v31;
          dword_1800C03B8 = v31;
          if ( v31 >= 0 )
          {
            _InterlockedExchange((volatile __int32 *)&ShutdownMgr::s_sync, 1);
            _InterlockedExchange(&dword_1800C163C, 1);
            v33 = CreateEventW(0, 1, 0, 0);
            InterlockedAutoHandle::operator=(&ShutdownMgr::s_hEvent, v33);
            v34 = -1;
            if ( _InterlockedCompareExchange64((volatile signed __int64 *)&ShutdownMgr::s_hEvent, -1, -1) )
            {
              v35 = 0;
            }
            else
            {
              v35 = GetLastError();
              if ( v35 > 0 )
                v35 = (unsigned __int16)v35 | 0x80070000;
            }
            pvData = v35;
            dword_1800C03D8 = v35;
            if ( v35 >= 0 )
            {
              v36 = User::InitializeUserTable(v34);
              pvData = v36;
              dword_1800C0448 = v36;
              if ( v36 >= 0 )
              {
                v38 = CredStore::Init();
                pvData = v38;
                dword_1800C03C8 = v38;
                if ( v38 >= 0 )
                {
                  if ( RegCreateKeyExW(
                         HKEY_LOCAL_MACHINE,
                         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule",
                         0,
                         0,
                         0,
                         0x20019u,
                         0,
                         &phkResult,
                         0) )
                  {
                    return 0;
                  }
                  else
                  {
                    v62 = 0;
                    if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
                      GetServiceRegistryStateKey(a2, 1, 131103, &v62);
                    CommonJobStore = JobStore::CreateCommonJobStore(phkResult, v62);
                    pvData = CommonJobStore;
                    dword_1800C03E8 = CommonJobStore;
                    if ( CommonJobStore >= 0 )
                    {
                      v42 = (Scheduler *)operator new(0x1E0u);
                      *(_QWORD *)pcbData = v42;
                      if ( v42 )
                        v43 = Scheduler::Scheduler(v42, *((void **)this + 14), *((void **)this + 15));
                      else
                        v43 = 0;
                      g_pScheduler = v43;
                      dword_1800C0418 = 0;
                      v44 = (EventTrapMap *)operator new(0x838u);
                      if ( v44 )
                        v45 = EventTrapMap::EventTrapMap(v44);
                      else
                        v45 = 0;
                      g_pEventTrapMap = v45;
                      dword_1800C0428 = 0;
                      v46 = (PseudoEventTrap *)operator new(0xF0u);
                      *(_QWORD *)pcbData = v46;
                      if ( v46 )
                        v49 = PseudoEventTrap::PseudoEventTrap(v46);
                      else
                        v49 = 0;
                      g_pPseudoEventTrap = v49;
                      dword_1800C0438 = 0;
                      v50 = dword_1800C0398;
                      if ( (dword_1800C0398 & 0x80000000) == 0 )
                        v50 = Idolater::Init(v47);
                      dword_1800C0458 = v50;
                      if ( v50 < 0 )
                        EventManager::EvtReport(
                          g_pEventManager,
                          &SCHEDULE_SERVICE_IDLE_SERVICE_INIT_ERROR,
                          v50,
                          v48,
                          dwOptionsa);
                      pvData = 0;
                      pcbData[0] = 4;
                      if ( (RegGetValueW(
                              HKEY_LOCAL_MACHINE,
                              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule",
                              L"DisableDownlevelCompatibilityPlugin",
                              0x10u,
                              0,
                              &pvData,
                              pcbData)
                          & 0xFFFFFFFD) != 0
                        || !pvData )
                      {
                        InitializeCriticalSection(&PlugIn::s_singleton);
                        dword_1800C0468 = 0;
                        pvData = 0;
                        v51 = PlugIn::Load((PlugIn *)&PlugIn::s_singleton);
                        dword_1800C0478 = v51;
                        if ( v51 < 0 )
                          EventManager::EvtReport(g_pEventManager, &COMPAT_START_FAILED, v51, v52, dwOptionsb);
                      }
                      v53 = UbpmInitialize(a2);
                      if ( v53 > 0 )
                        v53 = (unsigned __int16)v53 | 0x80070000;
                      pvData = v53;
                      dword_1800C0498 = v53;
                      if ( v53 >= 0 )
                      {
                        pvData = JobsService::InitializeSCMEventLogNotifications(this);
                        pvData = JobsService::InitializeWPTS(v54);
                        dword_1800C04A8 = pvData;
                        started = RpcServer::StartServer((RPC_BINDING_VECTOR **)RpcServer::s_singleton);
                        if ( started < 0 )
                          RpcServer::StopServer((RPC_BINDING_VECTOR **)RpcServer::s_singleton);
                        pvData = started;
                        dword_1800C0488 = started;
                        if ( started >= 0 )
                        {
                          return 1;
                        }
                        else
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              19,
                              WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids,
                              (unsigned int)started);
                          }
                          return 0;
                        }
                      }
                      else
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            18,
                            WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids,
                            (unsigned int)v53);
                        }
                        return 0;
                      }
                    }
                    else
                    {
                      EventManager::EvtReport(
                        v41,
                        &SCHEDULE_SERVICE_START_FAILED,
                        L"JobStore::CreateCommonJobStore",
                        CommonJobStore,
                        dwOptionsa,
                        samDesireda);
                      return 0;
                    }
                  }
                }
                else
                {
                  EventManager::EvtReport(g_pEventManager, &SCHEDULE_SERVICE_CRED_STORE_INIT_ERROR, v38, v39, dwOptions);
                  return 0;
                }
              }
              else
              {
                EventManager::EvtReport(
                  v37,
                  &SCHEDULE_SERVICE_START_FAILED,
                  L"User::InitializeUserTable",
                  v36,
                  dwOptions,
                  samDesired);
                return 0;
              }
            }
            else
            {
              EventManager::EvtReport(
                (EventManager *)v34,
                &SCHEDULE_SERVICE_START_FAILED,
                L"ShutdownGuard::Initialize",
                v35,
                dwOptions,
                samDesired);
              return 0;
            }
          }
          else
          {
            EventManager::EvtReport(g_pEventManager, &SCHEDULE_SERVICE_COM_INIT_ERROR, v31, v32, dwOptions);
            return 0;
          }
        }
        else
        {
          v29 = GetLastError();
          EventManager::EvtReport(
            v30,
            &SCHEDULE_SERVICE_START_FAILED,
            L"CreateEvent (Shutdown)",
            v29,
            dwOptions,
            samDesired);
          return 0;
        }
      }
      else
      {
        v27 = GetLastError();
        EventManager::EvtReport(
          v28,
          &SCHEDULE_SERVICE_START_FAILED,
          L"CreateEvent (TimeChanged)",
          v27,
          dwOptions,
          samDesired);
        return 0;
      }
    }
    else
    {
      v24 = GetLastError();
      EventManager::EvtReport(v25, &SCHEDULE_SERVICE_START_FAILED, L"CreateEvent (Stop)", v24, dwOptions, samDesired);
      return 0;
    }
  }
  else
  {
    v18 = GetLastError();
    EventManager::EvtReport(v19, &SCHEDULE_SERVICE_START_FAILED, L"CreateWaitableTimer", v18, dwOptions, samDesired);
    return 0;
  }
}

```

## disassembly

```asm
0x1800519e0  mov     rax, rsp
0x1800519e3  mov     [rax+10h], rbx
0x1800519e7  mov     [rax+18h], rsi
0x1800519eb  push    rdi
0x1800519ec  push    r12
0x1800519ee  push    r14
0x1800519f0  sub     rsp, 70h
0x1800519f4  mov     r12, rdx
0x1800519f7  mov     r14, rcx
0x1800519fa  xor     ebx, ebx
0x1800519fc  mov     [rax-28h], rbx
0x180051a00  mov     [rax-30h], rbx
0x180051a04  mov     [rax+8], ebx
0x180051a07  call    cs:__imp_GetTickCount
0x180051a0e  nop     dword ptr [rax+rax+00h]
0x180051a13  mov     ecx, eax; Seed
0x180051a15  call    cs:__imp_srand
0x180051a1c  nop     dword ptr [rax+rax+00h]
0x180051a21  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180051a28  nop     dword ptr [rax+rax+00h]
0x180051a2d  mov     [r14+100h], rax
0x180051a34  test    rax, rax
0x180051a37  jz      loc_1800521AF
0x180051a3d  mov     [r14+0C8h], rax
0x180051a44  mov     [r14+0D0h], rbx
0x180051a4b  mov     rcx, r14; this
0x180051a4e  call    ?DetectBootStart@JobsService@@AEAAJXZ; JobsService::DetectBootStart(void)
0x180051a53  lea     rcx, ?init@ModuleTracker@@2UModuleList@@A; struct ModuleList *
0x180051a5a  call    ?Reset@ModuleTracker@@SAXAEAUModuleList@@@Z; ModuleTracker::Reset(ModuleList &)
0x180051a5f  mov     r8d, 105h; nSize
0x180051a65  lea     rdx, ?m_buffer@CmdExe@@0PAGA; lpDst
0x180051a6c  lea     rcx, Src; "%SystemRoot%\\SYSTEM32\\cmd.exe"
0x180051a73  call    cs:__imp_ExpandEnvironmentStringsW
0x180051a7a  nop     dword ptr [rax+rax+00h]
0x180051a7f  test    eax, eax
0x180051a81  jnz     short loc_180051AA4
0x180051a83  call    cs:__imp_GetLastError
0x180051a8a  nop     dword ptr [rax+rax+00h]
0x180051a8f  mov     edi, eax
0x180051a91  test    eax, eax
0x180051a93  jle     short loc_180051A9E
0x180051a95  movzx   edi, ax
0x180051a98  or      edi, 80070000h
0x180051a9e  test    edi, edi
0x180051aa0  js      short loc_180051AAB
0x180051aa2  jmp     short loc_180051AA6
0x180051aa4  mov     edi, ebx
0x180051aa6  call    ?InitExtensions@@YAXXZ; InitExtensions(void)
0x180051aab  mov     [rsp+88h+pvData], edi
0x180051ab2  mov     cs:dword_1800C04C8, edi
0x180051ab8  mov     ecx, 30h ; '0'; dwBytes
0x180051abd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051ac2  mov     rsi, rax
0x180051ac5  test    rax, rax
0x180051ac8  jz      short loc_180051AE4
0x180051aca  mov     [rax], rbx
0x180051acd  lea     rcx, [rax+8]; lpCriticalSection
0x180051ad1  xor     r8d, r8d; Flags
0x180051ad4  xor     edx, edx; dwSpinCount
0x180051ad6  call    cs:__imp_InitializeCriticalSectionEx
0x180051add  nop     dword ptr [rax+rax+00h]
0x180051ae2  jmp     short loc_180051AE7
0x180051ae4  mov     rsi, rbx
0x180051ae7  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, rsi; EventManager * g_pEventManager
0x180051aee  mov     r9, rsi
0x180051af1  xor     r8d, r8d
0x180051af4  xor     edx, edx
0x180051af6  lea     rcx, TASKSCHED
0x180051afd  call    cs:__imp_EtwEventRegister
0x180051b04  nop     dword ptr [rax+rax+00h]
0x180051b09  mov     edi, eax
0x180051b0b  cmp     [rsi], rbx
0x180051b0e  jz      short loc_180051B18
0x180051b10  test    eax, eax
0x180051b12  jnz     short loc_180051B18
0x180051b14  mov     edi, ebx
0x180051b16  jmp     short loc_180051B37
0x180051b18  mov     r8d, edi; unsigned int
0x180051b1b  lea     rdx, aEventregisterE; "EventRegister error"
0x180051b22  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180051b27  mov     [rsi], rbx
0x180051b2a  test    edi, edi
0x180051b2c  jle     short loc_180051B37
0x180051b2e  movzx   edi, di
0x180051b31  or      edi, 80070000h
0x180051b37  mov     [rsp+88h+pvData], edi
0x180051b3e  mov     cs:dword_1800C03A8, edi
0x180051b44  mov     ecx, 28h ; '('; dwBytes
0x180051b49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051b4e  test    rax, rax
0x180051b51  jz      short loc_180051B68
0x180051b53  mov     [rax], rbx
0x180051b56  mov     [rax+8], rbx
0x180051b5a  mov     [rax+10h], rbx
0x180051b5e  mov     [rax+18h], rbx
0x180051b62  mov     [rax+20h], rbx
0x180051b66  jmp     short loc_180051B6B
0x180051b68  mov     rax, rbx
0x180051b6b  mov     cs:?g_pAuditor@@3PEAVAuditor@@EA, rax; Auditor * g_pAuditor
0x180051b72  call    ?StartupAuditing@Auditor@@QEAAKXZ; Auditor::StartupAuditing(void)
0x180051b77  mov     [rsp+88h+pvData], eax
0x180051b7e  mov     cs:dword_1800C04B8, eax
0x180051b84  mov     r9d, 1F0003h; dwDesiredAccess
0x180051b8a  xor     r8d, r8d; dwFlags
0x180051b8d  xor     edx, edx; lpTimerName
0x180051b8f  xor     ecx, ecx; lpTimerAttributes
0x180051b91  call    cs:__imp_CreateWaitableTimerExW
0x180051b98  nop     dword ptr [rax+rax+00h]
0x180051b9d  mov     [r14+90h], rax
0x180051ba4  test    rax, rax
0x180051ba7  jnz     short loc_180051BD2
0x180051ba9  call    cs:__imp_GetLastError
0x180051bb0  nop     dword ptr [rax+rax+00h]
0x180051bb5  mov     r9d, eax; unsigned int
0x180051bb8  lea     r8, aCreatewaitable; "CreateWaitableTimer"
0x180051bbf  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051bc6  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051bcb  xor     eax, eax
0x180051bcd  jmp     loc_1800521AF
0x180051bd2  call    ItSrvInitialize
0x180051bd7  mov     edi, eax
0x180051bd9  test    eax, eax
0x180051bdb  jz      short loc_180051C00
0x180051bdd  mov     r8d, eax; unsigned int
0x180051be0  lea     rdx, SCHEDULE_SERVICE_IDLE_SERVICE_INIT_ERROR; struct _EVENT_DESCRIPTOR *
0x180051be7  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180051bee  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x180051bf3  test    edi, edi
0x180051bf5  jle     short loc_180051C00
0x180051bf7  movzx   edi, di
0x180051bfa  or      edi, 80070000h
0x180051c00  mov     cs:dword_1800C0398, edi
0x180051c06  xor     r9d, r9d; lpName
0x180051c09  xor     r8d, r8d; bInitialState
0x180051c0c  xor     edx, edx; bManualReset
0x180051c0e  xor     ecx, ecx; lpEventAttributes
0x180051c10  call    cs:__imp_CreateEventW
0x180051c17  nop     dword ptr [rax+rax+00h]
0x180051c1c  mov     [r14+70h], rax
0x180051c20  test    rax, rax
0x180051c23  jnz     short loc_180051C4E
0x180051c25  call    cs:__imp_GetLastError
0x180051c2c  nop     dword ptr [rax+rax+00h]
0x180051c31  mov     r9d, eax; unsigned int
0x180051c34  lea     r8, aCreateeventSto; "CreateEvent (Stop)"
0x180051c3b  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051c42  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051c47  xor     eax, eax
0x180051c49  jmp     loc_1800521AF
0x180051c4e  xor     r9d, r9d; lpName
0x180051c51  xor     r8d, r8d; bInitialState
0x180051c54  xor     edx, edx; bManualReset
0x180051c56  xor     ecx, ecx; lpEventAttributes
0x180051c58  call    cs:__imp_CreateEventW
0x180051c5f  nop     dword ptr [rax+rax+00h]
0x180051c64  mov     [r14+78h], rax
0x180051c68  test    rax, rax
0x180051c6b  jnz     short loc_180051C96
0x180051c6d  call    cs:__imp_GetLastError
0x180051c74  nop     dword ptr [rax+rax+00h]
0x180051c79  mov     r9d, eax; unsigned int
0x180051c7c  lea     r8, aCreateeventTim; "CreateEvent (TimeChanged)"
0x180051c83  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051c8a  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051c8f  xor     eax, eax
0x180051c91  jmp     loc_1800521AF
0x180051c96  xor     r9d, r9d; lpName
0x180051c99  xor     r8d, r8d; bInitialState
0x180051c9c  lea     esi, [r9+1]
0x180051ca0  mov     edx, esi; bManualReset
0x180051ca2  xor     ecx, ecx; lpEventAttributes
0x180051ca4  call    cs:__imp_CreateEventW
0x180051cab  nop     dword ptr [rax+rax+00h]
0x180051cb0  mov     cs:?g_hShutdownEvent@@3PEAXEA, rax; void * g_hShutdownEvent
0x180051cb7  test    rax, rax
0x180051cba  jnz     short loc_180051CE5
0x180051cbc  call    cs:__imp_GetLastError
0x180051cc3  nop     dword ptr [rax+rax+00h]
0x180051cc8  mov     r9d, eax; unsigned int
0x180051ccb  lea     r8, aCreateeventShu; "CreateEvent (Shutdown)"
0x180051cd2  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051cd9  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051cde  xor     eax, eax
0x180051ce0  jmp     loc_1800521AF
0x180051ce5  xor     edx, edx; dwCoInit
0x180051ce7  xor     ecx, ecx; pvReserved
0x180051ce9  call    cs:__imp_CoInitializeEx
0x180051cf0  nop     dword ptr [rax+rax+00h]
0x180051cf5  mov     [rsp+88h+pvData], eax
0x180051cfc  mov     cs:dword_1800C03B8, eax
0x180051d02  test    eax, eax
0x180051d04  jns     short loc_180051D23
0x180051d06  mov     r8d, eax; unsigned int
0x180051d09  lea     rdx, SCHEDULE_SERVICE_COM_INIT_ERROR; struct _EVENT_DESCRIPTOR *
0x180051d10  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180051d17  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x180051d1c  xor     eax, eax
0x180051d1e  jmp     loc_1800521AF
0x180051d23  mov     eax, esi
0x180051d25  xchg    eax, cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x180051d2b  mov     ecx, esi
0x180051d2d  xchg    ecx, cs:dword_1800C163C
0x180051d33  xor     r9d, r9d; lpName
0x180051d36  xor     r8d, r8d; bInitialState
0x180051d39  mov     edx, esi; bManualReset
0x180051d3b  xor     ecx, ecx; lpEventAttributes
0x180051d3d  call    cs:__imp_CreateEventW
0x180051d44  nop     dword ptr [rax+rax+00h]
0x180051d49  mov     rdx, rax
0x180051d4c  lea     rcx, ?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x180051d53  call    ??4InterlockedAutoHandle@@QEAAAEAV0@PEAX@Z; InterlockedAutoHandle::operator=(void *)
0x180051d58  or      rcx, 0FFFFFFFFFFFFFFFFh; int
0x180051d5c  mov     rax, rcx
0x180051d5f  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x180051d68  test    rax, rax
0x180051d6b  jnz     short loc_180051D87
0x180051d6d  call    cs:__imp_GetLastError
0x180051d74  nop     dword ptr [rax+rax+00h]
0x180051d79  test    eax, eax
0x180051d7b  jle     short loc_180051D89
0x180051d7d  movzx   eax, ax
0x180051d80  or      eax, 80070000h
0x180051d85  jmp     short loc_180051D89
0x180051d87  mov     eax, ebx
0x180051d89  mov     [rsp+88h+pvData], eax
0x180051d90  mov     cs:dword_1800C03D8, eax
0x180051d96  test    eax, eax
0x180051d98  jns     short loc_180051DB7
0x180051d9a  mov     r9d, eax; unsigned int
0x180051d9d  lea     r8, aShutdownguardI; "ShutdownGuard::Initialize"
0x180051da4  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051dab  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051db0  xor     eax, eax
0x180051db2  jmp     loc_1800521AF
0x180051db7  call    ?InitializeUserTable@User@@SAJH@Z; User::InitializeUserTable(int)
0x180051dbc  mov     [rsp+88h+pvData], eax
0x180051dc3  mov     cs:dword_1800C0448, eax
0x180051dc9  test    eax, eax
0x180051dcb  jns     short loc_180051DEA
0x180051dcd  mov     r9d, eax; unsigned int
0x180051dd0  lea     r8, aUserInitialize; "User::InitializeUserTable"
0x180051dd7  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051dde  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051de3  xor     eax, eax
0x180051de5  jmp     loc_1800521AF
0x180051dea  call    ?Init@CredStore@@SAJXZ; CredStore::Init(void)
0x180051def  mov     [rsp+88h+pvData], eax
0x180051df6  mov     cs:dword_1800C03C8, eax
0x180051dfc  test    eax, eax
0x180051dfe  jns     short loc_180051E1D
0x180051e00  mov     r8d, eax; unsigned int
0x180051e03  lea     rdx, SCHEDULE_SERVICE_CRED_STORE_INIT_ERROR; struct _EVENT_DESCRIPTOR *
0x180051e0a  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180051e11  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x180051e16  xor     eax, eax
0x180051e18  jmp     loc_1800521AF
0x180051e1d  mov     [rsp+88h+lpdwDisposition], rbx; lpdwDisposition
0x180051e22  lea     rax, [rsp+88h+var_28]
0x180051e27  mov     [rsp+88h+phkResult], rax; phkResult
0x180051e2c  mov     [rsp+88h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180051e31  mov     [rsp+88h+samDesired], 20019h; struct _GUID *
0x180051e39  mov     [rsp+88h+dwOptions], ebx; struct _GUID *
0x180051e3d  xor     r9d, r9d; lpClass
0x180051e40  xor     r8d, r8d; Reserved
0x180051e43  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180051e4a  mov     rdi, 0FFFFFFFF80000002h
0x180051e51  mov     rcx, rdi; hKey
0x180051e54  call    cs:__imp_RegCreateKeyExW
0x180051e5b  nop     dword ptr [rax+rax+00h]
0x180051e60  test    eax, eax
0x180051e62  jz      short loc_180051E6B
0x180051e64  xor     eax, eax
0x180051e66  jmp     loc_1800521AF
0x180051e6b  mov     [rsp+88h+var_30], rbx
0x180051e70  call    cs:__imp_RtlIsStateSeparationEnabled
0x180051e77  nop     dword ptr [rax+rax+00h]
0x180051e7c  test    al, al
0x180051e7e  jz      short loc_180051E9C
0x180051e80  lea     r9, [rsp+88h+var_30]
0x180051e85  mov     r8d, 2001Fh
0x180051e8b  mov     edx, esi
0x180051e8d  mov     rcx, r12
0x180051e90  call    cs:__imp_GetServiceRegistryStateKey
0x180051e97  nop     dword ptr [rax+rax+00h]
0x180051e9c  mov     rdx, [rsp+88h+var_30]; HKEY
0x180051ea1  mov     rcx, [rsp+88h+var_28]; HKEY
0x180051ea6  call    ?CreateCommonJobStore@JobStore@@SAJPEAUHKEY__@@0@Z; JobStore::CreateCommonJobStore(HKEY__ *,HKEY__ *)
0x180051eab  mov     [rsp+88h+pvData], eax
0x180051eb2  mov     cs:dword_1800C03E8, eax
0x180051eb8  test    eax, eax
0x180051eba  jns     short loc_180051ED9
0x180051ebc  mov     r9d, eax; unsigned int
0x180051ebf  lea     r8, aJobstoreCreate; "JobStore::CreateCommonJobStore"
0x180051ec6  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180051ecd  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180051ed2  xor     eax, eax
0x180051ed4  jmp     loc_1800521AF
0x180051ed9  mov     ecx, 1E0h; dwBytes
0x180051ede  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051ee3  mov     qword ptr [rsp+88h+pcbData], rax
  ... truncated ...
```
