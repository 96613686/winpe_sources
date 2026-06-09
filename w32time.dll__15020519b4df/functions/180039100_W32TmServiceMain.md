# W32TmServiceMain

- ea: `0x180039100`
- end: `0x180039ccc`
- name: `W32TmServiceMain`
- size: `3020`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d420`

## callees

- `0x180005480`
- `0x180008930`
- `0x18000a210`
- `0x18000a7e0`
- `0x18000b200`
- `0x18000b260`
- `0x18000b494`
- `0x18000be58`
- `0x18000c28c`
- `0x18000c91c`
- `0x18000e620`
- `0x18000e758`
- `0x180011120`
- `0x1800180c4`
- `0x180018138`
- `0x18001a780`
- `0x18001a8dc`
- `0x18001a9b0`
- `0x18001d9a0`
- `0x18001fcc0`
- `0x180021170`
- `0x1800279b0`
- `0x180029fa0`
- `0x18002aca4`
- `0x18002b7b0`
- `0x18002b850`
- `0x18002c1c4`
- `0x18002d250`
- `0x18002dccc`
- `0x18002e7b8`
- `0x180030628`
- `0x180030990`
- `0x180030a54`
- `0x180030c20`
- `0x180030e70`
- `0x180031124`
- `0x180033e8c`
- `0x180039100`
- `0x18003d270`
- `0x18003dce4`
- `0x18003dd08`
- `0x18003dd2c`
- `0x18004b614`
- `0x18004c3b8`
- `0x180063ef0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039250`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039250`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180039157`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180039af2`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180039157`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180039af2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039454`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039454`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039286`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039944`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180039928`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180039928`
- `ntdll!RtlNtStatusToDosError` at `0x180039637`
- `ntdll!RtlNtStatusToDosError` at `0x180039637`
- `ntdll!RtlInitUnicodeString` at `0x18003935a`
- `ntdll!RtlInitUnicodeString` at `0x180039445`
- `ntdll!RtlInitUnicodeString` at `0x18003935a`
- `ntdll!RtlInitUnicodeString` at `0x180039445`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180039621`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180039621`
- `USERENV!RegisterGPNotification` at `0x1800395ee`
- `USERENV!RegisterGPNotification` at `0x1800395ee`

## string_xrefs

- `0x180039240`: `task_started`
- `0x18003926c`: `Service started as a task. Service will be shut down when synchornization is complete.\n`
- `0x180039346`: `Logging error: The time service encountered an error while refreshing its configuration in the registry and cannot start. The error was: %s\n`
- `0x18003942e`: `Logging error: The time service encountered an error while reading its configuration from the registry and cannot start. The error was: %s\n`
- `0x180039c62`: `Failed in initialization, w/o restart service`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall W32TmServiceMain(unsigned int a1, _QWORD *a2)
{
  char v3; // si
  signed int inited; // ebx
  signed int refreshed; // eax
  int v6; // esi
  char v7; // al
  WCHAR *v8; // rbx
  signed int Config; // eax
  int v10; // esi
  char v11; // al
  WCHAR *v12; // rbx
  __int64 v13; // rbx
  int v14; // eax
  signed int v15; // eax
  unsigned int v16; // esi
  int v17; // esi
  unsigned __int64 v18; // rbx
  __int64 v19; // rax
  signed int LastError; // eax
  void *v21; // rdx
  void *v22; // r9
  void *v23; // rdx
  void *v24; // r9
  void *v25; // rdx
  void *v26; // r9
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  unsigned int v33; // [rsp+30h] [rbp-40D8h]
  unsigned int v34; // [rsp+30h] [rbp-40D8h]
  unsigned int v35; // [rsp+30h] [rbp-40D8h]
  int v36; // [rsp+40h] [rbp-40C8h] BYREF
  char v37; // [rsp+44h] [rbp-40C4h]
  char v38; // [rsp+45h] [rbp-40C3h]
  char v39; // [rsp+46h] [rbp-40C2h]
  char v40; // [rsp+47h] [rbp-40C1h]
  char v41; // [rsp+48h] [rbp-40C0h]
  char v42; // [rsp+49h] [rbp-40BFh]
  int v43; // [rsp+4Ch] [rbp-40BCh]
  PCWSTR SourceString; // [rsp+50h] [rbp-40B8h] BYREF
  PCWSTR v45; // [rsp+58h] [rbp-40B0h] BYREF
  _QWORD *v46; // [rsp+60h] [rbp-40A8h]
  unsigned __int64 v47; // [rsp+68h] [rbp-40A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-4098h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-4090h] BYREF
  struct _UNICODE_STRING v50; // [rsp+88h] [rbp-4080h] BYREF
  unsigned __int16 v51[4]; // [rsp+D0h] [rbp-4038h] BYREF
  HANDLE v52; // [rsp+D8h] [rbp-4030h]
  HANDLE *v53; // [rsp+E0h] [rbp-4028h]
  void (__fastcall *v54)(void *); // [rsp+E8h] [rbp-4020h]
  int v55; // [rsp+F0h] [rbp-4018h]
  HANDLE v56; // [rsp+F8h] [rbp-4010h]
  __int64 *v57; // [rsp+100h] [rbp-4008h]
  void (__fastcall *v58)(void *); // [rsp+108h] [rbp-4000h]
  int v59; // [rsp+110h] [rbp-3FF8h]
  HANDLE v60; // [rsp+118h] [rbp-3FF0h]
  __int64 *v61; // [rsp+120h] [rbp-3FE8h]
  void (__fastcall *v62)(int *); // [rsp+128h] [rbp-3FE0h]
  int v63; // [rsp+130h] [rbp-3FD8h]
  HANDLE v64; // [rsp+138h] [rbp-3FD0h]
  HANDLE *v65; // [rsp+140h] [rbp-3FC8h]
  void (__fastcall *v66)(void *, unsigned __int8); // [rsp+148h] [rbp-3FC0h]
  int v67; // [rsp+150h] [rbp-3FB8h]
  HANDLE v68; // [rsp+158h] [rbp-3FB0h]
  HANDLE *v69; // [rsp+160h] [rbp-3FA8h]
  void (__fastcall *v70)(void *, unsigned __int8); // [rsp+168h] [rbp-3FA0h]
  int v71; // [rsp+170h] [rbp-3F98h]
  HANDLE v72; // [rsp+178h] [rbp-3F90h]
  HANDLE *v73; // [rsp+180h] [rbp-3F88h]
  void (__fastcall *v74)(void *); // [rsp+188h] [rbp-3F80h]
  int v75; // [rsp+190h] [rbp-3F78h]
  HANDLE v76; // [rsp+198h] [rbp-3F70h]
  __int64 *v77; // [rsp+1A0h] [rbp-3F68h]
  void (__fastcall *v78)(void *); // [rsp+1A8h] [rbp-3F60h]
  int v79; // [rsp+1B0h] [rbp-3F58h]
  HANDLE v80; // [rsp+1B8h] [rbp-3F50h]
  __int64 *v81; // [rsp+1C0h] [rbp-3F48h]
  void (__fastcall *v82)(int *); // [rsp+1C8h] [rbp-3F40h]
  int v83; // [rsp+1D0h] [rbp-3F38h]
  HANDLE v84; // [rsp+1D8h] [rbp-3F30h]
  HANDLE *v85; // [rsp+1E0h] [rbp-3F28h]
  void (__fastcall *v86)(void *); // [rsp+1E8h] [rbp-3F20h]
  int v87; // [rsp+1F0h] [rbp-3F18h]
  HANDLE v88; // [rsp+1F8h] [rbp-3F10h]
  __int64 *v89; // [rsp+200h] [rbp-3F08h]
  void (__fastcall *v90)(void *); // [rsp+208h] [rbp-3F00h]
  unsigned __int16 v91; // [rsp+20D0h] [rbp-2038h] BYREF
  _BYTE v92[8190]; // [rsp+20D2h] [rbp-2036h] BYREF

  v46 = a2;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  v3 = 0;
  v41 = 0;
  v47 = 0;
  v48 = _set_se_translator(SeTransFunc);
  g_servicestatushandle = (struct SERVICE_STATUS_HANDLE__ *)((__int64 (__fastcall *)(const WCHAR *, __int64 (__fastcall *)(unsigned int, unsigned int, void *, void *), _QWORD))fnW32TmRegisterServiceCtrlHandlerEx)(
                                                              L"w32time",
                                                              W32TimeServiceCtrlHandler,
                                                              0);
  if ( !g_servicestatushandle )
    return;
  SafeAllocaInitialize();
  _InterlockedExchange(&g_bIsSafeAllocaInitialized, 1);
  v41 = 1;
  inited = InitShutdownState();
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_77;
  inited = AllowShutdown(0);
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_77;
  v38 = 1;
  v3 = 1;
  v42 = 1;
  inited = InitGlobalState();
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_74;
  v40 = 1;
  inited = FileLogBegin();
  v36 = inited;
  LogFileLogOpenErrorEvent(inited);
  if ( inited < 0 )
    goto LABEL_74;
  InitLocStrings();
  inited = W32TimeInitializeEvents();
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_74;
  v39 = 1;
  bStartedAsTask = 0;
  if ( a1 > 1 && !(unsigned int)_o__wcsicmp(v46[1], L"task_started") )
  {
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAdd(L"Service started as a task. Service will be shut down when synchornization is complete.\n");
    bStartedAsTask = 1;
  }
  EnterCriticalSection(&CriticalSection);
  v37 = 1;
  inited = MySetServiceStatus(2u, 0x3F2u, 0);
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  RegistrationHandle = RegisterForConnectedStandby();
  if ( !RegistrationHandle )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failed to register for power state changes\n");
    inited = -2147418113;
    v36 = -2147418113;
    goto LABEL_72;
  }
  refreshed = RefreshConfig();
  v6 = refreshed;
  v36 = refreshed;
  if ( refreshed < 0 )
  {
    SourceString = 0;
    DestinationString = 0;
    inited = GetSystemErrorString(refreshed, (unsigned __int16 **)&SourceString);
    v36 = inited;
    if ( inited >= 0 )
    {
      v7 = FileLogAllowEntry(11);
      v8 = (WCHAR *)SourceString;
      if ( v7 )
        FileLogAdd(
          L"Logging error: The time service encountered an error while refreshing its configuration in the registry and ca"
           "nnot start. The error was: %s\n",
          SourceString);
      RtlInitUnicodeString(&DestinationString, v8);
      LocalFree(v8);
      inited = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_CONFIG_REFRESH_FAILED, L"u", &DestinationString);
      v36 = inited;
      if ( inited >= 0 )
      {
        inited = v6;
        v36 = v6;
      }
    }
    goto LABEL_72;
  }
  inited = MySetServiceStatus(2u, 0x3F2u, 0);
  v36 = inited;
  if ( inited < 0 )
  {
LABEL_72:
    LeaveCriticalSection(&CriticalSection);
    goto LABEL_73;
  }
  Config = ReadConfig((struct StateInfo *)&g_state, (struct TimeProvider ***)&qword_1800A42F0);
  v10 = Config;
  v36 = Config;
  if ( Config < 0 )
  {
    v45 = 0;
    v50 = 0;
    inited = GetSystemErrorString(Config, (unsigned __int16 **)&v45);
    v36 = inited;
    if ( inited >= 0 )
    {
      v11 = FileLogAllowEntry(11);
      v12 = (WCHAR *)v45;
      if ( v11 )
        FileLogAdd(
          L"Logging error: The time service encountered an error while reading its configuration from the registry and can"
           "not start. The error was: %s\n",
          v45);
      RtlInitUnicodeString(&v50, v12);
      LocalFree(v12);
      inited = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_CONFIG_READ_FAILED, L"u", &v50);
      v36 = inited;
      if ( inited >= 0 )
      {
        inited = v10;
        v36 = v10;
      }
    }
    goto LABEL_72;
  }
  AccurateGetTickCountSafe(&qword_1800A42F8, 0);
  qword_1800A4308 = qword_1800A42F8;
  dword_1800A381C = *((_DWORD *)qword_1800A42F0 + 25);
  dword_1800A45B8 = *((_DWORD *)qword_1800A42F0 + 55);
  v13 = (unsigned int)(*((_DWORD *)qword_1800A42F0 + 4) << 6);
  o_log_0((float)(1.0 / (float)(int)v13));
  dword_1800A4358 = (int)o_ceil_0();
  if ( (unsigned __int8)FileLogAllowEntry(64) )
    FileLogAdd(
      L"lastClockRate=%ld, clockFrequency:%I64u clockPrecision=%d\n",
      *((unsigned int *)qword_1800A42F0 + 4),
      v13,
      (unsigned int)dword_1800A4358);
  inited = MySetServiceStatus(2u, 0x3F2u, 0);
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  inited = StartOrStopTimeSlipNotification(1);
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  LOBYTE(word_1800A45A8) = 1;
  inited = OpenSocketLayer();
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  HIBYTE(word_1800A45A8) = 1;
  RequestNetTopoChangeNotification(&qword_1800A37B8);
  inited = RequestNetTopoChangeNotification(&s);
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  byte_1800A45AA = 1;
  if ( RegisterGPNotification(qword_1800A36E8, 1) )
    byte_1800A45AB = 1;
  HandleDomHierRoleChangeEvent(&v36);
  v36 = 0;
  v14 = LsaRegisterPolicyChangeNotification(PolicyNotifyServerRoleInformation, NotificationEventHandle);
  v36 = v14;
  if ( v14 )
  {
    v15 = RtlNtStatusToDosError(v14);
    inited = v15;
    if ( v15 > 0 )
      inited = (unsigned __int16)v15 | 0x80070000;
    v36 = inited;
    goto LABEL_72;
  }
  v16 = dword_1800A468C;
  inited = UpdateNetlogonServiceBits(1);
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  if ( v16 != dword_1800A468C )
  {
    SetNetlogonServiceBits(dword_1800A468C);
    v36 = 0;
  }
  inited = StartClockDiscipline();
  v36 = inited;
  if ( inited < 0 )
    goto LABEL_72;
  qword_1800A4310 = 10000000 * (1LL << dword_1800A381C);
  qword_1800A4320 = 160000000;
  qword_1800A4328 = 160000000;
  qword_1800A4330 = 0;
  *(_DWORD *)v51 = 8;
  v52 = qword_1800A36E8;
  v53 = &qword_1800A3768;
  v54 = HandleManagerGPUpdate;
  v55 = 0;
  v56 = qword_1800A36F0;
  v57 = &qword_1800A3760;
  v58 = HandleManagerParamChange;
  v59 = 0;
  v60 = qword_1800A36F8;
  v61 = &qword_1800A3770;
  v62 = HandleManagerTimeSlip;
  v63 = 8;
  v64 = qword_1800A3710;
  v65 = &qword_1800A3778;
  v66 = HandleManagerNetTopoChangeNoRPC4;
  v67 = 8;
  v68 = qword_1800A3718;
  v69 = &qword_1800A3780;
  v70 = HandleManagerNetTopoChangeNoRPC6;
  v71 = 8;
  v72 = qword_1800A3738;
  v73 = &qword_1800A37A0;
  v74 = HandleManagerApmResumeSuspendEvent;
  v75 = 8;
  v76 = hThread;
  v77 = &qword_1800A3788;
  v78 = HandleClockDisplnThread;
  v79 = 0;
  v80 = NotificationEventHandle;
  v81 = &qword_1800A3790;
  v82 = HandleDomHierRoleChangeEvent;
  v83 = 8;
  v84 = qword_1800A3730;
  v85 = &qword_1800A3798;
  v86 = HandleSamplesAvail;
  v87 = 8;
  v88 = qword_1800A3740;
  v89 = &qword_1800A37A8;
  v90 = HandleSetProviderStatus;
  v17 = 0;
  v43 = 0;
  while ( (unsigned __int64)v17 < 0xA )
  {
    v18 = 32LL * v17;
    v19 = RegisterWaitForSingleObjectEx(
            *(HANDLE *)((char *)&v52 + v18),
            *(void (__fastcall **)(void *))((char *)&v54 + v18),
            0,
            0xFFFFFFFFLL,
            *(_DWORD *)&v51[v18 / 2]);
    *(&v53)[v18 / 8] = (HANDLE)v19;
    if ( !v19 )
    {
      LastError = GetLastError();
      inited = LastError;
      if ( LastError > 0 )
        inited = (unsigned __int16)LastError | 0x80070000;
      v36 = inited;
      goto LABEL_71;
    }
    v43 = ++v17;
  }
  inited = myCreateTimerQueueTimer(&lpCriticalSection);
  v36 = inited;
  if ( inited >= 0 )
  {
    inited = myStartTimerQueueTimer(
               lpCriticalSection,
               v21,
               (void (*)(void *, unsigned __int8))HandleTimeout,
               v22,
               0xFFFFu,
               0xFFFFu,
               v33);
    v36 = inited;
    if ( inited >= 0 )
    {
      inited = myCreateTimerQueueTimer(&qword_1800A4640);
      v36 = inited;
      if ( inited >= 0 )
      {
        inited = myStartTimerQueueTimer(
                   qword_1800A4640,
                   v23,
                   (void (*)(void *, unsigned __int8))HandleRefreshTickCount,
                   v24,
                   0x5265C00u,
                   0x5265C00u,
                   v34);
        v36 = inited;
        if ( inited >= 0 )
        {
          inited = myCreateTimerQueueTimer(&qword_1800A4650);
          v36 = inited;
          if ( inited >= 0 )
          {
            inited = myStartTimerQueueTimer(
                       qword_1800A4650,
                       v25,
                       (void (*)(void *, unsigned __int8))HandleManagerNetTopoChangeActual,
                       v26,
                       0x3E8u,
                       0,
                       v35);
            v36 = inited;
            if ( inited >= 0 )
            {
              byte_1800A4648 = 1;
              v27 = InitializePerfInfo();
              if ( v27 > 0 )
                v27 = (unsigned __int16)v27 | 0x80070000;
              v36 = v27;
              RefreshAndEnforceSecureTime(0);
              StartAllProviders();
              if ( (unsigned __int8)FileLogAllowEntry(121) )
                FileLogTimeProviderList(*(struct TimeProvider **)qword_1800A42F0, L"All providers started");
              inited = W32TmStartRpcServer();
              v36 = inited;
              if ( inited >= 0 )
              {
                inited = UpdateTimerQueue1();
                v36 = inited;
                if ( inited >= 0 )
                {
                  inited = MySetServiceStatus(4u, 0, 0);
                  v36 = inited;
                  if ( inited >= 0 )
                  {
                    _set_se_translator(v48);
                    if ( g_pSvcsGlobalData
                      && (v28 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pSvcsGlobalData
                                 + 24))(
                                  &WaitHandle,
                                  *v46,
                                  qword_1800A3748,
                                  StopService,
                                  0,
                                  8),
                          (inited = v28) != 0) )
                    {
                      if ( v28 > 0 )
                        inited = (unsigned __int16)v28 | 0x80070000;
                    }
                    else
                    {
                      v91 = 0;
                      memset_0(v92, 0, sizeof(v92));
                      v51[0] = 0;
                      memset_0(&v51[1], 0, 0x1FFEu);
                      GetServiceConfigStrings(&v91, v29, v51);
                      AccurateGetSystemTime(&v47);
                      LogEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_STARTUP, L"TiSSi", v47);
                      InitializeW32TimeTelemetry();
                      inited = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_71:
  if ( v37 )
    goto LABEL_72;
LABEL_73:
  v3 = v38;
  if ( !v38 )
    goto LABEL_77;
LABEL_74:
  v30 = AllowShutdown(1);
  if ( v30 >= 0 )
    goto LABEL_77;
  if ( inited >= 0 )
  {
    inited = v30;
LABEL_77:
    if ( inited >= 0 )
      return;
  }
  if ( v39 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(73) )
      FileLogAdd(L"Failed in initialization, w/o restart service");
    SendServiceShutdown((void *)(unsigned int)inited, v31, v32);
  }
  else
  {
    if ( v40 )
      FileLogEnd();
    if ( v3 )
      FreeGlobalState();
    if ( v41 )
      FreeShutdownState();
    MySetServiceStatus(1u, 0, (unsigned __int16)inited);
    g_servicestatushandle = 0;
  }
}

```

## disassembly

```asm
0x180039100  push    rbx
0x180039102  push    rsi
0x180039103  push    rdi
0x180039104  push    r14
0x180039106  mov     eax, 40E8h
0x18003910b  call    _alloca_probe
0x180039110  sub     rsp, rax
0x180039113  mov     rax, cs:__security_cookie
0x18003911a  xor     rax, rsp
0x18003911d  mov     [rsp+4108h+var_38], rax
0x180039125  mov     r14d, ecx
0x180039128  mov     [rsp+4108h+var_40A8], rdx
0x18003912d  xor     edi, edi
0x18003912f  mov     [rsp+4108h+var_40C3], dil
0x180039134  mov     [rsp+4108h+var_40C2], dil
0x180039139  mov     [rsp+4108h+var_40C1], dil
0x18003913e  mov     [rsp+4108h+var_40C4], dil
0x180039143  mov     sil, dil
0x180039146  mov     [rsp+4108h+var_40C0], dil
0x18003914b  mov     [rsp+4108h+var_40A0], rdi
0x180039150  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180039157  call    cs:__imp__set_se_translator
0x18003915e  nop     dword ptr [rax+rax+00h]
0x180039163  mov     [rsp+4108h+var_4098], rax
0x180039168  xor     r8d, r8d
0x18003916b  lea     rdx, ?W32TimeServiceCtrlHandler@@YAKKKPEAX0@Z; W32TimeServiceCtrlHandler(ulong,ulong,void *,void *)
0x180039172  lea     rcx, ModuleName; "w32time"
0x180039179  mov     rax, cs:?fnW32TmRegisterServiceCtrlHandlerEx@@3P6APEAUSERVICE_STATUS_HANDLE__@@PEBGP6AKKKPEAX1@Z1@ZEA; SERVICE_STATUS_HANDLE__ * (*fnW32TmRegisterServiceCtrlHandlerEx)(ushort const *,ulong (*)(ulong,ulong,void *,void *),void *)
0x180039180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039185  mov     cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x18003918c  test    rax, rax
0x18003918f  jz      loc_180039CAE
0x180039195  call    SafeAllocaInitialize
0x18003919a  mov     eax, 1
0x18003919f  xchg    eax, cs:g_bIsSafeAllocaInitialized
0x1800391a5  mov     [rsp+4108h+var_40C0], 1
0x1800391aa  call    ?InitShutdownState@@YAJXZ; InitShutdownState(void)
0x1800391af  mov     ebx, eax
0x1800391b1  mov     [rsp+4108h+var_40C8], eax
0x1800391b5  test    eax, eax
0x1800391b7  jns     short loc_1800391BE
0x1800391b9  jmp     loc_180039C49
0x1800391be  xor     ecx, ecx; int
0x1800391c0  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x1800391c5  mov     ebx, eax
0x1800391c7  mov     [rsp+4108h+var_40C8], eax
0x1800391cb  test    eax, eax
0x1800391cd  jns     short loc_1800391D4
0x1800391cf  jmp     loc_180039C49
0x1800391d4  mov     [rsp+4108h+var_40C3], 1
0x1800391d9  mov     sil, 1
0x1800391dc  mov     [rsp+4108h+var_40BF], sil
0x1800391e1  call    ?InitGlobalState@@YAJXZ; InitGlobalState(void)
0x1800391e6  mov     ebx, eax
0x1800391e8  mov     [rsp+4108h+var_40C8], eax
0x1800391ec  test    eax, eax
0x1800391ee  jns     short loc_1800391F5
0x1800391f0  jmp     loc_180039C35
0x1800391f5  mov     [rsp+4108h+var_40C1], sil
0x1800391fa  call    FileLogBegin
0x1800391ff  mov     ebx, eax
0x180039201  mov     [rsp+4108h+var_40C8], eax
0x180039205  mov     ecx, eax; dwMessageId
0x180039207  call    ?LogFileLogOpenErrorEvent@@YAXJ@Z; LogFileLogOpenErrorEvent(long)
0x18003920c  test    ebx, ebx
0x18003920e  jns     short loc_180039215
0x180039210  jmp     loc_180039C35
0x180039215  call    ?InitLocStrings@@YAJXZ; InitLocStrings(void)
0x18003921a  call    ?W32TimeInitializeEvents@@YAJXZ; W32TimeInitializeEvents(void)
0x18003921f  mov     ebx, eax
0x180039221  mov     [rsp+4108h+var_40C8], eax
0x180039225  test    eax, eax
0x180039227  jns     short loc_18003922E
0x180039229  jmp     loc_180039C35
0x18003922e  mov     [rsp+4108h+var_40C2], sil
0x180039233  mov     cs:?bStartedAsTask@@3_NA, dil; bool bStartedAsTask
0x18003923a  cmp     r14d, 1
0x18003923e  jbe     short loc_18003927F
0x180039240  lea     rdx, aTaskStarted; "task_started"
0x180039247  mov     rcx, [rsp+4108h+var_40A8]
0x18003924c  mov     rcx, [rcx+8]
0x180039250  call    cs:__imp__o__wcsicmp
0x180039257  nop     dword ptr [rax+rax+00h]
0x18003925c  test    eax, eax
0x18003925e  jnz     short loc_18003927F
0x180039260  lea     ecx, [rax+40h]
0x180039263  call    FileLogAllowEntry
0x180039268  test    al, al
0x18003926a  jz      short loc_180039278
0x18003926c  lea     rcx, aServiceStarted; "Service started as a task. Service will"...
0x180039273  call    FileLogAdd
0x180039278  mov     cs:?bStartedAsTask@@3_NA, sil; bool bStartedAsTask
0x18003927f  lea     rcx, CriticalSection; lpCriticalSection
0x180039286  call    cs:__imp_EnterCriticalSection
0x18003928d  nop     dword ptr [rax+rax+00h]
0x180039292  mov     [rsp+4108h+var_40C8], edi
0x180039296  mov     [rsp+4108h+var_40C4], sil
0x18003929b  xor     r8d, r8d; unsigned int
0x18003929e  mov     r14d, 3F2h
0x1800392a4  mov     edx, r14d; unsigned int
0x1800392a7  lea     ecx, [r8+2]; unsigned int
0x1800392ab  call    ?MySetServiceStatus@@YAJKKK@Z; MySetServiceStatus(ulong,ulong,ulong)
0x1800392b0  mov     ebx, eax
0x1800392b2  mov     [rsp+4108h+var_40C8], eax
0x1800392b6  test    eax, eax
0x1800392b8  jns     short loc_1800392BF
0x1800392ba  jmp     loc_180039C18
0x1800392bf  call    ?RegisterForConnectedStandby@@YAPEAXXZ; RegisterForConnectedStandby(void)
0x1800392c4  mov     cs:RegistrationHandle, rax
0x1800392cb  test    rax, rax
0x1800392ce  jnz     short loc_1800392F5
0x1800392d0  xor     ecx, ecx
0x1800392d2  call    FileLogAllowEntry
0x1800392d7  test    al, al
0x1800392d9  jz      short loc_1800392E7
0x1800392db  lea     rcx, aFailedToRegist; "Failed to register for power state chan"...
0x1800392e2  call    FileLogAdd
0x1800392e7  mov     ebx, 8000FFFFh
0x1800392ec  mov     [rsp+4108h+var_40C8], ebx
0x1800392f0  jmp     loc_180039C18
0x1800392f5  call    ?RefreshConfig@@YAJXZ; RefreshConfig(void)
0x1800392fa  mov     esi, eax
0x1800392fc  mov     [rsp+4108h+var_40C8], eax
0x180039300  test    eax, eax
0x180039302  jns     loc_1800393AE
0x180039308  mov     [rsp+4108h+SourceString], rdi
0x18003930d  xorps   xmm0, xmm0
0x180039310  movups  xmmword ptr [rsp+4108h+DestinationString.Length], xmm0
0x180039315  lea     rdx, [rsp+4108h+SourceString]; unsigned __int16 **
0x18003931a  mov     ecx, eax; dwMessageId
0x18003931c  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x180039321  mov     ebx, eax
0x180039323  mov     [rsp+4108h+var_40C8], eax
0x180039327  test    eax, eax
0x180039329  jns     short loc_180039330
0x18003932b  jmp     loc_180039C18
0x180039330  mov     ecx, 0Bh
0x180039335  call    FileLogAllowEntry
0x18003933a  mov     rbx, [rsp+4108h+SourceString]
0x18003933f  test    al, al
0x180039341  jz      short loc_180039352
0x180039343  mov     rdx, rbx
0x180039346  lea     rcx, aLoggingErrorTh_4; "Logging error: The time service encount"...
0x18003934d  call    FileLogAdd
0x180039352  mov     rdx, rbx; SourceString
0x180039355  lea     rcx, [rsp+4108h+DestinationString]; DestinationString
0x18003935a  call    cs:__imp_RtlInitUnicodeString
0x180039361  nop     dword ptr [rax+rax+00h]
0x180039366  mov     rcx, rbx; hMem
0x180039369  call    cs:__imp_LocalFree
0x180039370  nop     dword ptr [rax+rax+00h]
0x180039375  lea     r9, [rsp+4108h+DestinationString]
0x18003937a  lea     r8, aU; "u"
0x180039381  lea     rdx, W32TIME_EVENT_CONFIG_REFRESH_FAILED
0x180039388  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18003938f  call    LogEvent
0x180039394  mov     ebx, eax
0x180039396  mov     [rsp+4108h+var_40C8], eax
0x18003939a  test    eax, eax
0x18003939c  jns     short loc_1800393A3
0x18003939e  jmp     loc_180039C18
0x1800393a3  mov     ebx, esi
0x1800393a5  mov     [rsp+4108h+var_40C8], ebx
0x1800393a9  jmp     loc_180039C18
0x1800393ae  xor     r8d, r8d; unsigned int
0x1800393b1  mov     edx, r14d; unsigned int
0x1800393b4  lea     ecx, [r8+2]; unsigned int
0x1800393b8  call    ?MySetServiceStatus@@YAJKKK@Z; MySetServiceStatus(ulong,ulong,ulong)
0x1800393bd  mov     ebx, eax
0x1800393bf  mov     [rsp+4108h+var_40C8], eax
0x1800393c3  test    eax, eax
0x1800393c5  jns     short loc_1800393CC
0x1800393c7  jmp     loc_180039C18
0x1800393cc  lea     rdx, qword_1800A42F0; struct ConfigInfo **
0x1800393d3  lea     rcx, ?g_state@@3UStateInfo@@A; struct StateInfo *
0x1800393da  call    ?ReadConfig@@YAJPEAUStateInfo@@PEAPEAUConfigInfo@@@Z; ReadConfig(StateInfo *,ConfigInfo * *)
0x1800393df  mov     esi, eax
0x1800393e1  mov     [rsp+4108h+var_40C8], eax
0x1800393e5  test    eax, eax
0x1800393e7  jns     loc_18003949C
0x1800393ed  mov     [rsp+4108h+var_40B0], rdi
0x1800393f2  xorps   xmm0, xmm0
0x1800393f5  movups  xmmword ptr [rsp+4108h+var_4080.Length], xmm0
0x1800393fd  lea     rdx, [rsp+4108h+var_40B0]; unsigned __int16 **
0x180039402  mov     ecx, eax; dwMessageId
0x180039404  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x180039409  mov     ebx, eax
0x18003940b  mov     [rsp+4108h+var_40C8], eax
0x18003940f  test    eax, eax
0x180039411  jns     short loc_180039418
0x180039413  jmp     loc_180039C18
0x180039418  mov     ecx, 0Bh
0x18003941d  call    FileLogAllowEntry
0x180039422  mov     rbx, [rsp+4108h+var_40B0]
0x180039427  test    al, al
0x180039429  jz      short loc_18003943A
0x18003942b  mov     rdx, rbx
0x18003942e  lea     rcx, aLoggingErrorTh_2; "Logging error: The time service encount"...
0x180039435  call    FileLogAdd
0x18003943a  mov     rdx, rbx; SourceString
0x18003943d  lea     rcx, [rsp+4108h+var_4080]; DestinationString
0x180039445  call    cs:__imp_RtlInitUnicodeString
0x18003944c  nop     dword ptr [rax+rax+00h]
0x180039451  mov     rcx, rbx; hMem
0x180039454  call    cs:__imp_LocalFree
0x18003945b  nop     dword ptr [rax+rax+00h]
0x180039460  lea     r9, [rsp+4108h+var_4080]
0x180039468  lea     r8, aU; "u"
0x18003946f  lea     rdx, W32TIME_EVENT_CONFIG_READ_FAILED
0x180039476  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18003947d  call    LogEvent
0x180039482  mov     ebx, eax
0x180039484  mov     [rsp+4108h+var_40C8], eax
0x180039488  test    eax, eax
0x18003948a  jns     short loc_180039491
0x18003948c  jmp     loc_180039C18
0x180039491  mov     ebx, esi
0x180039493  mov     [rsp+4108h+var_40C8], ebx
0x180039497  jmp     loc_180039C18
0x18003949c  xor     edx, edx; bool
0x18003949e  lea     rcx, qword_1800A42F8; unsigned __int64 *
0x1800394a5  call    ?AccurateGetTickCountSafe@@YAJPEA_K_N@Z; AccurateGetTickCountSafe(unsigned __int64 *,bool)
0x1800394aa  mov     rax, cs:qword_1800A42F8
0x1800394b1  mov     cs:qword_1800A4308, rax
0x1800394b8  mov     rcx, cs:qword_1800A42F0
0x1800394bf  mov     eax, [rcx+64h]
0x1800394c2  mov     cs:dword_1800A381C, eax
0x1800394c8  mov     eax, [rcx+0DCh]
0x1800394ce  mov     cs:dword_1800A45B8, eax
0x1800394d4  mov     ebx, [rcx+10h]
0x1800394d7  shl     ebx, 6
0x1800394da  xorps   xmm1, xmm1
0x1800394dd  test    rbx, rbx
0x1800394e0  js      short loc_1800394E9
0x1800394e2  cvtsi2ss xmm1, rbx
0x1800394e7  jmp     short loc_180039501
0x1800394e9  mov     rcx, rbx
0x1800394ec  shr     rcx, 1
0x1800394ef  mov     rax, rbx
0x1800394f2  and     eax, 1
0x1800394f5  or      rcx, rax
0x1800394f8  cvtsi2ss xmm1, rcx
0x1800394fd  addss   xmm1, xmm1
0x180039501  movss   xmm0, cs:__real@3f800000
0x180039509  divss   xmm0, xmm1
0x18003950d  cvtps2pd xmm0, xmm0; X
0x180039510  call    _o_log_0
0x180039515  divsd   xmm0, cs:__real@3fe62e42fead449c
0x18003951d  call    _o_ceil_0
0x180039522  cvttsd2si eax, xmm0
0x180039526  mov     cs:dword_1800A4358, eax
0x18003952c  mov     ecx, 40h ; '@'
0x180039531  call    FileLogAllowEntry
0x180039536  test    al, al
0x180039538  jz      short loc_18003955A
0x18003953a  mov     r9d, cs:dword_1800A4358
0x180039541  mov     r8, rbx
0x180039544  mov     rdx, cs:qword_1800A42F0
0x18003954b  mov     edx, [rdx+10h]
0x18003954e  lea     rcx, aLastclockrateL; "lastClockRate=%ld, clockFrequency:%I64u"...
0x180039555  call    FileLogAdd
0x18003955a  xor     r8d, r8d; unsigned int
0x18003955d  mov     edx, r14d; unsigned int
0x180039560  lea     ecx, [r8+2]; unsigned int
0x180039564  call    ?MySetServiceStatus@@YAJKKK@Z; MySetServiceStatus(ulong,ulong,ulong)
0x180039569  mov     ebx, eax
0x18003956b  mov     [rsp+4108h+var_40C8], eax
0x18003956f  test    eax, eax
0x180039571  jns     short loc_180039578
0x180039573  jmp     loc_180039C18
0x180039578  mov     cl, 1; bool
0x18003957a  call    ?StartOrStopTimeSlipNotification@@YAJ_N@Z; StartOrStopTimeSlipNotification(bool)
0x18003957f  mov     ebx, eax
0x180039581  mov     [rsp+4108h+var_40C8], eax
0x180039585  test    eax, eax
0x180039587  jns     short loc_18003958E
0x180039589  jmp     loc_180039C18
0x18003958e  mov     byte ptr cs:word_1800A45A8, 1
0x180039595  call    ?OpenSocketLayer@@YAJXZ; OpenSocketLayer(void)
0x18003959a  mov     ebx, eax
0x18003959c  mov     [rsp+4108h+var_40C8], eax
0x1800395a0  test    eax, eax
0x1800395a2  jns     short loc_1800395A9
0x1800395a4  jmp     loc_180039C18
0x1800395a9  mov     byte ptr cs:word_1800A45A8+1, 1
0x1800395b0  lea     rcx, qword_1800A37B8; unsigned __int64 *
0x1800395b7  call    ?RequestNetTopoChangeNotification@@YAJPEA_K@Z; RequestNetTopoChangeNotification(unsigned __int64 *)
0x1800395bc  mov     [rsp+4108h+var_40C8], eax
0x1800395c0  lea     rcx, s; unsigned __int64 *
0x1800395c7  call    ?RequestNetTopoChangeNotification@@YAJPEA_K@Z; RequestNetTopoChangeNotification(unsigned __int64 *)
0x1800395cc  mov     ebx, eax
0x1800395ce  mov     [rsp+4108h+var_40C8], eax
0x1800395d2  test    eax, eax
0x1800395d4  jns     short loc_1800395DB
0x1800395d6  jmp     loc_180039C18
0x1800395db  mov     cs:byte_1800A45AA, 1
0x1800395e2  mov     edx, 1; bMachine
0x1800395e7  mov     rcx, cs:qword_1800A36E8; hEvent
0x1800395ee  call    cs:__imp_RegisterGPNotification
0x1800395f5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
