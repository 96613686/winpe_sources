# JobsService::Initialize(SERVICE_STATUS_HANDLE__ *,ulong,ushort const * const *)

- ea: `0x18004f190`
- end: `0x18004f903`
- name: `?Initialize@JobsService@@UEAAHPEAUSERVICE_STATUS_HANDLE__@@KPEBQEBG@Z`
- size: `1907`
- prototype: `__int64 __fastcall(JobsService *this, struct SERVICE_STATUS_HANDLE__ *, __int64, const unsigned __int16 *const *)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180030f80`
- `0x180039b6c`
- `0x18004def0`
- `0x18004f190`
- `0x18004fea8`
- `0x18004ff54`
- `0x1800526b8`
- `0x18005331c`
- `0x180054084`
- `0x1800599ac`
- `0x18005a24c`
- `0x18005a3dc`
- `0x18005dfc8`
- `0x180062ff4`
- `0x180064c10`
- `0x180066228`
- `0x180068398`
- `0x180068a60`
- `0x18006a738`
- `0x18006b3ac`
- `0x18006f7c0`
- `0x180073c94`
- `0x180076c20`

## import_xrefs

- `msvcrt!srand` at `0x18004f1bf`
- `msvcrt!srand` at `0x18004f1bf`
- `UBPM!UbpmInitialize` at `0x18004f787`
- `UBPM!UbpmInitialize` at `0x18004f787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f22f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f22f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004f1b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004f1b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004f27c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004f27c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f39e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f3da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f418`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f4a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f39e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f3da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f418`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f4a7`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18004f32b`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18004f32b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004f745`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004f745`
- `ntdll!EtwEventRegister` at `0x18004f29d`
- `ntdll!EtwEventRegister` at `0x18004f29d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18004f5c8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18004f5c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f728`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f728`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f5b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f5b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004f1c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004f1c5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004f225`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004f225`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004f451`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004f451`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18004f5e5`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18004f5e5`

## string_xrefs

- `0x18004f346`: `CreateWaitableTimer`
- `0x18004f3b6`: `CreateEvent (Stop)`
- `0x18004f3f2`: `CreateEvent (TimeChanged)`
- `0x18004f433`: `CreateEvent (Shutdown)`
- `0x18004f60e`: `JobStore::CreateCommonJobStore`
- `0x18004f717`: `DisableDownlevelCompatibilityPlugin`
- `0x18004f21e`: `%SystemRoot%\SYSTEM32\cmd.exe`

## pseudocode

```c
__int64 __fastcall JobsService::Initialize(
        JobsService *this,
        struct SERVICE_STATUS_HANDLE__ *a2,
        __int64 a3,
        const unsigned __int16 *const *a4)
{
  DWORD TickCount; // eax
  __int64 result; // rax
  unsigned __int64 i; // rcx
  signed int LastError; // eax
  signed int v10; // edi
  char *v11; // rax
  EventManager *v12; // rsi
  unsigned int v13; // eax
  EventManager *v14; // rcx
  signed int v15; // edi
  Auditor *v16; // rax
  Auditor *v17; // rcx
  HANDLE WaitableTimer; // rax
  DWORD v19; // eax
  EventManager *v20; // rcx
  unsigned int v21; // eax
  void *v22; // r9
  signed int v23; // edi
  HANDLE EventW; // rax
  DWORD v25; // eax
  EventManager *v26; // rcx
  HANDLE v27; // rax
  DWORD v28; // eax
  EventManager *v29; // rcx
  DWORD v30; // eax
  EventManager *v31; // rcx
  HRESULT v32; // eax
  void *v33; // r9
  HANDLE v34; // rax
  __int64 v35; // rcx
  signed int v36; // eax
  signed int v37; // eax
  EventManager *v38; // rcx
  signed int v39; // eax
  void *v40; // r9
  signed int CommonJobStore; // eax
  EventManager *v42; // rcx
  Scheduler *v43; // rax
  Scheduler *v44; // rax
  EventTrapMap *v45; // rax
  EventTrapMap *v46; // rax
  PseudoEventTrap *v47; // rax
  Idolater *v48; // rcx
  void *v49; // r9
  PseudoEventTrap *v50; // rax
  signed int v51; // eax
  signed int v52; // eax
  void *v53; // r9
  signed int v54; // eax
  JobsService *v55; // rcx
  int started; // edi
  struct _GUID *dwOptions; // [rsp+20h] [rbp-68h]
  struct _GUID *dwOptionsa; // [rsp+20h] [rbp-68h]
  const struct _GUID *dwOptionsb; // [rsp+20h] [rbp-68h]
  const struct _GUID *samDesired; // [rsp+28h] [rbp-60h]
  const struct _GUID *samDesireda; // [rsp+28h] [rbp-60h]
  DWORD pcbData[2]; // [rsp+50h] [rbp-38h] BYREF
  HKEY v63; // [rsp+58h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-28h] BYREF
  unsigned int pvData; // [rsp+90h] [rbp+8h] BYREF

  phkResult = 0;
  v63 = 0;
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
  for ( i = 0; i < 0x14; ++i )
    *(&dword_1800BC398 + 4 * i) = -1;
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\SYSTEM32\\cmd.exe", &CmdExe::m_buffer, 0x105u) )
  {
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_11;
  }
  InitExtensions();
LABEL_11:
  pvData = v10;
  dword_1800BC4C8 = v10;
  v11 = (char *)operator new(0x30u);
  v12 = (EventManager *)v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v11 + 8), 0, 0);
  }
  else
  {
    v12 = 0;
  }
  g_pEventManager = v12;
  v13 = EtwEventRegister(TASKSCHED, 0, 0, v12);
  v15 = v13;
  if ( !*(_QWORD *)v12 || v13 )
  {
    EventManager::LogIt(v14, L"EventRegister error", v13);
    *(_QWORD *)v12 = 0;
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
  }
  else
  {
    v15 = 0;
  }
  pvData = v15;
  dword_1800BC3A8 = v15;
  v16 = (Auditor *)operator new(0x28u);
  if ( v16 )
  {
    *(_QWORD *)v16 = 0;
    *((_QWORD *)v16 + 1) = 0;
    *((_QWORD *)v16 + 2) = 0;
    *((_QWORD *)v16 + 3) = 0;
    *((_QWORD *)v16 + 4) = 0;
  }
  else
  {
    v16 = 0;
  }
  g_pAuditor = v16;
  pvData = Auditor::StartupAuditing(v17);
  dword_1800BC4B8 = pvData;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 18) = WaitableTimer;
  if ( WaitableTimer )
  {
    v21 = ItSrvInitialize();
    v23 = v21;
    if ( v21 )
    {
      EventManager::EvtReport(g_pEventManager, &SCHEDULE_SERVICE_IDLE_SERVICE_INIT_ERROR, v21, v22, dwOptions);
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
    }
    dword_1800BC398 = v23;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 14) = EventW;
    if ( EventW )
    {
      v27 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 15) = v27;
      if ( v27 )
      {
        g_hShutdownEvent = CreateEventW(0, 1, 0, 0);
        if ( g_hShutdownEvent )
        {
          v32 = CoInitializeEx(0, 0);
          pvData = v32;
          dword_1800BC3B8 = v32;
          if ( v32 >= 0 )
          {
            _InterlockedExchange((volatile __int32 *)&ShutdownMgr::s_sync, 1);
            _InterlockedExchange(&dword_1800BD53C, 1);
            v34 = CreateEventW(0, 1, 0, 0);
            InterlockedAutoHandle::operator=(&ShutdownMgr::s_hEvent, v34);
            v35 = -1;
            if ( _InterlockedCompareExchange64((volatile signed __int64 *)&ShutdownMgr::s_hEvent, -1, -1) )
            {
              v36 = 0;
            }
            else
            {
              v36 = GetLastError();
              if ( v36 > 0 )
                v36 = (unsigned __int16)v36 | 0x80070000;
            }
            pvData = v36;
            dword_1800BC3D8 = v36;
            if ( v36 >= 0 )
            {
              v37 = User::InitializeUserTable(v35);
              pvData = v37;
              dword_1800BC448 = v37;
              if ( v37 >= 0 )
              {
                v39 = CredStore::Init();
                pvData = v39;
                dword_1800BC3C8 = v39;
                if ( v39 >= 0 )
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
                    v63 = 0;
                    if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
                      GetServiceRegistryStateKey(a2, 1, 131103, &v63);
                    CommonJobStore = JobStore::CreateCommonJobStore(phkResult, v63);
                    pvData = CommonJobStore;
                    dword_1800BC3E8 = CommonJobStore;
                    if ( CommonJobStore >= 0 )
                    {
                      v43 = (Scheduler *)operator new(0x1E0u);
                      *(_QWORD *)pcbData = v43;
                      if ( v43 )
                        v44 = Scheduler::Scheduler(v43, *((void **)this + 14), *((void **)this + 15));
                      else
                        v44 = 0;
                      g_pScheduler = v44;
                      dword_1800BC418 = 0;
                      v45 = (EventTrapMap *)operator new(0x838u);
                      if ( v45 )
                        v46 = EventTrapMap::EventTrapMap(v45);
                      else
                        v46 = 0;
                      g_pEventTrapMap = v46;
                      dword_1800BC428 = 0;
                      v47 = (PseudoEventTrap *)operator new(0xF0u);
                      *(_QWORD *)pcbData = v47;
                      if ( v47 )
                        v50 = PseudoEventTrap::PseudoEventTrap(v47);
                      else
                        v50 = 0;
                      g_pPseudoEventTrap = v50;
                      dword_1800BC438 = 0;
                      v51 = dword_1800BC398;
                      if ( (dword_1800BC398 & 0x80000000) == 0 )
                        v51 = Idolater::Init(v48);
                      dword_1800BC458 = v51;
                      if ( v51 < 0 )
                        EventManager::EvtReport(
                          g_pEventManager,
                          &SCHEDULE_SERVICE_IDLE_SERVICE_INIT_ERROR,
                          v51,
                          v49,
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
                        dword_1800BC468 = 0;
                        pvData = 0;
                        v52 = PlugIn::Load(&PlugIn::s_singleton);
                        dword_1800BC478 = v52;
                        if ( v52 < 0 )
                          EventManager::EvtReport(g_pEventManager, &COMPAT_START_FAILED, v52, v53, dwOptionsb);
                      }
                      v54 = UbpmInitialize(a2);
                      if ( v54 > 0 )
                        v54 = (unsigned __int16)v54 | 0x80070000;
                      pvData = v54;
                      dword_1800BC498 = v54;
                      if ( v54 >= 0 )
                      {
                        pvData = JobsService::InitializeSCMEventLogNotifications(this);
                        pvData = JobsService::InitializeWPTS(v55);
                        dword_1800BC4A8 = pvData;
                        started = RpcServer::StartServer((RPC_BINDING_VECTOR **)RpcServer::s_singleton);
                        if ( started < 0 )
                          RpcServer::StopServer((RPC_BINDING_VECTOR **)RpcServer::s_singleton);
                        pvData = started;
                        dword_1800BC488 = started;
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
                            (unsigned int)v54);
                        }
                        return 0;
                      }
                    }
                    else
                    {
                      EventManager::EvtReport(
                        v42,
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
                  EventManager::EvtReport(g_pEventManager, &SCHEDULE_SERVICE_CRED_STORE_INIT_ERROR, v39, v40, dwOptions);
                  return 0;
                }
              }
              else
              {
                EventManager::EvtReport(
                  v38,
                  &SCHEDULE_SERVICE_START_FAILED,
                  L"User::InitializeUserTable",
                  v37,
                  dwOptions,
                  samDesired);
                return 0;
              }
            }
            else
            {
              EventManager::EvtReport(
                (EventManager *)v35,
                &SCHEDULE_SERVICE_START_FAILED,
                L"ShutdownGuard::Initialize",
                v36,
                dwOptions,
                samDesired);
              return 0;
            }
          }
          else
          {
            EventManager::EvtReport(g_pEventManager, &SCHEDULE_SERVICE_COM_INIT_ERROR, v32, v33, dwOptions);
            return 0;
          }
        }
        else
        {
          v30 = GetLastError();
          EventManager::EvtReport(
            v31,
            &SCHEDULE_SERVICE_START_FAILED,
            L"CreateEvent (Shutdown)",
            v30,
            dwOptions,
            samDesired);
          return 0;
        }
      }
      else
      {
        v28 = GetLastError();
        EventManager::EvtReport(
          v29,
          &SCHEDULE_SERVICE_START_FAILED,
          L"CreateEvent (TimeChanged)",
          v28,
          dwOptions,
          samDesired);
        return 0;
      }
    }
    else
    {
      v25 = GetLastError();
      EventManager::EvtReport(v26, &SCHEDULE_SERVICE_START_FAILED, L"CreateEvent (Stop)", v25, dwOptions, samDesired);
      return 0;
    }
  }
  else
  {
    v19 = GetLastError();
    EventManager::EvtReport(v20, &SCHEDULE_SERVICE_START_FAILED, L"CreateWaitableTimer", v19, dwOptions, samDesired);
    return 0;
  }
}

```

## disassembly

```asm
0x18004f190  mov     rax, rsp
0x18004f193  mov     [rax+10h], rbx
0x18004f197  mov     [rax+18h], rsi
0x18004f19b  push    rdi
0x18004f19c  push    r13
0x18004f19e  push    r14
0x18004f1a0  sub     rsp, 70h
0x18004f1a4  mov     r13, rdx
0x18004f1a7  mov     r14, rcx
0x18004f1aa  xor     ebx, ebx
0x18004f1ac  mov     [rax-28h], rbx
0x18004f1b0  mov     [rax-30h], rbx
0x18004f1b4  mov     [rax+8], ebx
0x18004f1b7  call    cs:__imp_GetTickCount
0x18004f1bd  mov     ecx, eax; Seed
0x18004f1bf  call    cs:__imp_srand
0x18004f1c5  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18004f1cb  mov     [r14+100h], rax
0x18004f1d2  test    rax, rax
0x18004f1d5  jz      loc_18004F8EC
0x18004f1db  mov     [r14+0C8h], rax
0x18004f1e2  mov     [r14+0D0h], rbx
0x18004f1e9  mov     rcx, r14; this
0x18004f1ec  call    ?DetectBootStart@JobsService@@AEAAJXZ; JobsService::DetectBootStart(void)
0x18004f1f1  mov     rcx, rbx
0x18004f1f4  mov     rax, rcx
0x18004f1f7  add     rax, rax
0x18004f1fa  lea     rdx, dword_1800BC398
0x18004f201  mov     dword ptr [rdx+rax*8], 0FFFFFFFFh
0x18004f208  inc     rcx
0x18004f20b  cmp     rcx, 14h
0x18004f20f  jb      short loc_18004F1F4
0x18004f211  mov     r8d, 105h; nSize
0x18004f217  lea     rdx, ?m_buffer@CmdExe@@0PAGA; lpDst
0x18004f21e  lea     rcx, Src; "%SystemRoot%\\SYSTEM32\\cmd.exe"
0x18004f225  call    cs:__imp_ExpandEnvironmentStringsW
0x18004f22b  test    eax, eax
0x18004f22d  jnz     short loc_18004F24A
0x18004f22f  call    cs:__imp_GetLastError
0x18004f235  mov     edi, eax
0x18004f237  test    eax, eax
0x18004f239  jle     short loc_18004F244
0x18004f23b  movzx   edi, ax
0x18004f23e  or      edi, 80070000h
0x18004f244  test    edi, edi
0x18004f246  js      short loc_18004F251
0x18004f248  jmp     short loc_18004F24C
0x18004f24a  mov     edi, ebx
0x18004f24c  call    ?InitExtensions@@YAXXZ; InitExtensions(void)
0x18004f251  mov     [rsp+88h+pvData], edi
0x18004f258  mov     cs:dword_1800BC4C8, edi
0x18004f25e  mov     ecx, 30h ; '0'; dwBytes
0x18004f263  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f268  mov     rsi, rax
0x18004f26b  test    rax, rax
0x18004f26e  jz      short loc_18004F284
0x18004f270  mov     [rax], rbx
0x18004f273  lea     rcx, [rax+8]; lpCriticalSection
0x18004f277  xor     r8d, r8d; Flags
0x18004f27a  xor     edx, edx; dwSpinCount
0x18004f27c  call    cs:__imp_InitializeCriticalSectionEx
0x18004f282  jmp     short loc_18004F287
0x18004f284  mov     rsi, rbx
0x18004f287  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, rsi; EventManager * g_pEventManager
0x18004f28e  mov     r9, rsi
0x18004f291  xor     r8d, r8d
0x18004f294  xor     edx, edx
0x18004f296  lea     rcx, TASKSCHED
0x18004f29d  call    cs:__imp_EtwEventRegister
0x18004f2a3  mov     edi, eax
0x18004f2a5  cmp     [rsi], rbx
0x18004f2a8  jz      short loc_18004F2B2
0x18004f2aa  test    eax, eax
0x18004f2ac  jnz     short loc_18004F2B2
0x18004f2ae  mov     edi, ebx
0x18004f2b0  jmp     short loc_18004F2D1
0x18004f2b2  mov     r8d, edi; unsigned int
0x18004f2b5  lea     rdx, aEventregisterE; "EventRegister error"
0x18004f2bc  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004f2c1  mov     [rsi], rbx
0x18004f2c4  test    edi, edi
0x18004f2c6  jle     short loc_18004F2D1
0x18004f2c8  movzx   edi, di
0x18004f2cb  or      edi, 80070000h
0x18004f2d1  mov     [rsp+88h+pvData], edi
0x18004f2d8  mov     cs:dword_1800BC3A8, edi
0x18004f2de  mov     ecx, 28h ; '('; dwBytes
0x18004f2e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f2e8  test    rax, rax
0x18004f2eb  jz      short loc_18004F302
0x18004f2ed  mov     [rax], rbx
0x18004f2f0  mov     [rax+8], rbx
0x18004f2f4  mov     [rax+10h], rbx
0x18004f2f8  mov     [rax+18h], rbx
0x18004f2fc  mov     [rax+20h], rbx
0x18004f300  jmp     short loc_18004F305
0x18004f302  mov     rax, rbx
0x18004f305  mov     cs:?g_pAuditor@@3PEAVAuditor@@EA, rax; Auditor * g_pAuditor
0x18004f30c  call    ?StartupAuditing@Auditor@@QEAAKXZ; Auditor::StartupAuditing(void)
0x18004f311  mov     [rsp+88h+pvData], eax
0x18004f318  mov     cs:dword_1800BC4B8, eax
0x18004f31e  mov     r9d, 1F0003h; dwDesiredAccess
0x18004f324  xor     r8d, r8d; dwFlags
0x18004f327  xor     edx, edx; lpTimerName
0x18004f329  xor     ecx, ecx; lpTimerAttributes
0x18004f32b  call    cs:__imp_CreateWaitableTimerExW
0x18004f331  mov     [r14+90h], rax
0x18004f338  test    rax, rax
0x18004f33b  jnz     short loc_18004F360
0x18004f33d  call    cs:__imp_GetLastError
0x18004f343  mov     r9d, eax; unsigned int
0x18004f346  lea     r8, aCreatewaitable; "CreateWaitableTimer"
0x18004f34d  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f354  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f359  xor     eax, eax
0x18004f35b  jmp     loc_18004F8EC
0x18004f360  call    ItSrvInitialize
0x18004f365  mov     edi, eax
0x18004f367  test    eax, eax
0x18004f369  jz      short loc_18004F38E
0x18004f36b  mov     r8d, eax; unsigned int
0x18004f36e  lea     rdx, SCHEDULE_SERVICE_IDLE_SERVICE_INIT_ERROR; struct _EVENT_DESCRIPTOR *
0x18004f375  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x18004f37c  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18004f381  test    edi, edi
0x18004f383  jle     short loc_18004F38E
0x18004f385  movzx   edi, di
0x18004f388  or      edi, 80070000h
0x18004f38e  mov     cs:dword_1800BC398, edi
0x18004f394  xor     r9d, r9d; lpName
0x18004f397  xor     r8d, r8d; bInitialState
0x18004f39a  xor     edx, edx; bManualReset
0x18004f39c  xor     ecx, ecx; lpEventAttributes
0x18004f39e  call    cs:__imp_CreateEventW
0x18004f3a4  mov     [r14+70h], rax
0x18004f3a8  test    rax, rax
0x18004f3ab  jnz     short loc_18004F3D0
0x18004f3ad  call    cs:__imp_GetLastError
0x18004f3b3  mov     r9d, eax; unsigned int
0x18004f3b6  lea     r8, aCreateeventSto; "CreateEvent (Stop)"
0x18004f3bd  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f3c4  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f3c9  xor     eax, eax
0x18004f3cb  jmp     loc_18004F8EC
0x18004f3d0  xor     r9d, r9d; lpName
0x18004f3d3  xor     r8d, r8d; bInitialState
0x18004f3d6  xor     edx, edx; bManualReset
0x18004f3d8  xor     ecx, ecx; lpEventAttributes
0x18004f3da  call    cs:__imp_CreateEventW
0x18004f3e0  mov     [r14+78h], rax
0x18004f3e4  test    rax, rax
0x18004f3e7  jnz     short loc_18004F40C
0x18004f3e9  call    cs:__imp_GetLastError
0x18004f3ef  mov     r9d, eax; unsigned int
0x18004f3f2  lea     r8, aCreateeventTim; "CreateEvent (TimeChanged)"
0x18004f3f9  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f400  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f405  xor     eax, eax
0x18004f407  jmp     loc_18004F8EC
0x18004f40c  xor     r9d, r9d; lpName
0x18004f40f  xor     r8d, r8d; bInitialState
0x18004f412  lea     edx, [r9+1]; bManualReset
0x18004f416  xor     ecx, ecx; lpEventAttributes
0x18004f418  call    cs:__imp_CreateEventW
0x18004f41e  mov     cs:?g_hShutdownEvent@@3PEAXEA, rax; void * g_hShutdownEvent
0x18004f425  test    rax, rax
0x18004f428  jnz     short loc_18004F44D
0x18004f42a  call    cs:__imp_GetLastError
0x18004f430  mov     r9d, eax; unsigned int
0x18004f433  lea     r8, aCreateeventShu; "CreateEvent (Shutdown)"
0x18004f43a  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f441  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f446  xor     eax, eax
0x18004f448  jmp     loc_18004F8EC
0x18004f44d  xor     edx, edx; dwCoInit
0x18004f44f  xor     ecx, ecx; pvReserved
0x18004f451  call    cs:__imp_CoInitializeEx
0x18004f457  mov     [rsp+88h+pvData], eax
0x18004f45e  mov     cs:dword_1800BC3B8, eax
0x18004f464  test    eax, eax
0x18004f466  jns     short loc_18004F485
0x18004f468  mov     r8d, eax; unsigned int
0x18004f46b  lea     rdx, SCHEDULE_SERVICE_COM_INIT_ERROR; struct _EVENT_DESCRIPTOR *
0x18004f472  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x18004f479  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18004f47e  xor     eax, eax
0x18004f480  jmp     loc_18004F8EC
0x18004f485  mov     eax, 1
0x18004f48a  xchg    eax, cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18004f490  mov     ecx, 1
0x18004f495  xchg    ecx, cs:dword_1800BD53C
0x18004f49b  xor     r9d, r9d; lpName
0x18004f49e  xor     r8d, r8d; bInitialState
0x18004f4a1  lea     edx, [r9+1]; bManualReset
0x18004f4a5  xor     ecx, ecx; lpEventAttributes
0x18004f4a7  call    cs:__imp_CreateEventW
0x18004f4ad  mov     rdx, rax
0x18004f4b0  lea     rcx, ?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x18004f4b7  call    ??4InterlockedAutoHandle@@QEAAAEAV0@PEAX@Z; InterlockedAutoHandle::operator=(void *)
0x18004f4bc  or      rcx, 0FFFFFFFFFFFFFFFFh; int
0x18004f4c0  mov     rax, rcx
0x18004f4c3  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x18004f4cc  test    rax, rax
0x18004f4cf  jnz     short loc_18004F4E5
0x18004f4d1  call    cs:__imp_GetLastError
0x18004f4d7  test    eax, eax
0x18004f4d9  jle     short loc_18004F4E7
0x18004f4db  movzx   eax, ax
0x18004f4de  or      eax, 80070000h
0x18004f4e3  jmp     short loc_18004F4E7
0x18004f4e5  mov     eax, ebx
0x18004f4e7  mov     [rsp+88h+pvData], eax
0x18004f4ee  mov     cs:dword_1800BC3D8, eax
0x18004f4f4  test    eax, eax
0x18004f4f6  jns     short loc_18004F515
0x18004f4f8  mov     r9d, eax; unsigned int
0x18004f4fb  lea     r8, aShutdownguardI; "ShutdownGuard::Initialize"
0x18004f502  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f509  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f50e  xor     eax, eax
0x18004f510  jmp     loc_18004F8EC
0x18004f515  call    ?InitializeUserTable@User@@SAJH@Z; User::InitializeUserTable(int)
0x18004f51a  mov     [rsp+88h+pvData], eax
0x18004f521  mov     cs:dword_1800BC448, eax
0x18004f527  test    eax, eax
0x18004f529  jns     short loc_18004F548
0x18004f52b  mov     r9d, eax; unsigned int
0x18004f52e  lea     r8, aUserInitialize; "User::InitializeUserTable"
0x18004f535  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f53c  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f541  xor     eax, eax
0x18004f543  jmp     loc_18004F8EC
0x18004f548  call    ?Init@CredStore@@SAJXZ; CredStore::Init(void)
0x18004f54d  mov     [rsp+88h+pvData], eax
0x18004f554  mov     cs:dword_1800BC3C8, eax
0x18004f55a  test    eax, eax
0x18004f55c  jns     short loc_18004F57B
0x18004f55e  mov     r8d, eax; unsigned int
0x18004f561  lea     rdx, SCHEDULE_SERVICE_CRED_STORE_INIT_ERROR; struct _EVENT_DESCRIPTOR *
0x18004f568  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x18004f56f  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18004f574  xor     eax, eax
0x18004f576  jmp     loc_18004F8EC
0x18004f57b  mov     [rsp+88h+lpdwDisposition], rbx; lpdwDisposition
0x18004f580  lea     rax, [rsp+88h+var_28]
0x18004f585  mov     [rsp+88h+phkResult], rax; phkResult
0x18004f58a  mov     [rsp+88h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18004f58f  mov     [rsp+88h+samDesired], 20019h; struct _GUID *
0x18004f597  mov     [rsp+88h+dwOptions], ebx; struct _GUID *
0x18004f59b  xor     r9d, r9d; lpClass
0x18004f59e  xor     r8d, r8d; Reserved
0x18004f5a1  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004f5a8  mov     rdi, 0FFFFFFFF80000002h
0x18004f5af  mov     rcx, rdi; hKey
0x18004f5b2  call    cs:__imp_RegCreateKeyExW
0x18004f5b8  test    eax, eax
0x18004f5ba  jz      short loc_18004F5C3
0x18004f5bc  xor     eax, eax
0x18004f5be  jmp     loc_18004F8EC
0x18004f5c3  mov     [rsp+88h+var_30], rbx
0x18004f5c8  call    cs:__imp_RtlIsStateSeparationEnabled
0x18004f5ce  test    al, al
0x18004f5d0  jz      short loc_18004F5EB
0x18004f5d2  lea     r9, [rsp+88h+var_30]
0x18004f5d7  mov     edx, 1
0x18004f5dc  mov     r8d, 2001Fh
0x18004f5e2  mov     rcx, r13
0x18004f5e5  call    cs:__imp_GetServiceRegistryStateKey
0x18004f5eb  mov     rdx, [rsp+88h+var_30]; HKEY
0x18004f5f0  mov     rcx, [rsp+88h+var_28]; HKEY
0x18004f5f5  call    ?CreateCommonJobStore@JobStore@@SAJPEAUHKEY__@@0@Z; JobStore::CreateCommonJobStore(HKEY__ *,HKEY__ *)
0x18004f5fa  mov     [rsp+88h+pvData], eax
0x18004f601  mov     cs:dword_1800BC3E8, eax
0x18004f607  test    eax, eax
0x18004f609  jns     short loc_18004F628
0x18004f60b  mov     r9d, eax; unsigned int
0x18004f60e  lea     r8, aJobstoreCreate; "JobStore::CreateCommonJobStore"
0x18004f615  lea     rdx, SCHEDULE_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004f61c  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18004f621  xor     eax, eax
0x18004f623  jmp     loc_18004F8EC
0x18004f628  mov     ecx, 1E0h; dwBytes
0x18004f62d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f632  mov     qword ptr [rsp+88h+pcbData], rax
0x18004f637  test    rax, rax
0x18004f63a  jz      short loc_18004F64E
0x18004f63c  mov     r8, [r14+78h]; void *
0x18004f640  mov     rdx, [r14+70h]; void *
0x18004f644  mov     rcx, rax; this
0x18004f647  call    ??0Scheduler@@QEAA@PEAX0@Z; Scheduler::Scheduler(void *,void *)
0x18004f64c  jmp     short loc_18004F651
0x18004f64e  mov     rax, rbx
0x18004f651  mov     cs:?g_pScheduler@@3PEAVScheduler@@EA, rax; Scheduler * g_pScheduler
0x18004f658  mov     cs:dword_1800BC418, ebx
0x18004f65e  mov     ecx, 838h; dwBytes
0x18004f663  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f668  test    rax, rax
0x18004f66b  jz      short loc_18004F677
0x18004f66d  mov     rcx, rax; this
0x18004f670  call    ??0EventTrapMap@@QEAA@XZ; EventTrapMap::EventTrapMap(void)
  ... truncated ...
```
