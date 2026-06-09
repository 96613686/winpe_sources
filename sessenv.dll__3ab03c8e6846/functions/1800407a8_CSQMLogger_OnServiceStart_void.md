# CSQMLogger::OnServiceStart(void)

- ea: `0x1800407a8`
- end: `0x180040971`
- name: `?OnServiceStart@CSQMLogger@@QEAAJXZ`
- size: `457`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800404a0`

## callees

- `0x180003f30`
- `0x1800145d4`
- `0x180014f24`
- `0x180031e28`
- `0x180040668`
- `0x180040708`
- `0x1800407a8`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x1800408eb`
- `ntdll!WinSqmIsOptedIn` at `0x1800408eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004093d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004093d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800407d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800407d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800408bc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180040933`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800408bc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180040933`

## string_xrefs

- `0x180040802`: `CreateTimerQueue failed: 0x%x in %s`
- `0x1800408df`: `CreateTimerQueueTimer failed: 0x%x in %s`
- `0x18004080c`: `CSQMLogger::OnServiceStart`
- `0x180040879`: `CSQMUtil::ProcessTmpTsDataFile() failed:Couldn't move the tmp file to upload data directory: 0x%x`
- `0x180040956`: `CreateTimerQueueTimer for m_RdshSqmTimerQueueTimer failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSQMLogger::OnServiceStart(PVOID Parameter)
{
  signed int v2; // ebx
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  const char *v5; // rdx
  int inited; // eax
  int v7; // eax
  signed int v8; // eax
  signed int v9; // eax

  if ( (unsigned int)IsTSInAppServerMode() )
  {
    TimerQueue = CreateTimerQueue();
    *((_QWORD *)Parameter + 199) = TimerQueue;
    if ( TimerQueue )
      goto LABEL_10;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_10:
      CSQMLogger::m_CollectSqmDataToFileInterval = GetInterval();
      if ( !CSQMLogger::m_CollectSqmDataToFileInterval )
        CSQMLogger::m_CollectSqmDataToFileInterval = 1800000;
      CSQMLogger::m_SqmSaveDataToFileInterval = GetSQMSaveDataInterval();
      if ( !CSQMLogger::m_SqmSaveDataToFileInterval )
        CSQMLogger::m_SqmSaveDataToFileInterval = 43200000;
      inited = CSQMUtil::InitSQMSession();
      v2 = inited;
      if ( inited < 0 )
      {
        _DbgPrintMessage(
          8,
          "CSQMUtil::InitSQMSession failed: 0x%x in %s",
          (unsigned int)inited,
          "CSQMLogger::OnServiceStart");
        return (unsigned int)v2;
      }
      v7 = CSQMUtil::MoveOldTmpTsDataFileToUploadDir();
      v2 = v7;
      if ( v7 < 0 )
        _DbgPrintMessage(
          8,
          "CSQMUtil::ProcessTmpTsDataFile() failed:Couldn't move the tmp file to upload data directory: 0x%x",
          v7);
      if ( CreateTimerQueueTimer(
             (PHANDLE)Parameter + 200,
             *((HANDLE *)Parameter + 199),
             CSQMLogger::staticTSPerfLogSQM,
             Parameter,
             0,
             CSQMLogger::m_CollectSqmDataToFileInterval,
             0x20u) )
      {
        goto LABEL_34;
      }
      v8 = GetLastError();
      v2 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_34:
        if ( !(unsigned int)WinSqmIsOptedIn() )
        {
          _DbgPrintMessage(1, "WinSqmIsOptedIn() returned FALSE( not allowed to collect user data)");
          return (unsigned int)v2;
        }
        if ( CreateTimerQueueTimer(
               (PHANDLE)Parameter + 201,
               *((HANDLE *)Parameter + 199),
               CSQMLogger::staticRdshLogSQM,
               Parameter,
               0x36EE80u,
               0x36EE80u,
               0x20u) )
        {
          return 0;
        }
        v9 = GetLastError();
        v2 = v9;
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        if ( v2 >= 0 )
          return 0;
        v5 = "CreateTimerQueueTimer for m_RdshSqmTimerQueueTimer failed: 0x%x in %s";
      }
      else
      {
        v5 = "CreateTimerQueueTimer failed: 0x%x in %s";
      }
    }
    else
    {
      v5 = "CreateTimerQueue failed: 0x%x in %s";
    }
    _DbgPrintMessage(8, v5, (unsigned int)v2, "CSQMLogger::OnServiceStart");
    return (unsigned int)v2;
  }
  _DbgPrintMessage(1, "Not in TS App Server Mode; exiting SQM logger");
  return (unsigned int)-2147024846;
}

```

## disassembly

```asm
0x1800407a8  mov     [rsp+arg_0], rbx
0x1800407ad  push    rdi
0x1800407ae  sub     rsp, 40h
0x1800407b2  mov     rdi, rcx
0x1800407b5  call    ?IsTSInAppServerMode@@YAHXZ; IsTSInAppServerMode(void)
0x1800407ba  test    eax, eax
0x1800407bc  jnz     short loc_1800407D7
0x1800407be  lea     rdx, aNotInTsAppServ_0; "Not in TS App Server Mode; exiting SQM "...
0x1800407c5  lea     ecx, [rax+1]; int
0x1800407c8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800407cd  mov     ebx, 80070032h
0x1800407d2  jmp     loc_180040964
0x1800407d7  call    cs:__imp_CreateTimerQueue
0x1800407dd  mov     [rdi+638h], rax
0x1800407e4  test    rax, rax
0x1800407e7  jnz     short loc_180040822
0x1800407e9  call    cs:__imp_GetLastError
0x1800407ef  mov     ebx, eax
0x1800407f1  test    eax, eax
0x1800407f3  jle     short loc_1800407FE
0x1800407f5  movzx   ebx, ax
0x1800407f8  or      ebx, 80070000h
0x1800407fe  test    ebx, ebx
0x180040800  jns     short loc_180040822
0x180040802  lea     rdx, aCreatetimerque_2; "CreateTimerQueue failed: 0x%x in %s"
0x180040809  mov     r8d, ebx
0x18004080c  lea     r9, aCsqmloggerOnse; "CSQMLogger::OnServiceStart"
0x180040813  mov     ecx, 8; int
0x180040818  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004081d  jmp     loc_180040964
0x180040822  call    ?GetInterval@@YAKXZ; GetInterval(void)
0x180040827  mov     cs:?m_CollectSqmDataToFileInterval@CSQMLogger@@0HA, eax; int CSQMLogger::m_CollectSqmDataToFileInterval
0x18004082d  test    eax, eax
0x18004082f  jnz     short loc_18004083B
0x180040831  mov     cs:?m_CollectSqmDataToFileInterval@CSQMLogger@@0HA, 1B7740h; int CSQMLogger::m_CollectSqmDataToFileInterval
0x18004083b  call    ?GetSQMSaveDataInterval@@YAKXZ; GetSQMSaveDataInterval(void)
0x180040840  mov     cs:?m_SqmSaveDataToFileInterval@CSQMLogger@@0HA, eax; int CSQMLogger::m_SqmSaveDataToFileInterval
0x180040846  test    eax, eax
0x180040848  jnz     short loc_180040854
0x18004084a  mov     cs:?m_SqmSaveDataToFileInterval@CSQMLogger@@0HA, 2932E00h; int CSQMLogger::m_SqmSaveDataToFileInterval
0x180040854  call    ?InitSQMSession@CSQMUtil@@SAJXZ; CSQMUtil::InitSQMSession(void)
0x180040859  mov     ebx, eax
0x18004085b  test    eax, eax
0x18004085d  jns     short loc_18004086B
0x18004085f  mov     r8d, eax
0x180040862  lea     rdx, aCsqmutilInitsq_0; "CSQMUtil::InitSQMSession failed: 0x%x i"...
0x180040869  jmp     short loc_18004080C
0x18004086b  call    ?MoveOldTmpTsDataFileToUploadDir@CSQMUtil@@SAJXZ; CSQMUtil::MoveOldTmpTsDataFileToUploadDir(void)
0x180040870  mov     ebx, eax
0x180040872  test    eax, eax
0x180040874  jns     short loc_18004088A
0x180040876  mov     r8d, eax
0x180040879  lea     rdx, aCsqmutilProces; "CSQMUtil::ProcessTmpTsDataFile() failed"...
0x180040880  mov     ecx, 8; int
0x180040885  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004088a  mov     eax, cs:?m_CollectSqmDataToFileInterval@CSQMLogger@@0HA; int CSQMLogger::m_CollectSqmDataToFileInterval
0x180040890  lea     rcx, [rdi+640h]; phNewTimer
0x180040897  mov     rdx, [rdi+638h]; TimerQueue
0x18004089e  lea     r8, ?staticTSPerfLogSQM@CSQMLogger@@CAXPEAXE@Z; Callback
0x1800408a5  mov     [rsp+48h+Flags], 20h ; ' '; Flags
0x1800408ad  mov     r9, rdi; Parameter
0x1800408b0  mov     [rsp+48h+Period], eax; Period
0x1800408b4  mov     [rsp+48h+DueTime], 0; DueTime
0x1800408bc  call    cs:__imp_CreateTimerQueueTimer
0x1800408c2  test    eax, eax
0x1800408c4  jnz     short loc_1800408EB
0x1800408c6  call    cs:__imp_GetLastError
0x1800408cc  mov     ebx, eax
0x1800408ce  test    eax, eax
0x1800408d0  jle     short loc_1800408DB
0x1800408d2  movzx   ebx, ax
0x1800408d5  or      ebx, 80070000h
0x1800408db  test    ebx, ebx
0x1800408dd  jns     short loc_1800408EB
0x1800408df  lea     rdx, aCreatetimerque; "CreateTimerQueueTimer failed: 0x%x in %"...
0x1800408e6  jmp     loc_180040809
0x1800408eb  call    cs:__imp_WinSqmIsOptedIn
0x1800408f1  test    eax, eax
0x1800408f3  jnz     short loc_180040906
0x1800408f5  lea     rdx, aWinsqmisoptedi; "WinSqmIsOptedIn() returned FALSE( not a"...
0x1800408fc  lea     ecx, [rax+1]; int
0x1800408ff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180040904  jmp     short loc_180040964
0x180040906  mov     rdx, [rdi+638h]; TimerQueue
0x18004090d  lea     rcx, [rdi+648h]; phNewTimer
0x180040914  mov     eax, 36EE80h
0x180040919  mov     [rsp+48h+Flags], 20h ; ' '; Flags
0x180040921  mov     [rsp+48h+Period], eax; Period
0x180040925  lea     r8, ?staticRdshLogSQM@CSQMLogger@@CAXPEAXE@Z; Callback
0x18004092c  mov     r9, rdi; Parameter
0x18004092f  mov     [rsp+48h+DueTime], eax; DueTime
0x180040933  call    cs:__imp_CreateTimerQueueTimer
0x180040939  test    eax, eax
0x18004093b  jnz     short loc_180040962
0x18004093d  call    cs:__imp_GetLastError
0x180040943  mov     ebx, eax
0x180040945  test    eax, eax
0x180040947  jle     short loc_180040952
0x180040949  movzx   ebx, ax
0x18004094c  or      ebx, 80070000h
0x180040952  test    ebx, ebx
0x180040954  jns     short loc_180040962
0x180040956  lea     rdx, aCreatetimerque_0; "CreateTimerQueueTimer for m_RdshSqmTime"...
0x18004095d  jmp     loc_180040809
0x180040962  xor     ebx, ebx
0x180040964  mov     eax, ebx
0x180040966  mov     rbx, [rsp+48h+arg_0]
0x18004096b  add     rsp, 40h
0x18004096f  pop     rdi
0x180040970  retn
```
