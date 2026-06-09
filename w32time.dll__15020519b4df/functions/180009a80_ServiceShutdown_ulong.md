# ServiceShutdown(ulong)

- ea: `0x180009a80`
- end: `0x18000a1ff`
- name: `?ServiceShutdown@@YAXK@Z`
- size: `1919`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180030cac`

## callees

- `0x180009a80`
- `0x18000a210`
- `0x18000a7e0`
- `0x18000b200`
- `0x18000b260`
- `0x18000b494`
- `0x18000b5f4`
- `0x180010b74`
- `0x180018138`
- `0x18001d9a0`
- `0x18002a940`
- `0x18002fce4`
- `0x180030628`
- `0x180030fec`
- `0x180033e2c`
- `0x180039dd4`
- `0x180039ff8`
- `0x18003d270`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009e51`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009e51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009e7a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009e7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a03d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a03d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180009e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180009e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009eb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009eb5`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180009e1a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180009e1a`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180009d23`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180009d23`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009b7b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009ceb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009b7b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009ceb`
- `ntdll!RtlNtStatusToDosError` at `0x18000a071`
- `ntdll!RtlNtStatusToDosError` at `0x18000a071`
- `WS2_32!__imp_closesocket` at `0x180009efe`
- `WS2_32!__imp_closesocket` at `0x18000a16a`
- `WS2_32!__imp_closesocket` at `0x180009efe`
- `WS2_32!__imp_closesocket` at `0x18000a16a`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x180009c88`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x180009c88`
- `USERENV!UnregisterGPNotification` at `0x180009f16`
- `USERENV!UnregisterGPNotification` at `0x180009f16`

## string_xrefs

- `0x18000a0c4`: `Service shutdown initiated with exit code: %d.\n`
- `0x18000a1d8`: `Exiting ServiceShutdown\n`

## pseudocode

```c
void __fastcall ServiceShutdown(DWORD a1)
{
  signed int v2; // eax
  void *v3; // r8
  unsigned int i; // ebx
  struct SERVICE_STATUS_HANDLE__ **v5; // rdi
  struct SERVICE_STATUS_HANDLE__ *v6; // rcx
  int v7; // eax
  bool v8; // sf
  signed int ClockRate; // eax
  NTSTATUS v10; // eax
  signed int v11; // eax
  __int64 v12; // rdx
  unsigned __int64 v13; // rdi
  signed int v14; // eax
  int v15; // eax
  bool v16; // sf
  __int64 v17; // rbx
  __int64 v18; // rdi
  signed int v19; // eax
  signed int v20; // eax
  int LastError; // eax
  bool v22; // sf
  int v23; // eax
  bool v24; // sf
  int v25; // eax
  bool v26; // sf
  bool v27; // sf
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  signed int v31; // eax
  DWORD ExitCode; // [rsp+30h] [rbp-49h] BYREF
  bool v33; // [rsp+34h] [rbp-45h] BYREF
  __int64 v34; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v35[10]; // [rsp+40h] [rbp-39h]
  _OWORD v36[2]; // [rsp+90h] [rbp+17h] BYREF

  ExitCode = a1;
  if ( byte_1800A4689 == 1 )
  {
    v30 = W32TmStopRpcServer();
    if ( v30 < 0 && (ExitCode & 0x80000000) == 0 )
      ExitCode = v30;
  }
  v35[0] = &qword_1800A3760;
  v35[1] = &qword_1800A3768;
  v35[2] = &qword_1800A37A0;
  v35[3] = &qword_1800A3778;
  v35[4] = &qword_1800A3780;
  v35[5] = &qword_1800A3770;
  v35[6] = &qword_1800A3788;
  v35[7] = &qword_1800A3790;
  v35[8] = &qword_1800A3798;
  v35[9] = &qword_1800A37A8;
  if ( (unsigned __int8)FileLogAllowEntry(64) )
    FileLogAdd(L"Service shutdown initiated with exit code: %d.\n", a1);
  v2 = MySetServiceStatus(3u, 0x3E8u, 0);
  if ( v2 < 0 && (ExitCode & 0x80000000) == 0 )
    ExitCode = v2;
  for ( i = 0; i < 0xA; ++i )
  {
    v5 = (struct SERVICE_STATUS_HANDLE__ **)v35[i];
    v6 = *v5;
    if ( *v5 )
    {
      if ( !UnregisterWaitEx(v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        LastError = GetLastError();
        v22 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v22 = LastError < 0;
        }
        if ( v22 && (ExitCode & 0x80000000) == 0 )
          ExitCode = LastError;
      }
      v6 = g_servicestatushandle;
      *v5 = 0;
      if ( v6 )
      {
        ++HIDWORD(qword_1800A3620);
        *(_QWORD *)&g_servicestatus.dwWin32ExitCode = 0;
        *(_QWORD *)&g_servicestatus.dwCurrentState = 3;
        g_servicestatus.dwServiceType = 32;
        dword_1800A3628 = 1000;
        v36[0] = *(_OWORD *)&g_servicestatus.dwServiceType;
        *(_OWORD *)((char *)v36 + 12) = *(_OWORD *)&g_servicestatus.dwWin32ExitCode;
        if ( !(unsigned int)((__int64 (__fastcall *)(struct SERVICE_STATUS_HANDLE__ *, _OWORD *))fnW32TmSetServiceStatus)(
                              v6,
                              v36) )
        {
          v7 = GetLastError();
          v8 = v7 < 0;
          if ( v7 > 0 )
          {
            v7 = (unsigned __int16)v7 | 0x80070000;
            v8 = v7 < 0;
          }
          if ( v8 && (ExitCode & 0x80000000) == 0 )
            ExitCode = v7;
        }
      }
    }
  }
  if ( lpCriticalSection )
  {
    myDeleteTimerQueueTimer(v6, lpCriticalSection, v3);
    lpCriticalSection = 0;
  }
  if ( qword_1800A4640 )
  {
    myDeleteTimerQueueTimer(v6, qword_1800A4640, v3);
    qword_1800A4640 = 0;
  }
  if ( qword_1800A4650 )
  {
    myDeleteTimerQueueTimer(v6, qword_1800A4650, v3);
    qword_1800A4650 = 0;
    byte_1800A4648 = 0;
  }
  if ( hEvent )
  {
    if ( !SetEvent(hEvent) )
    {
      v23 = GetLastError();
      v24 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v24 = v23 < 0;
      }
      if ( v24 && (ExitCode & 0x80000000) == 0 )
        ExitCode = v23;
      goto LABEL_21;
    }
    if ( !hThread )
      goto LABEL_21;
    if ( WaitForSingleObject(hThread, 0xFFFFFFFF) == -1 )
    {
      v25 = GetLastError();
      v26 = v25 < 0;
      if ( v25 > 0 )
      {
        v25 = (unsigned __int16)v25 | 0x80070000;
        v26 = v25 < 0;
      }
      if ( !v26 || (ExitCode & 0x80000000) != 0 )
        goto LABEL_47;
    }
    else
    {
      if ( GetExitCodeThread(hThread, &ExitCode) )
        goto LABEL_47;
      v25 = GetLastError();
      v27 = v25 < 0;
      if ( v25 > 0 )
      {
        v25 = (unsigned __int16)v25 | 0x80070000;
        v27 = v25 < 0;
      }
      if ( !v27 || (ExitCode & 0x80000000) != 0 )
        goto LABEL_47;
    }
    ExitCode = v25;
LABEL_47:
    CloseHandle(hThread);
    hThread = 0;
  }
LABEL_21:
  ClockRate = SaveLastClockRate();
  if ( ClockRate < 0 && (ExitCode & 0x80000000) == 0 )
    ExitCode = ClockRate;
  if ( qword_1800A42F0 )
  {
    v17 = *(_QWORD *)qword_1800A42F0;
    if ( *(_QWORD *)qword_1800A42F0 )
    {
      do
      {
        v18 = *(_QWORD *)(v17 + 24);
        v33 = 0;
        v19 = MySetServiceStatus(3u, 0x3E8u, 0);
        if ( v19 < 0 && (ExitCode & 0x80000000) == 0 )
          ExitCode = v19;
        v20 = RemoveProviderFromList((struct TimeProvider *)v17, 0, &v33);
        if ( v20 < 0 && (ExitCode & 0x80000000) == 0 )
          ExitCode = v20;
        v17 = v18;
      }
      while ( v18 );
    }
  }
  v10 = LsaUnregisterPolicyChangeNotification(PolicyNotifyServerRoleInformation, NotificationEventHandle);
  if ( v10 )
  {
    v28 = RtlNtStatusToDosError(v10);
    v29 = v28 < 0;
    if ( v28 > 0 )
    {
      v28 = (unsigned __int16)v28 | 0x80070000;
      v29 = v28 < 0;
    }
    if ( v29 && (ExitCode & 0x80000000) == 0 )
      ExitCode = v28;
  }
  v11 = ShutdownNetlogonServiceBits();
  if ( v11 < 0 && (ExitCode & 0x80000000) == 0 )
    ExitCode = v11;
  if ( byte_1800A45AA == 1 )
  {
    if ( qword_1800A37B8 )
      closesocket(qword_1800A37B8);
    if ( s )
      closesocket(s);
  }
  if ( HIBYTE(word_1800A45A8) == 1 )
  {
    v14 = CloseSocketLayer();
    if ( v14 < 0 && (ExitCode & 0x80000000) == 0 )
      ExitCode = v14;
  }
  if ( byte_1800A45AB == 1 && !UnregisterGPNotification(qword_1800A36E8) )
  {
    v15 = GetLastError();
    v16 = v15 < 0;
    if ( v15 > 0 )
    {
      v15 = (unsigned __int16)v15 | 0x80070000;
      v16 = v15 < 0;
    }
    if ( v16 && (ExitCode & 0x80000000) == 0 )
      ExitCode = v15;
  }
  if ( (_BYTE)word_1800A45A8 == 1 )
  {
    v31 = StartOrStopTimeSlipNotification(0);
    if ( v31 < 0 && (ExitCode & 0x80000000) == 0 )
      ExitCode = v31;
  }
  if ( WaitHandle )
  {
    UnregisterWaitEx(WaitHandle, 0);
    WaitHandle = 0;
  }
  if ( RegistrationHandle )
  {
    PowerSettingUnregisterNotification(RegistrationHandle);
    RegistrationHandle = 0;
  }
  if ( dword_1800A5288 )
  {
    CleanupState();
    dword_1800A5288 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(135) )
      FileLogAdd(L"W32time perf counters uninitialized.\n");
  }
  v34 = 0;
  GetSystemTimePreciseAsFileTime(&v34, v12);
  v13 = (unsigned int)v34 + ((unsigned __int64)HIDWORD(v34) << 32);
  EnterCriticalSection(&stru_1800A4610);
  if ( (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24) < dword_1800A5278 )
    ++dword_1800A5284;
  dword_1800A5278 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  LeaveCriticalSection(&stru_1800A4610);
  LogEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_SHUTDOWN, L"Tie", v13);
  if ( (unsigned __int8)FileLogAllowEntry(64) )
    FileLogAdd(L"Exiting ServiceShutdown\n");
  FileLogEnd();
  W32TimeUnregisterEvents();
  FreeGlobalState();
  FreeShutdownState();
  if ( g_servicestatushandle )
    MySetServiceStatus(1u, 0, (unsigned __int16)ExitCode);
}

```

## disassembly

```asm
0x180009a80  mov     [rsp-8+arg_8], rbx
0x180009a85  mov     [rsp-8+arg_10], rsi
0x180009a8a  push    rbp
0x180009a8b  push    rdi
0x180009a8c  push    r14
0x180009a8e  lea     rbp, [rsp-47h]
0x180009a93  sub     rsp, 0C0h
0x180009a9a  mov     rax, cs:__security_cookie
0x180009aa1  xor     rax, rsp
0x180009aa4  mov     [rbp+57h+var_20], rax
0x180009aa8  cmp     cs:byte_1800A4689, 1
0x180009aaf  mov     esi, ecx
0x180009ab1  mov     [rbp+57h+ExitCode], ecx
0x180009ab4  jz      loc_18000A0A3
0x180009aba  lea     rax, qword_1800A3760
0x180009ac1  mov     ecx, 40h ; '@'
0x180009ac6  mov     [rbp+57h+var_90], rax
0x180009aca  lea     rax, qword_1800A3768
0x180009ad1  mov     [rbp+57h+var_88], rax
0x180009ad5  lea     rax, qword_1800A37A0
0x180009adc  mov     [rbp+57h+var_80], rax
0x180009ae0  lea     rax, qword_1800A3778
0x180009ae7  mov     [rbp+57h+var_78], rax
0x180009aeb  lea     rax, qword_1800A3780
0x180009af2  mov     [rbp+57h+var_70], rax
0x180009af6  lea     rax, qword_1800A3770
0x180009afd  mov     [rbp+57h+var_68], rax
0x180009b01  lea     rax, qword_1800A3788
0x180009b08  mov     [rbp+57h+var_60], rax
0x180009b0c  lea     rax, qword_1800A3790
0x180009b13  mov     [rbp+57h+var_58], rax
0x180009b17  lea     rax, qword_1800A3798
0x180009b1e  mov     [rbp+57h+var_50], rax
0x180009b22  lea     rax, qword_1800A37A8
0x180009b29  mov     [rbp+57h+var_48], rax
0x180009b2d  call    FileLogAllowEntry
0x180009b32  test    al, al
0x180009b34  jnz     loc_18000A0C2
0x180009b3a  xor     r8d, r8d; unsigned int
0x180009b3d  mov     edx, 3E8h; unsigned int
0x180009b42  mov     ecx, 3; unsigned int
0x180009b47  call    ?MySetServiceStatus@@YAJKKK@Z; MySetServiceStatus(ulong,ulong,ulong)
0x180009b4c  test    eax, eax
0x180009b4e  js      loc_18000A0D5
0x180009b54  xor     r14d, r14d
0x180009b57  mov     ebx, r14d
0x180009b5a  nop     word ptr [rax+rax+00h]
0x180009b60  movsxd  rax, ebx
0x180009b63  mov     rdi, [rbp+rax*8+57h+var_90]
0x180009b68  mov     rcx, [rdi]; WaitHandle
0x180009b6b  test    rcx, rcx
0x180009b6e  jz      loc_180009C14
0x180009b74  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180009b7b  call    cs:__imp_UnregisterWaitEx
0x180009b82  nop     dword ptr [rax+rax+00h]
0x180009b87  test    eax, eax
0x180009b89  jz      loc_180009FAD
0x180009b8f  mov     rcx, cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x180009b96  mov     [rdi], r14
0x180009b99  test    rcx, rcx
0x180009b9c  jz      short loc_180009C14
0x180009b9e  inc     dword ptr cs:qword_1800A3620+4
0x180009ba4  lea     rdx, [rbp+57h+var_40]
0x180009ba8  mov     rax, cs:?fnW32TmSetServiceStatus@@3P6AHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@ZEA; int (*fnW32TmSetServiceStatus)(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x180009baf  mov     qword ptr cs:?g_servicestatus@@3U_SERVICE_STATUS@@A+0Ch, r14; _SERVICE_STATUS g_servicestatus
0x180009bb6  mov     qword ptr cs:?g_servicestatus@@3U_SERVICE_STATUS@@A+4, 3; _SERVICE_STATUS g_servicestatus
0x180009bc1  mov     dword ptr cs:?g_servicestatus@@3U_SERVICE_STATUS@@A, 20h ; ' '; _SERVICE_STATUS g_servicestatus
0x180009bcb  movups  xmm0, cs:?g_servicestatus@@3U_SERVICE_STATUS@@A; _SERVICE_STATUS g_servicestatus
0x180009bd2  mov     cs:dword_1800A3628, 3E8h
0x180009bdc  movups  xmm1, cs:?g_servicestatus@@3U_SERVICE_STATUS@@A+0Ch; _SERVICE_STATUS g_servicestatus
0x180009be3  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180009be7  movups  xmmword ptr [rbp+57h+var_40+0Ch], xmm1
0x180009beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf0  test    eax, eax
0x180009bf2  jnz     short loc_180009C14
0x180009bf4  call    cs:__imp_GetLastError
0x180009bfb  nop     dword ptr [rax+rax+00h]
0x180009c00  test    eax, eax
0x180009c02  jle     short loc_180009C0E
0x180009c04  movzx   eax, ax
0x180009c07  or      eax, 80070000h
0x180009c0c  test    eax, eax
0x180009c0e  js      loc_18000A0E7
0x180009c14  inc     ebx
0x180009c16  cmp     ebx, 0Ah
0x180009c19  jb      loc_180009B60
0x180009c1f  mov     rdx, cs:lpCriticalSection; void *
0x180009c26  test    rdx, rdx
0x180009c29  jnz     loc_18000A0F9
0x180009c2f  mov     rdx, cs:qword_1800A4640; void *
0x180009c36  test    rdx, rdx
0x180009c39  jnz     loc_180009ECD
0x180009c3f  mov     rdx, cs:qword_1800A4650; void *
0x180009c46  test    rdx, rdx
0x180009c49  jnz     loc_18000A10A
0x180009c4f  mov     rcx, cs:hEvent; hEvent
0x180009c56  test    rcx, rcx
0x180009c59  jnz     loc_180009E51
0x180009c5f  call    ?SaveLastClockRate@@YAJXZ; SaveLastClockRate(void)
0x180009c64  test    eax, eax
0x180009c66  js      loc_18000A122
0x180009c6c  mov     rax, cs:qword_1800A42F0
0x180009c73  test    rax, rax
0x180009c76  jnz     loc_180009F5C
0x180009c7c  mov     rdx, cs:NotificationEventHandle; NotificationEventHandle
0x180009c83  mov     ecx, 3; InformationClass
0x180009c88  call    cs:__imp_LsaUnregisterPolicyChangeNotification
0x180009c8f  nop     dword ptr [rax+rax+00h]
0x180009c94  test    eax, eax
0x180009c96  jnz     loc_18000A06F
0x180009c9c  call    ?ShutdownNetlogonServiceBits@@YAJXZ; ShutdownNetlogonServiceBits(void)
0x180009ca1  test    eax, eax
0x180009ca3  js      loc_18000A158
0x180009ca9  cmp     cs:byte_1800A45AA, 1
0x180009cb0  jz      loc_180009EDE
0x180009cb6  cmp     byte ptr cs:word_1800A45A8+1, 1
0x180009cbd  jz      loc_180009E32
0x180009cc3  cmp     cs:byte_1800A45AB, 1
0x180009cca  jz      loc_180009F0F
0x180009cd0  cmp     byte ptr cs:word_1800A45A8, 1
0x180009cd7  jz      loc_18000A17B
0x180009cdd  mov     rcx, cs:WaitHandle; WaitHandle
0x180009ce4  test    rcx, rcx
0x180009ce7  jz      short loc_180009CFE
0x180009ce9  xor     edx, edx; CompletionEvent
0x180009ceb  call    cs:__imp_UnregisterWaitEx
0x180009cf2  nop     dword ptr [rax+rax+00h]
0x180009cf7  mov     cs:WaitHandle, r14
0x180009cfe  mov     rcx, cs:RegistrationHandle; RegistrationHandle
0x180009d05  test    rcx, rcx
0x180009d08  jnz     loc_180009E1A
0x180009d0e  cmp     cs:dword_1800A5288, r14d
0x180009d15  jnz     loc_18000A19C
0x180009d1b  lea     rcx, [rbp+57h+var_98]
0x180009d1f  mov     [rbp+57h+var_98], r14
0x180009d23  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180009d2a  nop     dword ptr [rax+rax+00h]
0x180009d2f  mov     eax, dword ptr [rbp+57h+var_98]
0x180009d32  lea     rcx, stru_1800A4610; lpCriticalSection
0x180009d39  mov     edi, dword ptr [rbp+57h+var_98+4]
0x180009d3c  shl     rdi, 20h
0x180009d40  add     rdi, rax
0x180009d43  call    cs:__imp_EnterCriticalSection
0x180009d4a  nop     dword ptr [rax+rax+00h]
0x180009d4f  mov     eax, 7FFE0320h
0x180009d54  mov     rax, [rax]
0x180009d57  mov     ecx, ds:7FFE0004h
0x180009d5e  imul    rcx, rax
0x180009d62  mov     eax, cs:dword_1800A5284
0x180009d68  shr     rcx, 18h
0x180009d6c  cmp     ecx, cs:dword_1800A5278
0x180009d72  jb      loc_18000A1CB
0x180009d78  mov     ebx, eax
0x180009d7a  mov     eax, ecx
0x180009d7c  mov     cs:dword_1800A5278, ecx
0x180009d82  lea     rcx, stru_1800A4610; lpCriticalSection
0x180009d89  shl     rbx, 20h
0x180009d8d  add     rbx, rax
0x180009d90  call    cs:__imp_LeaveCriticalSection
0x180009d97  nop     dword ptr [rax+rax+00h]
0x180009d9c  mov     r9, rdi
0x180009d9f  mov     [rsp+0D0h+var_A8], esi
0x180009da3  lea     r8, aTie; "Tie"
0x180009daa  mov     [rsp+0D0h+var_B0], rbx
0x180009daf  lea     rdx, W32TIME_OPS_SHUTDOWN
0x180009db6  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180009dbd  call    LogEvent
0x180009dc2  mov     ecx, 40h ; '@'
0x180009dc7  call    FileLogAllowEntry
0x180009dcc  test    al, al
0x180009dce  jnz     loc_18000A1D8
0x180009dd4  call    FileLogEnd
0x180009dd9  call    ?W32TimeUnregisterEvents@@YAXXZ; W32TimeUnregisterEvents(void)
0x180009dde  call    ?FreeGlobalState@@YAXXZ; FreeGlobalState(void)
0x180009de3  call    ?FreeShutdownState@@YAXXZ; FreeShutdownState(void)
0x180009de8  cmp     cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, r14; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x180009def  jnz     loc_18000A1E9
0x180009df5  mov     rcx, [rbp+57h+var_20]
0x180009df9  xor     rcx, rsp; StackCookie
0x180009dfc  call    __security_check_cookie
0x180009e01  lea     r11, [rsp+0D0h+var_10]
0x180009e09  mov     rbx, [r11+28h]
0x180009e0d  mov     rsi, [r11+30h]
0x180009e11  mov     rsp, r11
0x180009e14  pop     r14
0x180009e16  pop     rdi
0x180009e17  pop     rbp
0x180009e18  retn
0x180009e1a  call    cs:__imp_PowerSettingUnregisterNotification
0x180009e21  nop     dword ptr [rax+rax+00h]
0x180009e26  mov     cs:RegistrationHandle, r14
0x180009e2d  jmp     loc_180009D0E
0x180009e32  call    ?CloseSocketLayer@@YAJXZ; CloseSocketLayer(void)
0x180009e37  test    eax, eax
0x180009e39  jns     loc_180009CC3
0x180009e3f  cmp     [rbp+57h+ExitCode], r14d
0x180009e43  jl      loc_180009CC3
0x180009e49  mov     [rbp+57h+ExitCode], eax
0x180009e4c  jmp     loc_180009CC3
0x180009e51  call    cs:__imp_SetEvent
0x180009e58  nop     dword ptr [rax+rax+00h]
0x180009e5d  test    eax, eax
0x180009e5f  jz      loc_180009FDF
0x180009e65  mov     rcx, cs:hThread; hHandle
0x180009e6c  test    rcx, rcx
0x180009e6f  jz      loc_180009C5F
0x180009e75  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180009e7a  call    cs:__imp_WaitForSingleObject
0x180009e81  nop     dword ptr [rax+rax+00h]
0x180009e86  cmp     eax, 0FFFFFFFFh
0x180009e89  jz      loc_18000A011
0x180009e8f  mov     rcx, cs:hThread; hThread
0x180009e96  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x180009e9a  call    cs:__imp_GetExitCodeThread
0x180009ea1  nop     dword ptr [rax+rax+00h]
0x180009ea6  test    eax, eax
0x180009ea8  jz      loc_18000A03D
0x180009eae  mov     rcx, cs:hThread; hObject
0x180009eb5  call    cs:__imp_CloseHandle
0x180009ebc  nop     dword ptr [rax+rax+00h]
0x180009ec1  mov     cs:hThread, r14
0x180009ec8  jmp     loc_180009C5F
0x180009ecd  call    ?myDeleteTimerQueueTimer@@YAXPEAX00@Z; myDeleteTimerQueueTimer(void *,void *,void *)
0x180009ed2  mov     cs:qword_1800A4640, r14
0x180009ed9  jmp     loc_180009C3F
0x180009ede  mov     rcx, cs:qword_1800A37B8; s
0x180009ee5  test    rcx, rcx
0x180009ee8  jnz     loc_18000A16A
0x180009eee  mov     rcx, cs:s; s
0x180009ef5  test    rcx, rcx
0x180009ef8  jz      loc_180009CB6
0x180009efe  call    cs:__imp_closesocket
0x180009f05  nop     dword ptr [rax+rax+00h]
0x180009f0a  jmp     loc_180009CB6
0x180009f0f  mov     rcx, cs:qword_1800A36E8; hEvent
0x180009f16  call    cs:__imp_UnregisterGPNotification
0x180009f1d  nop     dword ptr [rax+rax+00h]
0x180009f22  test    eax, eax
0x180009f24  jnz     loc_180009CD0
0x180009f2a  call    cs:__imp_GetLastError
0x180009f31  nop     dword ptr [rax+rax+00h]
0x180009f36  test    eax, eax
0x180009f38  jle     short loc_180009F44
0x180009f3a  movzx   eax, ax
0x180009f3d  or      eax, 80070000h
0x180009f42  test    eax, eax
0x180009f44  jns     loc_180009CD0
0x180009f4a  cmp     [rbp+57h+ExitCode], r14d
0x180009f4e  jl      loc_180009CD0
0x180009f54  mov     [rbp+57h+ExitCode], eax
0x180009f57  jmp     loc_180009CD0
0x180009f5c  mov     rbx, [rax]
0x180009f5f  test    rbx, rbx
0x180009f62  jz      loc_180009C7C
0x180009f68  mov     rdi, [rbx+18h]
0x180009f6c  xor     r8d, r8d; unsigned int
0x180009f6f  mov     edx, 3E8h; unsigned int
0x180009f74  mov     [rbp+57h+var_9C], r14b
0x180009f78  mov     ecx, 3; unsigned int
0x180009f7d  call    ?MySetServiceStatus@@YAJKKK@Z; MySetServiceStatus(ulong,ulong,ulong)
0x180009f82  test    eax, eax
0x180009f84  js      loc_18000A134
0x180009f8a  lea     r8, [rbp+57h+var_9C]; bool *
0x180009f8e  xor     edx, edx; bool
0x180009f90  mov     rcx, rbx; struct TimeProvider *
0x180009f93  call    ?RemoveProviderFromList@@YAJPEAUTimeProvider@@_NPEA_N@Z; RemoveProviderFromList(TimeProvider *,bool,bool *)
0x180009f98  test    eax, eax
0x180009f9a  js      loc_18000A146
0x180009fa0  mov     rbx, rdi
0x180009fa3  test    rdi, rdi
0x180009fa6  jnz     short loc_180009F68
0x180009fa8  jmp     loc_180009C7C
0x180009fad  call    cs:__imp_GetLastError
0x180009fb4  nop     dword ptr [rax+rax+00h]
0x180009fb9  test    eax, eax
0x180009fbb  jle     short loc_180009FC7
0x180009fbd  movzx   eax, ax
0x180009fc0  or      eax, 80070000h
0x180009fc5  test    eax, eax
0x180009fc7  jns     loc_180009B8F
0x180009fcd  cmp     [rbp+57h+ExitCode], r14d
0x180009fd1  jl      loc_180009B8F
0x180009fd7  mov     [rbp+57h+ExitCode], eax
0x180009fda  jmp     loc_180009B8F
0x180009fdf  call    cs:__imp_GetLastError
0x180009fe6  nop     dword ptr [rax+rax+00h]
0x180009feb  test    eax, eax
0x180009fed  jle     short loc_180009FF9
0x180009fef  movzx   eax, ax
0x180009ff2  or      eax, 80070000h
0x180009ff7  test    eax, eax
0x180009ff9  jns     loc_180009C5F
0x180009fff  cmp     [rbp+57h+ExitCode], r14d
0x18000a003  jl      loc_180009C5F
0x18000a009  mov     [rbp+57h+ExitCode], eax
0x18000a00c  jmp     loc_180009C5F
0x18000a011  call    cs:__imp_GetLastError
0x18000a018  nop     dword ptr [rax+rax+00h]
0x18000a01d  test    eax, eax
0x18000a01f  jle     short loc_18000A02B
  ... truncated ...
```
