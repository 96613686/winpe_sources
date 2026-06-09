# ItSpStartIdleDetection(_ITSRV_GLOBAL_CONTEXT *)

- ea: `0x180073254`
- end: `0x1800736af`
- name: `?ItSpStartIdleDetection@@YAKPEAU_ITSRV_GLOBAL_CONTEXT@@@Z`
- size: `1115`
- prototype: `__int64 __fastcall(struct _ITSRV_GLOBAL_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073c94`

## callees

- `0x18003e270`
- `0x18003e4a8`
- `0x180073254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800733e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800733e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073648`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073648`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180073397`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180073397`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800733f8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800733f8`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007351a`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007351a`
- `ntdll!RtlInitUnicodeString` at `0x1800732f5`
- `ntdll!RtlInitUnicodeString` at `0x180073306`
- `ntdll!RtlInitUnicodeString` at `0x1800732f5`
- `ntdll!RtlInitUnicodeString` at `0x180073306`
- `ntdll!RtlNtStatusToDosError` at `0x1800732dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800732dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180073440`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180073440`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800733d5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800733d5`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x1800732d1`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x1800732d1`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x18007333d`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x18007333d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180073490`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800734d2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18007355e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800735a0`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800735e6`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180073628`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180073490`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800734d2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18007355e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800735a0`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800735e6`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180073628`
- `WMICLNT!WmiOpenBlock` at `0x1800732ae`
- `WMICLNT!WmiOpenBlock` at `0x1800732ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ItSpStartIdleDetection(struct _ITSRV_GLOBAL_CONTEXT *a1)
{
  NTSTATUS Query; // eax
  DWORD SystemSnapshot; // ebx
  __int64 v4; // r8
  DWORD DueTime; // edx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  __int128 Recipient; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v9; // [rsp+50h] [rbp-20h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  struct _FILETIME v11; // [rsp+90h] [rbp+20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+28h] BYREF

  v11.dwHighDateTime = HIDWORD(a1);
  DestinationString = 0;
  v11.dwLowDateTime = 0;
  v9 = 0;
  SystemTimeAsFileTime = 0;
  Recipient = 0;
  if ( byte_1800BD492 && !qword_1800BD370 && (unsigned int)WmiOpenBlock(DiskPerfGuid, 0x80000000LL, &qword_1800BD370) )
    qword_1800BD370 = 0;
  if ( !qword_1800BD388 )
  {
    Query = PcwCreateQuery(&qword_1800BD388, 0);
    if ( Query < 0 )
      return RtlNtStatusToDosError(Query);
    RtlInitUnicodeString(&DestinationString, L"Processor Information");
    RtlInitUnicodeString(&v9, L"_Total");
    LOBYTE(v4) = 1;
    Query = ((__int64 (__fastcall *)(struct _FILETIME *, HANDLE, __int64, _UNICODE_STRING *, struct _UNICODE_STRING *, int, __int64, _QWORD, _QWORD, _QWORD))PcwAddQueryItem)(
              &v11,
              qword_1800BD388,
              v4,
              &DestinationString,
              &v9,
              -1,
              0x8000,
              0,
              Recipient,
              *((_QWORD *)&Recipient + 1));
    if ( Query < 0 )
      return RtlNtStatusToDosError(Query);
  }
  if ( (_DWORD)xmmword_1800BD1C4 != 1147547697
    || (SystemSnapshot = ItSpGetSystemSnapshot(
                           (struct _ITSRV_GLOBAL_CONTEXT *)&ItSrvGlobalContext,
                           (struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800BD390)) == 0
    && (SystemSnapshot = ItSpCopySystemSnapshot(
                           (struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800BD3E8,
                           (struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800BD390)) == 0 )
  {
    ResetEvent(qword_1800BD310);
    DueTime = Period;
    if ( ::DueTime >= Period )
      DueTime = ::DueTime;
    if ( CreateTimerQueueTimer(
           &Timer,
           0,
           (WAITORTIMERCALLBACK)ItSpIdleDetectionCallback,
           &ItSrvGlobalContext,
           DueTime,
           Period,
           0x10u) )
    {
      InitializeSRWLock(&stru_1800BD2F8);
      dword_1800BD2A8 = 3;
      xmmword_1800BD2B0 = 0;
      xmmword_1800BD2C0 = 0;
      xmmword_1800BD2D0 = 0;
      dword_1800BD2E0 = 0;
      dword_1800BD2E4 = 1;
      dword_1800BD2E8 = 72;
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      ptpcg = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        *((_QWORD *)&xmmword_1800BD2B0 + 1) = ThreadpoolCleanupGroup;
        *(_QWORD *)&xmmword_1800BD2C0 = 0;
        *(_QWORD *)&Recipient = ItSpUserDetectionCallback;
        dword_1800BD4C0 = 0;
        *((_QWORD *)&Recipient + 1) = &ItSrvGlobalContext;
        SystemSnapshot = PowerSettingRegisterNotification(
                           &GUID_GLOBAL_USER_PRESENCE,
                           2u,
                           &Recipient,
                           &RegistrationHandle);
        if ( SystemSnapshot )
        {
          RegistrationHandle = 0;
        }
        else
        {
          dword_1800BD4C4 = 0;
          *(_QWORD *)&Recipient = ItSpLPEDetectionCallback;
          *((_QWORD *)&Recipient + 1) = &ItSrvGlobalContext;
          SystemSnapshot = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 2u, &Recipient, &qword_1800BD4B0);
          if ( SystemSnapshot )
          {
            qword_1800BD4B0 = 0;
          }
          else
          {
            dword_1800BD4C8 = 0;
            if ( (int)RtlSubscribeWnfStateChangeNotification(
                        &qword_1800BD4B8,
                        WNF_XBOX_SYSTEM_CONSTRAINED_MODE_STATUS_CHANGED,
                        0,
                        ItSpConstrainedModeDetectionCallback,
                        &ItSrvGlobalContext,
                        0,
                        0,
                        0) >= 0 )
            {
              dword_1800BD4E0 = -1;
              *(_QWORD *)&Recipient = ItSpPowerSourceDetectionCallback;
              *((_QWORD *)&Recipient + 1) = &ItSrvGlobalContext;
              SystemSnapshot = PowerSettingRegisterNotification(
                                 &GUID_ACDC_POWER_SOURCE,
                                 2u,
                                 &Recipient,
                                 &qword_1800BD4D8);
              if ( SystemSnapshot )
              {
                qword_1800BD4D8 = 0;
              }
              else
              {
                dword_1800BD4F0 = 0;
                *(_QWORD *)&Recipient = ItSpBatteryThesholdCallback;
                *((_QWORD *)&Recipient + 1) = &ItSrvGlobalContext;
                SystemSnapshot = PowerSettingRegisterNotification(
                                   &GUID_BATTERY_DISCHARGE_LEVEL_1,
                                   2u,
                                   &Recipient,
                                   &qword_1800BD4E8);
                if ( SystemSnapshot )
                {
                  qword_1800BD4E8 = 0;
                }
                else
                {
                  dword_1800BD500 = 100;
                  *(_QWORD *)&Recipient = ItSpBatteryRemainingCallback;
                  *((_QWORD *)&Recipient + 1) = &ItSrvGlobalContext;
                  SystemSnapshot = PowerSettingRegisterNotification(
                                     &GUID_BATTERY_PERCENTAGE_REMAINING,
                                     2u,
                                     &Recipient,
                                     &qword_1800BD4F8);
                  if ( SystemSnapshot )
                  {
                    qword_1800BD4F8 = 0;
                  }
                  else
                  {
                    dword_1800BD510 = 0;
                    *(_QWORD *)&Recipient = ItSpConsoleDisplayStateChangeCallback;
                    *((_QWORD *)&Recipient + 1) = &ItSrvGlobalContext;
                    SystemSnapshot = PowerSettingRegisterNotification(
                                       &GUID_CONSOLE_DISPLAY_STATE,
                                       2u,
                                       &Recipient,
                                       &qword_1800BD508);
                    if ( SystemSnapshot )
                    {
                      qword_1800BD508 = 0;
                    }
                    else
                    {
                      qword_1800BD300 = 0;
                      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                      SystemSnapshot = 0;
                      _InterlockedExchange64(&qword_1800BD520, *(_QWORD *)&SystemTimeAsFileTime + 10000LL * ::DueTime);
                      v11 = SystemTimeAsFileTime;
                      _InterlockedExchange64(&qword_1800BD518, *(_QWORD *)&SystemTimeAsFileTime + 10000LL * ::DueTime);
                    }
                  }
                }
              }
            }
            else
            {
              qword_1800BD4B8 = 0;
            }
          }
        }
        return SystemSnapshot;
      }
    }
    Timer = 0;
    return GetLastError();
  }
  return SystemSnapshot;
}

```

## disassembly

```asm
0x180073254  mov     [rsp-18h+arg_10], rbx
0x180073259  mov     [rsp-18h+arg_18], rsi
0x18007325e  mov     [rsp-18h+arg_0], rcx
0x180073263  push    rbp
0x180073264  push    rdi
0x180073265  push    r14
0x180073267  mov     rbp, rsp
0x18007326a  sub     rsp, 70h
0x18007326e  xor     edi, edi
0x180073270  xorps   xmm0, xmm0
0x180073273  cmp     cs:byte_1800BD492, dil
0x18007327a  xorps   xmm1, xmm1
0x18007327d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180073281  mov     dword ptr [rbp+arg_0], edi
0x180073284  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x180073288  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18007328c  movups  [rbp+Recipient], xmm0
0x180073290  jz      short loc_1800732BF
0x180073292  cmp     cs:qword_1800BD370, rdi
0x180073299  jnz     short loc_1800732BF
0x18007329b  lea     r8, qword_1800BD370
0x1800732a2  mov     edx, 80000000h
0x1800732a7  lea     rcx, DiskPerfGuid
0x1800732ae  call    cs:__imp_WmiOpenBlock
0x1800732b4  test    eax, eax
0x1800732b6  jz      short loc_1800732BF
0x1800732b8  mov     cs:qword_1800BD370, rdi
0x1800732bf  cmp     cs:qword_1800BD388, rdi
0x1800732c6  jnz     short loc_180073347
0x1800732c8  xor     edx, edx
0x1800732ca  lea     rcx, qword_1800BD388
0x1800732d1  call    cs:__imp_PcwCreateQuery
0x1800732d7  test    eax, eax
0x1800732d9  jns     short loc_1800732EA
0x1800732db  mov     ecx, eax; Status
0x1800732dd  call    cs:__imp_RtlNtStatusToDosError
0x1800732e3  mov     ebx, eax
0x1800732e5  jmp     loc_180073698
0x1800732ea  lea     rdx, aProcessorInfor; "Processor Information"
0x1800732f1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800732f5  call    cs:__imp_RtlInitUnicodeString
0x1800732fb  lea     rdx, aTotal; "_Total"
0x180073302  lea     rcx, [rbp+var_20]; DestinationString
0x180073306  call    cs:__imp_RtlInitUnicodeString
0x18007330c  mov     rdx, cs:qword_1800BD388
0x180073313  lea     rax, [rbp+var_20]
0x180073317  mov     [rsp+70h+var_38], rdi
0x18007331c  lea     r9, [rbp+DestinationString]
0x180073320  mov     qword ptr [rsp+70h+Flags], 8000h
0x180073329  lea     rcx, [rbp+arg_0]
0x18007332d  mov     [rsp+70h+Period], 0FFFFFFFFh
0x180073335  mov     r8b, 1
0x180073338  mov     qword ptr [rsp+70h+DueTime], rax
0x18007333d  call    cs:__imp_PcwAddQueryItem
0x180073343  test    eax, eax
0x180073345  js      short loc_1800732DB
0x180073347  cmp     dword ptr cs:xmmword_1800BD1C4, 44663031h
0x180073351  lea     rsi, ?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x180073358  jnz     short loc_180073390
0x18007335a  lea     rdx, dword_1800BD390; struct _ITSRV_SYSTEM_SNAPSHOT *
0x180073361  mov     rcx, rsi; struct _ITSRV_GLOBAL_CONTEXT *
0x180073364  call    ?ItSpGetSystemSnapshot@@YAKPEAU_ITSRV_GLOBAL_CONTEXT@@PEAU_ITSRV_SYSTEM_SNAPSHOT@@@Z; ItSpGetSystemSnapshot(_ITSRV_GLOBAL_CONTEXT *,_ITSRV_SYSTEM_SNAPSHOT *)
0x180073369  mov     ebx, eax
0x18007336b  test    eax, eax
0x18007336d  jnz     loc_180073698
0x180073373  lea     rdx, dword_1800BD390; struct _ITSRV_SYSTEM_SNAPSHOT *
0x18007337a  lea     rcx, dword_1800BD3E8; struct _ITSRV_SYSTEM_SNAPSHOT *
0x180073381  call    ?ItSpCopySystemSnapshot@@YAKPEAU_ITSRV_SYSTEM_SNAPSHOT@@0@Z; ItSpCopySystemSnapshot(_ITSRV_SYSTEM_SNAPSHOT *,_ITSRV_SYSTEM_SNAPSHOT *)
0x180073386  mov     ebx, eax
0x180073388  test    eax, eax
0x18007338a  jnz     loc_180073698
0x180073390  mov     rcx, cs:qword_1800BD310; hEvent
0x180073397  call    cs:__imp_ResetEvent
0x18007339d  mov     ecx, cs:Period
0x1800733a3  lea     r8, ?ItSpIdleDetectionCallback@@YAXPEAXE@Z; Callback
0x1800733aa  cmp     cs:DueTime, ecx
0x1800733b0  mov     edx, ecx
0x1800733b2  mov     [rsp+70h+Flags], 10h; Flags
0x1800733ba  mov     r9, rsi; Parameter
0x1800733bd  cmovnb  edx, cs:DueTime
0x1800733c4  mov     [rsp+70h+Period], ecx; Period
0x1800733c8  lea     rcx, Timer; phNewTimer
0x1800733cf  mov     [rsp+70h+DueTime], edx; DueTime
0x1800733d3  xor     edx, edx; TimerQueue
0x1800733d5  call    cs:__imp_CreateTimerQueueTimer
0x1800733db  test    eax, eax
0x1800733dd  jnz     short loc_1800733F1
0x1800733df  mov     cs:Timer, rdi
0x1800733e6  call    cs:__imp_GetLastError
0x1800733ec  jmp     loc_1800732E3
0x1800733f1  lea     rcx, stru_1800BD2F8; SRWLock
0x1800733f8  call    cs:__imp_InitializeSRWLock
0x1800733fe  xorps   xmm0, xmm0
0x180073401  mov     cs:dword_1800BD2A8, 3
0x18007340b  xorps   xmm1, xmm1
0x18007340e  movdqa  cs:xmmword_1800BD2B0, xmm0
0x180073416  movdqa  cs:xmmword_1800BD2C0, xmm1
0x18007341e  movdqa  cs:xmmword_1800BD2D0, xmm0
0x180073426  mov     cs:dword_1800BD2E0, edi
0x18007342c  mov     cs:dword_1800BD2E4, 1
0x180073436  mov     cs:dword_1800BD2E8, 48h ; 'H'
0x180073440  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180073446  mov     cs:ptpcg, rax
0x18007344d  test    rax, rax
0x180073450  jz      short loc_1800733DF
0x180073452  mov     qword ptr cs:xmmword_1800BD2B0+8, rax
0x180073459  lea     r9, RegistrationHandle; RegistrationHandle
0x180073460  lea     rax, ?ItSpUserDetectionCallback@@YAKPEAXK0@Z; ItSpUserDetectionCallback(void *,ulong,void *)
0x180073467  mov     qword ptr cs:xmmword_1800BD2C0, rdi
0x18007346e  mov     r14d, 2
0x180073474  mov     qword ptr [rbp+Recipient], rax
0x180073478  mov     edx, r14d; Flags
0x18007347b  mov     cs:dword_1800BD4C0, edi
0x180073481  lea     r8, [rbp+Recipient]; Recipient
0x180073485  mov     qword ptr [rbp+Recipient+8], rsi
0x180073489  lea     rcx, GUID_GLOBAL_USER_PRESENCE; SettingGuid
0x180073490  call    cs:__imp_PowerSettingRegisterNotification
0x180073496  mov     ebx, eax
0x180073498  test    eax, eax
0x18007349a  jz      short loc_1800734A8
0x18007349c  mov     cs:RegistrationHandle, rdi
0x1800734a3  jmp     loc_180073698
0x1800734a8  lea     rax, ?ItSpLPEDetectionCallback@@YAKPEAXK0@Z; ItSpLPEDetectionCallback(void *,ulong,void *)
0x1800734af  mov     cs:dword_1800BD4C4, edi
0x1800734b5  lea     r9, qword_1800BD4B0; RegistrationHandle
0x1800734bc  mov     qword ptr [rbp+Recipient], rax
0x1800734c0  lea     r8, [rbp+Recipient]; Recipient
0x1800734c4  mov     qword ptr [rbp+Recipient+8], rsi
0x1800734c8  mov     edx, r14d; Flags
0x1800734cb  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x1800734d2  call    cs:__imp_PowerSettingRegisterNotification
0x1800734d8  mov     ebx, eax
0x1800734da  test    eax, eax
0x1800734dc  jz      short loc_1800734EA
0x1800734de  mov     cs:qword_1800BD4B0, rdi
0x1800734e5  jmp     loc_180073698
0x1800734ea  mov     rdx, cs:WNF_XBOX_SYSTEM_CONSTRAINED_MODE_STATUS_CHANGED
0x1800734f1  lea     r9, ?ItSpConstrainedModeDetectionCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ItSpConstrainedModeDetectionCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800734f8  mov     dword ptr [rsp+70h+var_38], edi
0x1800734fc  lea     rcx, qword_1800BD4B8
0x180073503  mov     [rsp+70h+Flags], edi
0x180073507  xor     r8d, r8d
0x18007350a  mov     qword ptr [rsp+70h+Period], rdi
0x18007350f  mov     qword ptr [rsp+70h+DueTime], rsi
0x180073514  mov     cs:dword_1800BD4C8, edi
0x18007351a  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180073520  test    eax, eax
0x180073522  jns     short loc_180073530
0x180073524  mov     cs:qword_1800BD4B8, rdi
0x18007352b  jmp     loc_180073698
0x180073530  lea     rax, ?ItSpPowerSourceDetectionCallback@@YAKPEAXK0@Z; ItSpPowerSourceDetectionCallback(void *,ulong,void *)
0x180073537  mov     cs:dword_1800BD4E0, 0FFFFFFFFh
0x180073541  lea     r9, qword_1800BD4D8; RegistrationHandle
0x180073548  mov     qword ptr [rbp+Recipient], rax
0x18007354c  lea     r8, [rbp+Recipient]; Recipient
0x180073550  mov     qword ptr [rbp+Recipient+8], rsi
0x180073554  mov     edx, r14d; Flags
0x180073557  lea     rcx, GUID_ACDC_POWER_SOURCE; SettingGuid
0x18007355e  call    cs:__imp_PowerSettingRegisterNotification
0x180073564  mov     ebx, eax
0x180073566  test    eax, eax
0x180073568  jz      short loc_180073576
0x18007356a  mov     cs:qword_1800BD4D8, rdi
0x180073571  jmp     loc_180073698
0x180073576  lea     rax, ?ItSpBatteryThesholdCallback@@YAKPEAXK0@Z; ItSpBatteryThesholdCallback(void *,ulong,void *)
0x18007357d  mov     cs:dword_1800BD4F0, edi
0x180073583  lea     r9, qword_1800BD4E8; RegistrationHandle
0x18007358a  mov     qword ptr [rbp+Recipient], rax
0x18007358e  lea     r8, [rbp+Recipient]; Recipient
0x180073592  mov     qword ptr [rbp+Recipient+8], rsi
0x180073596  mov     edx, r14d; Flags
0x180073599  lea     rcx, GUID_BATTERY_DISCHARGE_LEVEL_1; SettingGuid
0x1800735a0  call    cs:__imp_PowerSettingRegisterNotification
0x1800735a6  mov     ebx, eax
0x1800735a8  test    eax, eax
0x1800735aa  jz      short loc_1800735B8
0x1800735ac  mov     cs:qword_1800BD4E8, rdi
0x1800735b3  jmp     loc_180073698
0x1800735b8  lea     rax, ?ItSpBatteryRemainingCallback@@YAKPEAXK0@Z; ItSpBatteryRemainingCallback(void *,ulong,void *)
0x1800735bf  mov     cs:dword_1800BD500, 64h ; 'd'
0x1800735c9  lea     r9, qword_1800BD4F8; RegistrationHandle
0x1800735d0  mov     qword ptr [rbp+Recipient], rax
0x1800735d4  lea     r8, [rbp+Recipient]; Recipient
0x1800735d8  mov     qword ptr [rbp+Recipient+8], rsi
0x1800735dc  mov     edx, r14d; Flags
0x1800735df  lea     rcx, GUID_BATTERY_PERCENTAGE_REMAINING; SettingGuid
0x1800735e6  call    cs:__imp_PowerSettingRegisterNotification
0x1800735ec  mov     ebx, eax
0x1800735ee  test    eax, eax
0x1800735f0  jz      short loc_1800735FE
0x1800735f2  mov     cs:qword_1800BD4F8, rdi
0x1800735f9  jmp     loc_180073698
0x1800735fe  lea     rax, ?ItSpConsoleDisplayStateChangeCallback@@YAKPEAXK0@Z; ItSpConsoleDisplayStateChangeCallback(void *,ulong,void *)
0x180073605  mov     cs:dword_1800BD510, edi
0x18007360b  lea     r9, qword_1800BD508; RegistrationHandle
0x180073612  mov     qword ptr [rbp+Recipient], rax
0x180073616  lea     r8, [rbp+Recipient]; Recipient
0x18007361a  mov     qword ptr [rbp+Recipient+8], rsi
0x18007361e  mov     edx, r14d; Flags
0x180073621  lea     rcx, GUID_CONSOLE_DISPLAY_STATE; SettingGuid
0x180073628  call    cs:__imp_PowerSettingRegisterNotification
0x18007362e  mov     ebx, eax
0x180073630  test    eax, eax
0x180073632  jz      short loc_18007363D
0x180073634  mov     cs:qword_1800BD508, rdi
0x18007363b  jmp     short loc_180073698
0x18007363d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180073641  mov     cs:qword_1800BD300, rdi
0x180073648  call    cs:__imp_GetSystemTimeAsFileTime
0x18007364e  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180073651  mov     ebx, edi
0x180073653  mov     dword ptr [rbp+arg_0+4], eax
0x180073656  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180073659  mov     dword ptr [rbp+arg_0], eax
0x18007365c  mov     eax, cs:DueTime
0x180073662  imul    rcx, rax, 2710h
0x180073669  add     rcx, [rbp+arg_0]
0x18007366d  xchg    rcx, cs:qword_1800BD520
0x180073674  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180073677  mov     dword ptr [rbp+arg_0+4], eax
0x18007367a  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18007367d  mov     dword ptr [rbp+arg_0], eax
0x180073680  mov     eax, cs:DueTime
0x180073686  imul    rcx, rax, 2710h
0x18007368d  add     rcx, [rbp+arg_0]
0x180073691  xchg    rcx, cs:qword_1800BD518
0x180073698  lea     r11, [rsp+70h+var_s0]
0x18007369d  mov     eax, ebx
0x18007369f  mov     rbx, [r11+30h]
0x1800736a3  mov     rsi, [r11+38h]
0x1800736a7  mov     rsp, r11
0x1800736aa  pop     r14
0x1800736ac  pop     rdi
0x1800736ad  pop     rbp
0x1800736ae  retn
```
