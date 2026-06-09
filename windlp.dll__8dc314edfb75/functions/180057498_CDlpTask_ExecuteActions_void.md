# CDlpTask::ExecuteActions(void)

- ea: `0x180057498`
- end: `0x180058269`
- name: `?ExecuteActions@CDlpTask@@AEAAJXZ`
- size: `3537`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180054950`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180057498`
- `0x18006b8f4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005776f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005776f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180057a11`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180057a11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180057578`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180057578`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005782b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005782b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005765f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800576e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005765f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800576e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800581bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800581bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800574e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005752a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005759d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800574e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005752a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005759d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005750c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005755c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800575c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005750c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005755c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800575c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180057b55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800580cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180057b55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800580cc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800575d4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180057655`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800576d6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800575d4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180057655`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800576d6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800579a8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800579a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058236`

## string_xrefs

- `0x1800580a8`: `Signalling actions thread to shut down.`
- `0x180057882`: `Action execution thread timeout period: [%d ms]`
- `0x1800577e8`: `CDlpTask::ExecuteActions`
- `0x18005805c`: `CDlpTask::ExecuteActions`
- `0x1800581e8`: `Actions thread has exited.`
- `0x1800581a7`: `Waiting for actions thread to exit.`

## pseudocode

```c
__int64 __fastcall CDlpTask::ExecuteActions(CDlpTask *this)
{
  void *v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v4; // rdi
  signed int LastError; // eax
  signed int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  signed int v9; // eax
  signed int v10; // eax
  HANDLE Thread; // rax
  signed int v12; // eax
  int v13; // eax
  char *v14; // rsi
  unsigned int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  DWORD v20; // eax
  DWORD v21; // r13d
  bool v22; // sf
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  unsigned int v26; // r13d
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-69h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-61h]
  struct IDlpAction *v35; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-41h]
  int i; // [rsp+4Ch] [rbp-3Dh]
  signed int v38; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-35h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-31h] BYREF
  HANDLE v41; // [rsp+60h] [rbp-29h]
  int v42; // [rsp+78h] [rbp-11h]
  HANDLE Handles[11]; // [rsp+88h] [rbp-1h] BYREF
  unsigned int v44; // [rsp+F0h] [rbp+67h] BYREF
  struct _FILETIME v45; // [rsp+F8h] [rbp+6Fh] BYREF
  int v46; // [rsp+100h] [rbp+77h] BYREF
  DWORD ExitCode; // [rsp+108h] [rbp+7Fh] BYREF

  v35 = 0;
  v2 = 0;
  v41 = 0;
  v46 = 0;
  v44 = 0;
  ExitCode = 0;
  *(_OWORD *)Handles = 0;
  v38 = 0;
  SystemTimeAsFileTime = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 888);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v42 = 1;
  v44 = *((_DWORD *)this + 218);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  LeaveCriticalSection(v3);
  v42 = 0;
  v39 = *((_DWORD *)this + 95);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
  v42 = 1;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v42 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
    v42 = 0;
  }
  *((_QWORD *)this + 181) = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v45 = SystemTimeAsFileTime;
  v4 = *(_QWORD *)(*((_QWORD *)this + 148) + 8LL * (int)v44);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
  v42 = 1;
  *(struct _FILETIME *)v4 = v45;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v42 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
    v42 = 0;
  }
  if ( !ResetEvent(*((HANDLE *)this + 29)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_180;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v8 = 0;
    if ( v6 < 0 && v7 )
    {
      LODWORD(lpThreadId) = v6;
      dwCreationFlags[0] = 3387;
      goto LABEL_41;
    }
LABEL_43:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    goto LABEL_180;
  }
  if ( !ResetEvent(*((HANDLE *)this + 30)) )
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_180;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v8 = 0;
    if ( v6 >= 0 || !v7 )
      goto LABEL_43;
    LODWORD(lpThreadId) = v6;
    dwCreationFlags[0] = 3388;
    goto LABEL_41;
  }
  if ( !ResetEvent(*((HANDLE *)this + 31)) )
  {
    v10 = GetLastError();
    v6 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_180;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v8 = 0;
    if ( v6 >= 0 || !v7 )
      goto LABEL_43;
    LODWORD(lpThreadId) = v6;
    dwCreationFlags[0] = 3389;
    goto LABEL_41;
  }
  Thread = CreateThread(0, 0, CDlpTask::ExecuteActionsThreadProc, this, 0, 0);
  v2 = Thread;
  if ( !Thread )
  {
    v41 = 0;
    v12 = GetLastError();
    v6 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_180;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v8 = 0;
    if ( v6 >= 0 || !v7 )
      goto LABEL_43;
    LODWORD(lpThreadId) = v6;
    dwCreationFlags[0] = 3399;
LABEL_41:
    v13 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v7,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTask::ExecuteActions",
            *(_QWORD *)dwCreationFlags,
            lpThreadId);
    v8 = (unsigned int)v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    goto LABEL_43;
  }
  v41 = Thread;
  Handles[0] = *((HANDLE *)this + 30);
  Handles[1] = Thread;
  *((_DWORD *)this + 361) = GetTickCount();
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 183) = 0;
  v14 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v15 = *((_DWORD *)this + 360);
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v16, 2u, (__int64)L"Action execution thread timeout period: [%d ms]", v15);
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  v6 = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, struct IDlpAction **))(*(_QWORD *)this + 120LL))(this, v44, &v35);
  if ( v6 < 0 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
    {
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
      v18 = 0;
      if ( v17 )
      {
        LODWORD(lpThreadId) = v6;
        dwCreationFlags[0] = 3418;
        goto LABEL_161;
      }
      goto LABEL_163;
    }
    goto LABEL_164;
  }
  v45.dwLowDateTime = 1;
  v6 = CDlpTask::ProgressHandlerAction(this, v35, v44, (unsigned int *)&v45);
  if ( v6 < 0 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
    {
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
      v18 = 0;
      if ( v17 )
      {
        LODWORD(lpThreadId) = v6;
        dwCreationFlags[0] = 3420;
        goto LABEL_161;
      }
      goto LABEL_163;
    }
    goto LABEL_164;
  }
  v19 = 1;
  v36 = v44;
  while ( 2 )
  {
    for ( i = v19; ; v19 = i )
    {
      if ( !v19 )
      {
        if ( *((_DWORD *)this + 353) )
          goto LABEL_164;
        v26 = v39;
        if ( v44 >= v39 )
          goto LABEL_164;
        while ( 1 )
        {
          if ( v35 )
          {
            (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
          v6 = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, struct IDlpAction **))(*(_QWORD *)this + 120LL))(
                 this,
                 v44,
                 &v35);
          if ( v6 < 0 )
            break;
          v45.dwLowDateTime |= 2u;
          v6 = CDlpTask::ProgressHandlerAction(this, v35, v44, (unsigned int *)&v45);
          if ( v6 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
              goto LABEL_164;
            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
            v18 = 0;
            if ( v17 )
            {
              LODWORD(lpThreadId) = v6;
              dwCreationFlags[0] = 3511;
              goto LABEL_161;
            }
            goto LABEL_163;
          }
          v6 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v35 + 24LL))(v35, &v46);
          if ( v6 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
              goto LABEL_164;
            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
            v18 = 0;
            if ( v17 )
            {
              LODWORD(lpThreadId) = v6;
              dwCreationFlags[0] = 3514;
              goto LABEL_161;
            }
            goto LABEL_163;
          }
          if ( ((v46 - 4) & 0xFFFFFFFD) != 0 )
          {
            v6 = -2147019873;
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
              goto LABEL_164;
            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
            v18 = 0;
            if ( v17 )
            {
              LODWORD(lpThreadId) = -2147019873;
              dwCreationFlags[0] = 3516;
              goto LABEL_161;
            }
            goto LABEL_163;
          }
          if ( v44 + 1 < v44 )
          {
            v6 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
          }
          else
          {
            ++v44;
            v6 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
          if ( v6 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
              goto LABEL_164;
            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
            v18 = 0;
            if ( v17 )
            {
              LODWORD(lpThreadId) = v6;
              dwCreationFlags[0] = 3518;
              goto LABEL_161;
            }
            goto LABEL_163;
          }
          if ( v44 >= v26 )
            goto LABEL_164;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
          goto LABEL_164;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
        v18 = 0;
        if ( v17 )
        {
          LODWORD(lpThreadId) = v6;
          dwCreationFlags[0] = 3509;
          goto LABEL_161;
        }
        goto LABEL_163;
      }
      v20 = WaitForMultipleObjects(2u, Handles, 0, *((_DWORD *)this + 360));
      v21 = v20;
      if ( !v20 )
        goto LABEL_62;
      if ( v20 == 1 )
        break;
      if ( v20 != 258 )
      {
        if ( v20 != -1 )
        {
          v6 = -2147418113;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
            goto LABEL_164;
          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
          v18 = 0;
          if ( v17 )
          {
            LODWORD(lpThreadId) = -2147418113;
            dwCreationFlags[0] = 3497;
            goto LABEL_161;
          }
          goto LABEL_163;
        }
        v23 = GetLastError();
        v6 = v23;
        if ( v23 > 0 )
          v6 = (unsigned __int16)v23 | 0x80070000;
        if ( v6 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
          goto LABEL_164;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
        v18 = 0;
        if ( !v17 )
          goto LABEL_163;
        LODWORD(lpThreadId) = v6;
        dwCreationFlags[0] = 3492;
        goto LABEL_161;
      }
LABEL_62:
      if ( v35 )
      {
        (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v35 + 16LL))(v35);
        v35 = 0;
      }
      v6 = (*(__int64 (__fastcall **)(CDlpTask *, struct IDlpAction **, unsigned int *))(*(_QWORD *)this + 160LL))(
             this,
             &v35,
             &v44);
      if ( v6 == -2147023728 )
      {
        v6 = 0;
      }
      else if ( v6 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
          goto LABEL_164;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
        v18 = 0;
        if ( v17 )
        {
          LODWORD(lpThreadId) = v6;
          dwCreationFlags[0] = 3439;
          goto LABEL_161;
        }
        goto LABEL_163;
      }
      if ( v35 )
      {
        v6 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v35 + 24LL))(v35, &v46);
        if ( v6 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
            goto LABEL_164;
          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
          v18 = 0;
          if ( v17 )
          {
            LODWORD(lpThreadId) = v6;
            dwCreationFlags[0] = 3442;
            goto LABEL_161;
          }
          goto LABEL_163;
        }
        if ( v46 )
        {
          if ( v46 == 6 )
          {
            v45.dwLowDateTime |= 2u;
            v6 = CDlpTask::ProgressHandlerAction(this, v35, v44, (unsigned int *)&v45);
            if ( v6 < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
                goto LABEL_164;
              v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
              v18 = 0;
              if ( v17 )
              {
                LODWORD(lpThreadId) = v6;
                dwCreationFlags[0] = 3456;
                goto LABEL_161;
              }
              goto LABEL_163;
            }
            goto LABEL_88;
          }
          if ( v46 == -1073741824 )
            goto LABEL_88;
        }
        else if ( v36 != v44 )
        {
          v45.dwLowDateTime = 1;
          v6 = CDlpTask::ProgressHandlerAction(this, v35, v44, (unsigned int *)&v45);
          if ( v6 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
              goto LABEL_164;
            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
            v18 = 0;
            if ( v17 )
            {
              LODWORD(lpThreadId) = v6;
              dwCreationFlags[0] = 3448;
              goto LABEL_161;
            }
            goto LABEL_163;
          }
          v36 = v44;
          goto LABEL_88;
        }
        if ( !v21 || (*((_BYTE *)this + 1420) & 1) != 0 )
          v45.dwLowDateTime |= 4u;
        v6 = CDlpTask::ProgressHandlerAction(this, v35, v44, (unsigned int *)&v45);
        if ( v6 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
            goto LABEL_164;
          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
          v18 = 0;
          if ( v17 )
          {
            LODWORD(lpThreadId) = v6;
            dwCreationFlags[0] = 3471;
            goto LABEL_161;
          }
          goto LABEL_163;
        }
      }
LABEL_88:
      if ( !v21 && !SetEvent(*((HANDLE *)this + 31)) )
      {
        v25 = GetLastError();
        v6 = v25;
        if ( v25 )
        {
          if ( v25 > 0 )
            v6 = (unsigned __int16)v25 | 0x80070000;
        }
        else
        {
          v6 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
          goto LABEL_164;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
        v18 = 0;
        if ( v6 < 0 && v17 )
        {
          LODWORD(lpThreadId) = v6;
          dwCreationFlags[0] = 3480;
          goto LABEL_161;
        }
        goto LABEL_163;
      }
    }
    if ( !GetExitCodeThread(v2, &ExitCode) )
    {
      v24 = GetLastError();
      v6 = v24;
      if ( v24 )
      {
        if ( v24 > 0 )
          v6 = (unsigned __int16)v24 | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
        goto LABEL_164;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
      v18 = 0;
      if ( v6 < 0 && v17 )
      {
        LODWORD(lpThreadId) = v6;
        dwCreationFlags[0] = 3486;
        goto LABEL_161;
      }
      goto LABEL_163;
    }
    v6 = ExitCode;
    v22 = (ExitCode & 0x80000000) != 0;
    if ( (int)ExitCode > 0 )
    {
      v6 = (unsigned __int16)ExitCode | 0x80070000;
      v22 = 1;
    }
    if ( !v22 )
    {
      v19 = 0;
      continue;
    }
    break;
  }
  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
    goto LABEL_164;
  v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
  v18 = 0;
  if ( !v17 )
    goto LABEL_163;
  LODWORD(lpThreadId) = v6;
  dwCreationFlags[0] = 3487;
LABEL_161:
  v27 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v17,
          4u,
          (__int64)L"%s(%d): Result = 0x%X",
          L"CDlpTask::ExecuteActions",
          *(_QWORD *)dwCreationFlags,
          lpThreadId);
  v18 = (unsigned int)v27;
  if ( v27 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27);
LABEL_163:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
LABEL_164:
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
  {
    v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v28, 2u, (__int64)L"Signalling actions thread to shut down.");
  }
  SetEvent(*((HANDLE *)this + 29));
  if ( v6 < 0 )
  {
    if ( v35 )
    {
      (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
    }
    if ( (*(int (__fastcall **)(CDlpTask *, struct IDlpAction **, unsigned int *))(*(_QWORD *)this + 160LL))(
           this,
           &v35,
           &v44) >= 0
      && v35
      && (*(int (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v35 + 24LL))(v35, &v46) >= 0
      && v46 == 3 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
      {
        v29 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
        CDlpLogT<CEmptyType>::DlpLogFormat(v29, 2u, (__int64)L"Cancelling running action...");
      }
      (*(void (__fastcall **)(struct IDlpAction *, CDlpTask *))(*(_QWORD *)v35 + 40LL))(v35, this);
    }
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
  {
    v30 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v30, 2u, (__int64)L"Waiting for actions thread to exit.");
  }
  WaitForSingleObject(v2, 0xFFFFFFFF);
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176) )
  {
    v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v31, 2u, (__int64)L"Actions thread has exited.");
  }
LABEL_180:
  v38 = v6;
  (**((void (__fastcall ***)(char *, __int64, _QWORD, signed int *, _QWORD, _DWORD))this + 2))(
    (char *)this + 16,
    8196,
    0,
    &v38,
    0,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v2 )
    CloseHandle(v2);
  if ( v35 )
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v35 + 16LL))(v35);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180057498  push    rbp
0x18005749a  push    rbx
0x18005749b  push    rsi
0x18005749c  push    rdi
0x18005749d  push    r12
0x18005749f  push    r13
0x1800574a1  push    r14
0x1800574a3  push    r15
0x1800574a5  lea     rbp, [rsp-1Fh]
0x1800574aa  sub     rsp, 0A8h
0x1800574b1  mov     r14, rcx
0x1800574b4  mov     [rbp+57h+var_A0], 0
0x1800574bc  xor     ebx, ebx
0x1800574be  mov     [rbp+57h+var_80], rbx
0x1800574c2  mov     [rbp+57h+arg_10], ebx
0x1800574c5  mov     [rbp+57h+arg_0], ebx
0x1800574c8  mov     [rbp+57h+ExitCode], ebx
0x1800574cb  xorps   xmm0, xmm0
0x1800574ce  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x1800574d2  mov     [rbp+57h+var_90], ebx
0x1800574d5  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800574d9  lea     rdi, [rcx+378h]
0x1800574e0  mov     rcx, rdi; lpCriticalSection
0x1800574e3  call    cs:__imp_EnterCriticalSection
0x1800574e9  lea     r15d, [rbx+1]
0x1800574ed  mov     [rbp+57h+var_68], r15d
0x1800574f1  mov     eax, [r14+368h]
0x1800574f8  mov     [rbp+57h+arg_0], eax
0x1800574fb  xor     ecx, ecx
0x1800574fd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180057502  mov     eax, [rbp+57h+var_68]
0x180057505  test    eax, eax
0x180057507  jz      short loc_180057515
0x180057509  mov     rcx, rdi; lpCriticalSection
0x18005750c  call    cs:__imp_LeaveCriticalSection
0x180057512  mov     [rbp+57h+var_68], ebx
0x180057515  mov     r13d, [r14+17Ch]
0x18005751c  mov     [rbp+57h+var_8C], r13d
0x180057520  lea     rdi, [r14+3C8h]
0x180057527  mov     rcx, rdi; lpCriticalSection
0x18005752a  call    cs:__imp_EnterCriticalSection
0x180057530  mov     [rbp+57h+var_68], r15d
0x180057534  xor     eax, eax
0x180057536  mov     [r14+3A8h], rax
0x18005753d  mov     [r14+3B0h], rax
0x180057544  mov     [r14+3B8h], rax
0x18005754b  xor     ecx, ecx
0x18005754d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180057552  mov     eax, [rbp+57h+var_68]
0x180057555  test    eax, eax
0x180057557  jz      short loc_180057569
0x180057559  mov     rcx, rdi; lpCriticalSection
0x18005755c  call    cs:__imp_LeaveCriticalSection
0x180057562  mov     [rbp+57h+var_68], 0
0x180057569  mov     qword ptr [r14+5A8h], 0
0x180057574  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180057578  call    cs:__imp_GetSystemTimeAsFileTime
0x18005757e  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x180057581  mov     dword ptr [rbp+57h+arg_8+4], eax
0x180057584  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180057587  mov     dword ptr [rbp+57h+arg_8], eax
0x18005758a  mov     rcx, [r14+4A0h]
0x180057591  movsxd  rax, [rbp+57h+arg_0]
0x180057595  mov     rdi, [rcx+rax*8]
0x180057599  lea     rcx, [rdi+10h]; lpCriticalSection
0x18005759d  call    cs:__imp_EnterCriticalSection
0x1800575a3  mov     [rbp+57h+var_68], r15d
0x1800575a7  mov     rax, [rbp+57h+arg_8]
0x1800575ab  mov     [rdi], rax
0x1800575ae  xor     ecx, ecx
0x1800575b0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800575b5  mov     eax, [rbp+57h+var_68]
0x1800575b8  test    eax, eax
0x1800575ba  jz      short loc_1800575CD
0x1800575bc  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800575c0  call    cs:__imp_LeaveCriticalSection
0x1800575c6  mov     [rbp+57h+var_68], 0
0x1800575cd  mov     rcx, [r14+0E8h]; hEvent
0x1800575d4  call    cs:__imp_ResetEvent
0x1800575da  test    eax, eax
0x1800575dc  jnz     short loc_18005764E
0x1800575de  call    cs:__imp_GetLastError
0x1800575e4  mov     edi, eax
0x1800575e6  test    eax, eax
0x1800575e8  jnz     short loc_1800575F1
0x1800575ea  mov     edi, 80004005h
0x1800575ef  jmp     short loc_1800575FC
0x1800575f1  jle     short loc_1800575FC
0x1800575f3  movzx   edi, ax
0x1800575f6  or      edi, 80070000h
0x1800575fc  lea     rsi, [r14+0B0h]
0x180057603  mov     rax, [rsi]
0x180057606  mov     rcx, rsi
0x180057609  mov     rax, [rax+10h]
0x18005760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057612  test    rax, rax
0x180057615  jz      loc_1800581F7
0x18005761b  mov     rax, [rsi]
0x18005761e  mov     rcx, rsi
0x180057621  mov     rax, [rax+10h]
0x180057625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005762a  xor     ecx, ecx
0x18005762c  test    edi, edi
0x18005762e  jns     loc_18005780E
0x180057634  test    rax, rax
0x180057637  jz      loc_18005780E
0x18005763d  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180057641  mov     [rsp+0E0h+dwCreationFlags], 0D3Bh
0x180057649  jmp     loc_1800577E8
0x18005764e  mov     rcx, [r14+0F0h]; hEvent
0x180057655  call    cs:__imp_ResetEvent
0x18005765b  test    eax, eax
0x18005765d  jnz     short loc_1800576CF
0x18005765f  call    cs:__imp_GetLastError
0x180057665  mov     edi, eax
0x180057667  test    eax, eax
0x180057669  jnz     short loc_180057672
0x18005766b  mov     edi, 80004005h
0x180057670  jmp     short loc_18005767D
0x180057672  jle     short loc_18005767D
0x180057674  movzx   edi, ax
0x180057677  or      edi, 80070000h
0x18005767d  lea     rsi, [r14+0B0h]
0x180057684  mov     rax, [rsi]
0x180057687  mov     rcx, rsi
0x18005768a  mov     rax, [rax+10h]
0x18005768e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057693  test    rax, rax
0x180057696  jz      loc_1800581F7
0x18005769c  mov     rax, [rsi]
0x18005769f  mov     rcx, rsi
0x1800576a2  mov     rax, [rax+10h]
0x1800576a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576ab  xor     ecx, ecx
0x1800576ad  test    edi, edi
0x1800576af  jns     loc_18005780E
0x1800576b5  test    rax, rax
0x1800576b8  jz      loc_18005780E
0x1800576be  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x1800576c2  mov     [rsp+0E0h+dwCreationFlags], 0D3Ch
0x1800576ca  jmp     loc_1800577E8
0x1800576cf  mov     rcx, [r14+0F8h]; hEvent
0x1800576d6  call    cs:__imp_ResetEvent
0x1800576dc  test    eax, eax
0x1800576de  jnz     short loc_180057750
0x1800576e0  call    cs:__imp_GetLastError
0x1800576e6  mov     edi, eax
0x1800576e8  test    eax, eax
0x1800576ea  jnz     short loc_1800576F3
0x1800576ec  mov     edi, 80004005h
0x1800576f1  jmp     short loc_1800576FE
0x1800576f3  jle     short loc_1800576FE
0x1800576f5  movzx   edi, ax
0x1800576f8  or      edi, 80070000h
0x1800576fe  lea     rsi, [r14+0B0h]
0x180057705  mov     rax, [rsi]
0x180057708  mov     rcx, rsi
0x18005770b  mov     rax, [rax+10h]
0x18005770f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057714  test    rax, rax
0x180057717  jz      loc_1800581F7
0x18005771d  mov     rax, [rsi]
0x180057720  mov     rcx, rsi
0x180057723  mov     rax, [rax+10h]
0x180057727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005772c  xor     ecx, ecx
0x18005772e  test    edi, edi
0x180057730  jns     loc_18005780E
0x180057736  test    rax, rax
0x180057739  jz      loc_18005780E
0x18005773f  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180057743  mov     [rsp+0E0h+dwCreationFlags], 0D3Dh
0x18005774b  jmp     loc_1800577E8
0x180057750  mov     [rsp+0E0h+lpThreadId], 0; lpThreadId
0x180057759  mov     [rsp+0E0h+dwCreationFlags], 0; dwCreationFlags
0x180057761  mov     r9, r14; lpParameter
0x180057764  lea     r8, ?ExecuteActionsThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x18005776b  xor     edx, edx; dwStackSize
0x18005776d  xor     ecx, ecx; lpThreadAttributes
0x18005776f  call    cs:__imp_CreateThread
0x180057775  mov     rbx, rax
0x180057778  test    rax, rax
0x18005777b  jnz     loc_180057818
0x180057781  mov     [rbp+57h+var_80], rax
0x180057785  call    cs:__imp_GetLastError
0x18005778b  mov     edi, eax
0x18005778d  test    eax, eax
0x18005778f  jnz     short loc_180057798
0x180057791  mov     edi, 80004005h
0x180057796  jmp     short loc_1800577A3
0x180057798  jle     short loc_1800577A3
0x18005779a  movzx   edi, ax
0x18005779d  or      edi, 80070000h
0x1800577a3  lea     rsi, [r14+0B0h]
0x1800577aa  mov     rax, [rsi]
0x1800577ad  mov     rcx, rsi
0x1800577b0  mov     rax, [rax+10h]
0x1800577b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577b9  test    rax, rax
0x1800577bc  jz      loc_1800581F7
0x1800577c2  mov     rax, [rsi]
0x1800577c5  mov     rcx, rsi
0x1800577c8  mov     rax, [rax+10h]
0x1800577cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577d1  xor     ecx, ecx
0x1800577d3  test    edi, edi
0x1800577d5  jns     short loc_18005780E
0x1800577d7  test    rax, rax
0x1800577da  jz      short loc_18005780E
0x1800577dc  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x1800577e0  mov     [rsp+0E0h+dwCreationFlags], 0D47h
0x1800577e8  lea     r9, aCdlptaskExecut_0; "CDlpTask::ExecuteActions"
0x1800577ef  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800577f6  mov     edx, 4
0x1800577fb  mov     rcx, rax
0x1800577fe  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180057803  test    eax, eax
0x180057805  mov     ecx, eax
0x180057807  jns     short loc_18005780E
0x180057809  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005780e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180057813  jmp     loc_1800581F7
0x180057818  mov     [rbp+57h+var_80], rbx
0x18005781c  mov     rax, [r14+0F0h]
0x180057823  mov     [rbp+57h+Handles], rax
0x180057827  mov     [rbp+57h+Handles+8], rbx
0x18005782b  call    cs:__imp_GetTickCount
0x180057831  mov     [r14+5A4h], eax
0x180057838  mov     qword ptr [r14+5B0h], 0
0x180057843  mov     qword ptr [r14+5B8h], 0
0x18005784e  lea     rsi, [r14+0B0h]
0x180057855  mov     rax, [rsi]
0x180057858  mov     rcx, rsi
0x18005785b  mov     rax, [rax+10h]
0x18005785f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057864  test    rax, rax
0x180057867  jz      short loc_180057896
0x180057869  mov     edi, [r14+5A0h]
0x180057870  mov     rax, [rsi]
0x180057873  mov     rcx, rsi
0x180057876  mov     rax, [rax+10h]
0x18005787a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005787f  mov     r9d, edi
0x180057882  lea     r8, aActionExecutio; "Action execution thread timeout period:"...
0x180057889  mov     edx, 2
0x18005788e  mov     rcx, rax
0x180057891  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180057896  mov     rcx, [rbp+57h+var_A0]
0x18005789a  test    rcx, rcx
0x18005789d  jz      short loc_1800578B4
0x18005789f  mov     rax, [rcx]
0x1800578a2  mov     rax, [rax+10h]
0x1800578a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578ab  nop
0x1800578ac  mov     [rbp+57h+var_A0], 0
0x1800578b4  mov     rax, [r14]
0x1800578b7  lea     r8, [rbp+57h+var_A0]
0x1800578bb  mov     edx, [rbp+57h+arg_0]
0x1800578be  mov     rcx, r14
0x1800578c1  mov     rax, [rax+78h]
0x1800578c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578ca  mov     edi, eax
0x1800578cc  test    eax, eax
0x1800578ce  jns     short loc_180057918
0x1800578d0  mov     rcx, [rsi]
0x1800578d3  mov     rax, [rcx+10h]
0x1800578d7  mov     rcx, rsi
0x1800578da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578df  test    rax, rax
0x1800578e2  jz      loc_180058082
0x1800578e8  mov     rax, [rsi]
0x1800578eb  mov     rcx, rsi
0x1800578ee  mov     rax, [rax+10h]
0x1800578f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578f7  xor     ecx, ecx
0x1800578f9  test    rax, rax
0x1800578fc  jz      loc_18005807D
0x180057902  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180057906  mov     [rsp+0E0h+dwCreationFlags], 0D5Ah
0x18005790e  mov     edx, 4
0x180057913  jmp     loc_18005805C
0x180057918  mov     dword ptr [rbp+57h+arg_8], r15d
0x18005791c  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180057920  mov     r8d, [rbp+57h+arg_0]; unsigned int
0x180057924  mov     rdx, [rbp+57h+var_A0]; struct IDlpAction *
0x180057928  mov     rcx, r14; this
0x18005792b  call    ?ProgressHandlerAction@CDlpTask@@AEAAJPEAVIDlpAction@@KPEAK@Z; CDlpTask::ProgressHandlerAction(IDlpAction *,ulong,ulong *)
0x180057930  mov     edi, eax
0x180057932  test    eax, eax
0x180057934  jns     short loc_180057976
0x180057936  mov     rax, [rsi]
0x180057939  mov     rcx, rsi
0x18005793c  mov     rax, [rax+10h]
0x180057940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057945  test    rax, rax
0x180057948  jz      loc_180058082
0x18005794e  mov     rax, [rsi]
0x180057951  mov     rcx, rsi
0x180057954  mov     rax, [rax+10h]
0x180057958  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
