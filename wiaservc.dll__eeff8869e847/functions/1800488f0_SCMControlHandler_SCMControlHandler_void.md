# SCMControlHandler::~SCMControlHandler(void)

- ea: `0x1800488f0`
- end: `0x180048b15`
- name: `??1SCMControlHandler@@UEAA@XZ`
- size: `549`
- prototype: `void __fastcall(SCMControlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180048b20`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18002c1ec`
- `0x18002c3e8`
- `0x18002c868`
- `0x18002c8b0`
- `0x1800488f0`
- `0x180048cc0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800489fb`
- `KERNEL32!WaitForSingleObject` at `0x1800489fb`
- `KERNEL32!GetLastError` at `0x180048ad2`
- `KERNEL32!GetLastError` at `0x180048ad2`
- `KERNEL32!CloseHandle` at `0x180048a05`
- `KERNEL32!CloseHandle` at `0x180048a17`
- `KERNEL32!CloseHandle` at `0x180048a29`
- `KERNEL32!CloseHandle` at `0x180048a05`
- `KERNEL32!CloseHandle` at `0x180048a17`
- `KERNEL32!CloseHandle` at `0x180048a29`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800489a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800489a5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180048ac8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180048ac8`

## string_xrefs

- `0x180048a41`: `SERVICE_STOPPED`
- `0x180048a87`: `SERVICE_STOPPED`
- `0x180048a4f`: `Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d`
- `0x180048a92`: `Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d`
- `0x1800489ab`: `Waiting for the control thread to terminate...`
- `0x1800489d1`: `Waiting for the control thread to terminate...`

## pseudocode

```c
void __fastcall SCMControlHandler::~SCMControlHandler(SCMControlHandler *this)
{
  SCMControlHandler *v1; // rdi
  char *v3; // rbx
  void *v4; // rdx
  void **lpMem; // rax
  void *v6; // rdx
  __int64 v7; // rcx
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx

  v1 = (SCMControlHandler *)((char *)this - 232);
  *((_QWORD *)this - 29) = &SCMControlHandler::`vftable'{for `SystemEventSource'};
  *((_QWORD *)this - 27) = &SCMControlHandler::`vftable'{for `ServiceStatus'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 28) + 4LL) - 224) = &SCMControlHandler::`vftable'{for `CSimpleRefCount'};
  v3 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(1, 0, " (%p)", (char *)this - 232);
  WriteDbgTraceInfoWI("SCMControlHandler::~SCMControlHandler", v3);
  WiaTrcLib::Free((WiaTrcLib *)v3, v4);
  lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(1, 0, " (%p)", v1);
  WiaTrace_ProcessTrace_Ex(v7, v6, (void *)"SCMControlHandler::~SCMControlHandler", 4, lpMem);
  SCMControlHandler::UnRegister(v1);
  if ( *((_QWORD *)this - 4) )
  {
    SetEvent(*((HANDLE *)this - 3));
    v8 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Waiting for the control thread to terminate...");
    WriteDbgTraceInfoWI("SCMControlHandler::~SCMControlHandler", v8);
    WiaTrcLib::Free((WiaTrcLib *)v8, v9);
    v10 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Waiting for the control thread to terminate...");
    WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"SCMControlHandler::~SCMControlHandler", 4, v10);
    WaitForSingleObject(*((HANDLE *)this - 4), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this - 4));
    v13 = (void *)*((_QWORD *)this - 3);
    *((_QWORD *)this - 4) = 0;
    CloseHandle(v13);
    v14 = (void *)*((_QWORD *)this - 2);
    *((_QWORD *)this - 3) = 0;
    CloseHandle(v14);
    *((_QWORD *)this - 2) = 0;
  }
  *((_DWORD *)this - 31) = 1;
  *(_QWORD *)((char *)this - 108) = 0;
  v15 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                  2,
                  0,
                  "Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d",
                  "SERVICE_STOPPED",
                  1,
                  0);
  WriteDbgTraceInfoWI("SCMControlHandler::~SCMControlHandler", v15);
  WiaTrcLib::Free((WiaTrcLib *)v15, v16);
  v17 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                   2,
                   0,
                   "Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d",
                   "SERVICE_STOPPED",
                   *((_DWORD *)this - 31),
                   *((_DWORD *)this - 26));
  WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"SCMControlHandler::~SCMControlHandler", 4, v17);
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this - 17), (LPSERVICE_STATUS)((char *)this - 128)) )
    GetLastError();
  *((_QWORD *)this - 25) = 1146320453;
  *((_OWORD *)this - 8) = 0;
  *(_OWORD *)((char *)this - 116) = 0;
  *((_QWORD *)this - 17) = 0;
  SCMControlQueue::~SCMControlQueue((SCMControlHandler *)((char *)this - 96));
  CRIT_SECT::~CRIT_SECT((struct _RTL_CRITICAL_SECTION *)((char *)this - 184));
}

```

## disassembly

```asm
0x1800488f0  push    rbx
0x1800488f2  push    rsi
0x1800488f3  push    rdi
0x1800488f4  push    r15
0x1800488f6  sub     rsp, 38h
0x1800488fa  lea     rdi, [rcx-0E8h]
0x180048901  mov     rsi, rcx
0x180048904  lea     rax, ??_7SCMControlHandler@@6BSystemEventSource@@@; const SCMControlHandler::`vftable'{for `SystemEventSource'}
0x18004890b  mov     r9, rdi
0x18004890e  mov     [rdi], rax
0x180048911  lea     r8, aP; " (%p)"
0x180048918  lea     rax, ??_7SCMControlHandler@@6BServiceStatus@@@; const SCMControlHandler::`vftable'{for `ServiceStatus'}
0x18004891f  mov     [rcx-0D8h], rax
0x180048926  mov     rax, [rcx-0E0h]
0x18004892d  movsxd  rdx, dword ptr [rax+4]
0x180048931  lea     rax, ??_7SCMControlHandler@@6BCSimpleRefCount@@@; const SCMControlHandler::`vftable'{for `CSimpleRefCount'}
0x180048938  mov     [rdx+rcx-0E0h], rax
0x180048940  xor     edx, edx
0x180048942  lea     ecx, [rdx+1]
0x180048945  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004894a  lea     r15, aScmcontrolhand_4; "SCMControlHandler::~SCMControlHandler"
0x180048951  mov     rdx, rax; char *
0x180048954  mov     rcx, r15; char *
0x180048957  mov     rbx, rax
0x18004895a  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004895f  mov     rcx, rbx; this
0x180048962  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180048967  xor     edx, edx
0x180048969  lea     r8, aP; " (%p)"
0x180048970  mov     r9, rdi
0x180048973  lea     ecx, [rdx+1]
0x180048976  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004897b  mov     r9d, 4; int
0x180048981  mov     [rsp+58h+lpMem], rax; lpMem
0x180048986  mov     r8, r15; int
0x180048989  call    WiaTrace_ProcessTrace_Ex
0x18004898e  mov     rcx, rdi; this
0x180048991  call    ?UnRegister@SCMControlHandler@@UEAAJXZ; SCMControlHandler::UnRegister(void)
0x180048996  cmp     qword ptr [rsi-20h], 0
0x18004899b  jz      loc_180048A37
0x1800489a1  mov     rcx, [rsi-18h]; hEvent
0x1800489a5  call    cs:__imp_SetEvent
0x1800489ab  lea     r8, aWaitingForTheC; "Waiting for the control thread to termi"...
0x1800489b2  xor     edx, edx
0x1800489b4  xor     ecx, ecx
0x1800489b6  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800489bb  mov     rdx, rax; char *
0x1800489be  mov     rcx, r15; char *
0x1800489c1  mov     rbx, rax
0x1800489c4  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800489c9  mov     rcx, rbx; this
0x1800489cc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800489d1  lea     r8, aWaitingForTheC; "Waiting for the control thread to termi"...
0x1800489d8  xor     edx, edx
0x1800489da  xor     ecx, ecx
0x1800489dc  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800489e1  mov     r9d, 4; int
0x1800489e7  mov     [rsp+58h+lpMem], rax; lpMem
0x1800489ec  mov     r8, r15; int
0x1800489ef  call    WiaTrace_ProcessTrace_Ex
0x1800489f4  mov     rcx, [rsi-20h]; hHandle
0x1800489f8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800489fb  call    cs:__imp_WaitForSingleObject
0x180048a01  mov     rcx, [rsi-20h]; hObject
0x180048a05  call    cs:__imp_CloseHandle
0x180048a0b  mov     rcx, [rsi-18h]; hObject
0x180048a0f  mov     qword ptr [rsi-20h], 0
0x180048a17  call    cs:__imp_CloseHandle
0x180048a1d  mov     rcx, [rsi-10h]; hObject
0x180048a21  mov     qword ptr [rsi-18h], 0
0x180048a29  call    cs:__imp_CloseHandle
0x180048a2f  mov     qword ptr [rsi-10h], 0
0x180048a37  xor     edx, edx
0x180048a39  mov     [rsp+58h+var_30], 0
0x180048a41  lea     r9, aServiceStopped; "SERVICE_STOPPED"
0x180048a48  mov     dword ptr [rsi-7Ch], 1
0x180048a4f  lea     r8, aUpdatingServic; "Updating service status. CurrentState=%"...
0x180048a56  mov     qword ptr [rsi-6Ch], 0
0x180048a5e  mov     dword ptr [rsp+58h+lpMem], 1
0x180048a66  lea     ecx, [rdx+2]
0x180048a69  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180048a6e  mov     rdx, rax; char *
0x180048a71  mov     rcx, r15; char *
0x180048a74  mov     rbx, rax
0x180048a77  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180048a7c  mov     rcx, rbx; this
0x180048a7f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180048a84  mov     eax, [rsi-68h]
0x180048a87  lea     r9, aServiceStopped; "SERVICE_STOPPED"
0x180048a8e  mov     [rsp+58h+var_30], eax
0x180048a92  lea     r8, aUpdatingServic; "Updating service status. CurrentState=%"...
0x180048a99  mov     eax, [rsi-7Ch]
0x180048a9c  xor     edx, edx
0x180048a9e  mov     dword ptr [rsp+58h+lpMem], eax
0x180048aa2  lea     ecx, [rdx+2]
0x180048aa5  call    WiaTrace_TraceWithSubCompTraceLevel
0x180048aaa  mov     r9d, 4; int
0x180048ab0  mov     [rsp+58h+lpMem], rax; lpMem
0x180048ab5  mov     r8, r15; int
0x180048ab8  call    WiaTrace_ProcessTrace_Ex
0x180048abd  mov     rcx, [rsi-88h]; hServiceStatus
0x180048ac4  lea     rdx, [rsi-80h]; lpServiceStatus
0x180048ac8  call    cs:__imp_SetServiceStatus
0x180048ace  test    eax, eax
0x180048ad0  jnz     short loc_180048AD8
0x180048ad2  call    cs:__imp_GetLastError
0x180048ad8  xorps   xmm0, xmm0
0x180048adb  mov     qword ptr [rsi-0C8h], 44537645h
0x180048ae6  movups  xmmword ptr [rsi-80h], xmm0
0x180048aea  xor     eax, eax
0x180048aec  lea     rcx, [rsi-60h]; this
0x180048af0  movups  xmmword ptr [rsi-74h], xmm0
0x180048af4  mov     [rsi-88h], rax
0x180048afb  call    ??1SCMControlQueue@@QEAA@XZ; SCMControlQueue::~SCMControlQueue(void)
0x180048b00  lea     rcx, [rsi-0B8h]; this
0x180048b07  add     rsp, 38h
0x180048b0b  pop     r15
0x180048b0d  pop     rdi
0x180048b0e  pop     rsi
0x180048b0f  pop     rbx
0x180048b10  jmp     ??1CRIT_SECT@@QEAA@XZ; CRIT_SECT::~CRIT_SECT(void)
```
