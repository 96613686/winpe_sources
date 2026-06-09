# CProfMgr::OnServiceStop(void)

- ea: `0x1800162cc`
- end: `0x180016426`
- name: `?OnServiceStop@CProfMgr@@QEAAXXZ`
- size: `346`
- prototype: `void __fastcall(CProfMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800310a0`

## callees

- `0x180001a24`
- `0x180003f30`
- `0x1800162cc`
- `0x18003212c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001631b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001631b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800162f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800162f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016373`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016373`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180016311`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180016311`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800163ed`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800163ed`
- `USERENV!UnregisterGPNotification` at `0x1800162e1`
- `USERENV!UnregisterGPNotification` at `0x1800162e1`

## string_xrefs

- `0x180016330`: `DeleteTimerQueueEx 0x%08x`
- `0x180016379`: `Completed WaitForSingleObject for PolicyMonitorWorker`

## pseudocode

```c
void __fastcall CProfMgr::OnServiceStop(CProfMgr *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  signed int LastError; // eax
  void *v6; // rcx
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 200);
  if ( v2 )
    UnregisterGPNotification(v2);
  v3 = (void *)*((_QWORD *)this + 199);
  if ( v3 )
    SetEvent(v3);
  CProfMgr::OnPolicyDisable(this);
  v4 = (void *)*((_QWORD *)this + 204);
  if ( v4 )
  {
    if ( DeleteTimerQueueEx(v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      *((_QWORD *)this + 204) = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "DeleteTimerQueueEx 0x%08x", LastError);
    }
  }
  if ( *((_QWORD *)this + 201) )
  {
    _DbgPrintMessage(1, "WaitForSingleObject for PolicyMonitorWorker");
    WaitForSingleObject(*((HANDLE *)this + 201), 0xFFFFFFFF);
    _DbgPrintMessage(1, "Completed WaitForSingleObject for PolicyMonitorWorker");
    CloseHandle(*((HANDLE *)this + 201));
    *((_QWORD *)this + 201) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 200);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 200) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 199);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 199) = 0;
  }
  if ( CUVHDProfileTelemetryLogging::m_hTelemetryTimerLowFreq )
  {
    DeleteTimerQueueTimer(0, CUVHDProfileTelemetryLogging::m_hTelemetryTimerLowFreq, 0);
    CUVHDProfileTelemetryLogging::m_hTelemetryTimerLowFreq = 0;
  }
  TraceLoggingUnregister_EventUnregister(&dword_1800842F8);
  TraceLoggingUnregister_EventUnregister(&dword_1800842C0);
  CUVHDProfileTelemetryLogging::m_TelemetryEnabled = 0;
}

```

## disassembly

```asm
0x1800162cc  push    rbx
0x1800162ce  sub     rsp, 20h
0x1800162d2  mov     rbx, rcx
0x1800162d5  mov     rcx, [rcx+640h]; hEvent
0x1800162dc  test    rcx, rcx
0x1800162df  jz      short loc_1800162E7
0x1800162e1  call    cs:__imp_UnregisterGPNotification
0x1800162e7  mov     rcx, [rbx+638h]; hEvent
0x1800162ee  test    rcx, rcx
0x1800162f1  jz      short loc_1800162F9
0x1800162f3  call    cs:__imp_SetEvent
0x1800162f9  mov     rcx, rbx; this
0x1800162fc  call    ?OnPolicyDisable@CProfMgr@@AEAAJXZ; CProfMgr::OnPolicyDisable(void)
0x180016301  mov     rcx, [rbx+660h]; TimerQueue
0x180016308  test    rcx, rcx
0x18001630b  jz      short loc_18001634E
0x18001630d  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180016311  call    cs:__imp_DeleteTimerQueueEx
0x180016317  test    eax, eax
0x180016319  jnz     short loc_180016343
0x18001631b  call    cs:__imp_GetLastError
0x180016321  test    eax, eax
0x180016323  jle     short loc_18001632D
0x180016325  movzx   eax, ax
0x180016328  or      eax, 80070000h
0x18001632d  mov     r8d, eax
0x180016330  lea     rdx, aDeletetimerque; "DeleteTimerQueueEx 0x%08x"
0x180016337  mov     ecx, 8; int
0x18001633c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016341  jmp     short loc_18001634E
0x180016343  mov     qword ptr [rbx+660h], 0
0x18001634e  cmp     qword ptr [rbx+648h], 0
0x180016356  jz      short loc_1800163A2
0x180016358  lea     rdx, aWaitforsingleo; "WaitForSingleObject for PolicyMonitorWo"...
0x18001635f  mov     ecx, 1; int
0x180016364  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016369  mov     rcx, [rbx+648h]; hHandle
0x180016370  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016373  call    cs:__imp_WaitForSingleObject
0x180016379  lea     rdx, aCompletedWaitf; "Completed WaitForSingleObject for Polic"...
0x180016380  mov     ecx, 1; int
0x180016385  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001638a  mov     rcx, [rbx+648h]; hObject
0x180016391  call    cs:__imp_CloseHandle
0x180016397  mov     qword ptr [rbx+648h], 0
0x1800163a2  mov     rcx, [rbx+640h]; hObject
0x1800163a9  test    rcx, rcx
0x1800163ac  jz      short loc_1800163BF
0x1800163ae  call    cs:__imp_CloseHandle
0x1800163b4  mov     qword ptr [rbx+640h], 0
0x1800163bf  mov     rcx, [rbx+638h]; hObject
0x1800163c6  test    rcx, rcx
0x1800163c9  jz      short loc_1800163DC
0x1800163cb  call    cs:__imp_CloseHandle
0x1800163d1  mov     qword ptr [rbx+638h], 0
0x1800163dc  mov     rdx, cs:?m_hTelemetryTimerLowFreq@CUVHDProfileTelemetryLogging@@0PEAXEA; Timer
0x1800163e3  test    rdx, rdx
0x1800163e6  jz      short loc_1800163FE
0x1800163e8  xor     r8d, r8d; CompletionEvent
0x1800163eb  xor     ecx, ecx; TimerQueue
0x1800163ed  call    cs:__imp_DeleteTimerQueueTimer
0x1800163f3  mov     cs:?m_hTelemetryTimerLowFreq@CUVHDProfileTelemetryLogging@@0PEAXEA, 0; void * CUVHDProfileTelemetryLogging::m_hTelemetryTimerLowFreq
0x1800163fe  lea     rcx, dword_1800842F8
0x180016405  call    TraceLoggingUnregister_EventUnregister
0x18001640a  lea     rcx, dword_1800842C0
0x180016411  call    TraceLoggingUnregister_EventUnregister
0x180016416  mov     cs:?m_TelemetryEnabled@CUVHDProfileTelemetryLogging@@0HA, 0; int CUVHDProfileTelemetryLogging::m_TelemetryEnabled
0x180016420  add     rsp, 20h
0x180016424  pop     rbx
0x180016425  retn
```
