# SCMControlHandler::SCMControlHandler(void)

- ea: `0x180014b9c`
- end: `0x180014ef1`
- name: `??0SCMControlHandler@@QEAA@XZ`
- size: `853`
- prototype: `SCMControlHandler *__fastcall(SCMControlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800147d0`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x180014b9c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002ec74`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180014c92`
- `KERNEL32!CreateEventW` at `0x180014cb2`
- `KERNEL32!CreateEventW` at `0x180014c92`
- `KERNEL32!CreateEventW` at `0x180014cb2`
- `KERNEL32!GetLastError` at `0x180014d50`
- `KERNEL32!GetLastError` at `0x180014d7e`
- `KERNEL32!GetLastError` at `0x180014dd3`
- `KERNEL32!GetLastError` at `0x180014e01`
- `KERNEL32!GetLastError` at `0x180014e3f`
- `KERNEL32!GetLastError` at `0x180014e6d`
- `KERNEL32!GetLastError` at `0x180014d50`
- `KERNEL32!GetLastError` at `0x180014d7e`
- `KERNEL32!GetLastError` at `0x180014dd3`
- `KERNEL32!GetLastError` at `0x180014e01`
- `KERNEL32!GetLastError` at `0x180014e3f`
- `KERNEL32!GetLastError` at `0x180014e6d`
- `KERNEL32!CloseHandle` at `0x180014dad`
- `KERNEL32!CloseHandle` at `0x180014dc1`
- `KERNEL32!CloseHandle` at `0x180014e30`
- `KERNEL32!CloseHandle` at `0x180014dad`
- `KERNEL32!CloseHandle` at `0x180014dc1`
- `KERNEL32!CloseHandle` at `0x180014e30`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180014cf4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180014d2e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180014cf4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180014d2e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180014cdf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180014cdf`

## string_xrefs

- `0x180014e47`: `CreateEvent(terminate control thread) failed, error code %u`
- `0x180014e75`: `CreateEvent(terminate control thread) failed, error code %u`
- `0x180014cfa`: `Created control thread Id %u`
- `0x180014d34`: `Created control thread Id %u`
- `0x180014d58`: `CreateThread for the control thread failed, error code: %u`
- `0x180014d86`: `CreateThread for the control thread failed, error code: %u`
- `0x180014ddb`: `CreateEvent(resume control thread) failed, error code %u`
- `0x180014e09`: `CreateEvent(resume control thread) failed, error code %u`
- `0x180014e9e`: `Control thread not created, reverting to syncronous control processing`
- `0x180014ec4`: `Control thread not created, reverting to syncronous control processing`

## pseudocode

```c
SCMControlHandler *__fastcall SCMControlHandler::SCMControlHandler(SCMControlHandler *this)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax
  HANDLE Thread; // rax
  DWORD ThreadId; // eax
  char *v6; // rbx
  void *v7; // rdx
  DWORD v8; // eax
  void **v9; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  int v12; // r9d
  char *v13; // rbx
  void *v14; // rdx
  DWORD v15; // eax
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  void *v19; // rcx
  char *v20; // rbx
  void *v21; // rdx
  DWORD LastError; // eax
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  DWORD v28; // eax
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx

  *((_QWORD *)this + 1) = &SCMControlHandler::`vbtable'{for `SystemEventSource'};
  *((_QWORD *)this + 3) = &SCMControlHandler::`vbtable'{for `ServiceStatus'};
  *((_QWORD *)this + 29) = &CSimpleRefCount::`vftable';
  *((_DWORD *)this + 60) = 1;
  *(_QWORD *)this = &SystemEventSource::`vftable'{for `SystemEventSource'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &SystemEventSource::`vftable'{for `CSimpleRefCount'};
  *((_QWORD *)this + 2) = &ServiceStatus::`vftable'{for `ServiceStatus'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 3) + 4LL) + 24) = &ServiceStatus::`vftable'{for `CSimpleRefCount'};
  *(_QWORD *)this = &SCMControlHandler::`vftable'{for `SystemEventSource'};
  *((_QWORD *)this + 2) = &SCMControlHandler::`vftable'{for `ServiceStatus'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &SCMControlHandler::`vftable'{for `CSimpleRefCount'};
  CRIT_SECT::CRIT_SECT((SCMControlHandler *)((char *)this + 48));
  CRIT_SECT::CRIT_SECT((SCMControlHandler *)((char *)this + 152));
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 8) = 1431533125;
  *((_DWORD *)this + 9) = 1;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 116) = 0;
  *((_QWORD *)this + 28) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 26) = EventW;
  if ( EventW )
  {
    v3 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 27) = v3;
    if ( !v3 )
    {
      GetLastError();
      v20 = (char *)WiaTrace_TraceLog("CreateEvent(resume control thread) failed, error code %u");
      WriteDbgTraceErrorWI("SCMControlHandler::SCMControlHandler", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      LastError = GetLastError();
      v23 = (void **)WiaTrace_Trace("CreateEvent(resume control thread) failed, error code %u", LastError);
      WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"SCMControlHandler::SCMControlHandler", 1, v23);
      CloseHandle(*((HANDLE *)this + 26));
      *((_QWORD *)this + 26) = 0;
      goto LABEL_9;
    }
    Thread = CreateThread(0, 0, SCMControlHandler::ControlThread, this, 0, 0);
    *((_QWORD *)this + 25) = Thread;
    if ( !Thread )
    {
      GetLastError();
      v13 = (char *)WiaTrace_TraceLog("CreateThread for the control thread failed, error code: %u");
      WriteDbgTraceErrorWI("SCMControlHandler::SCMControlHandler", v13);
      WiaTrcLib::Free((WiaTrcLib *)v13, v14);
      v15 = GetLastError();
      v16 = (void **)WiaTrace_Trace("CreateThread for the control thread failed, error code: %u", v15);
      WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"SCMControlHandler::SCMControlHandler", 1, v16);
      CloseHandle(*((HANDLE *)this + 26));
      v19 = (void *)*((_QWORD *)this + 27);
      *((_QWORD *)this + 26) = 0;
      CloseHandle(v19);
      *((_QWORD *)this + 27) = 0;
      goto LABEL_9;
    }
    ThreadId = GetThreadId(Thread);
    v6 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Created control thread Id %u", ThreadId);
    WriteDbgTraceInfoWI("SCMControlHandler::SCMControlHandler", v6);
    WiaTrcLib::Free((WiaTrcLib *)v6, v7);
    v8 = GetThreadId(*((HANDLE *)this + 25));
    v9 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Created control thread Id %u", v8);
    v12 = 4;
  }
  else
  {
    GetLastError();
    v26 = (char *)WiaTrace_TraceLog("CreateEvent(terminate control thread) failed, error code %u");
    WriteDbgTraceErrorWI("SCMControlHandler::SCMControlHandler", v26);
    WiaTrcLib::Free((WiaTrcLib *)v26, v27);
    v28 = GetLastError();
    v9 = (void **)WiaTrace_Trace("CreateEvent(terminate control thread) failed, error code %u", v28);
    v12 = 1;
  }
  WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"SCMControlHandler::SCMControlHandler", v12, v9);
LABEL_9:
  if ( !*((_QWORD *)this + 25) )
  {
    v29 = (char *)WiaTrace_TraceLog("Control thread not created, reverting to syncronous control processing");
    WriteDbgTraceErrorWI("SCMControlHandler::SCMControlHandler", v29);
    WiaTrcLib::Free((WiaTrcLib *)v29, v30);
    v31 = (void **)WiaTrace_Trace("Control thread not created, reverting to syncronous control processing");
    WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"SCMControlHandler::SCMControlHandler", 1, v31);
  }
  return this;
}

```

## disassembly

```asm
0x180014b9c  push    rbx
0x180014b9e  push    rbp
0x180014b9f  push    rdi
0x180014ba0  push    r14
0x180014ba2  sub     rsp, 38h
0x180014ba6  mov     rdi, rcx
0x180014ba9  lea     rax, ??_8SCMControlHandler@@7BSystemEventSource@@@; const SCMControlHandler::`vbtable'{for `SystemEventSource'}
0x180014bb0  mov     [rcx+8], rax
0x180014bb4  xor     ebp, ebp
0x180014bb6  lea     rax, ??_8SCMControlHandler@@7BServiceStatus@@@; const SCMControlHandler::`vbtable'{for `ServiceStatus'}
0x180014bbd  mov     [rcx+18h], rax
0x180014bc1  lea     rax, ??_7CSimpleRefCount@@6B@; const CSimpleRefCount::`vftable'
0x180014bc8  mov     [rcx+0E8h], rax
0x180014bcf  lea     rax, ??_7SystemEventSource@@6B0@@; const SystemEventSource::`vftable'{for `SystemEventSource'}
0x180014bd6  lea     r14d, [rbp+1]
0x180014bda  mov     [rcx+0F0h], r14d
0x180014be1  mov     [rcx], rax
0x180014be4  mov     rax, [rcx+8]
0x180014be8  movsxd  rcx, dword ptr [rax+4]
0x180014bec  lea     rax, ??_7SystemEventSource@@6BCSimpleRefCount@@@; const SystemEventSource::`vftable'{for `CSimpleRefCount'}
0x180014bf3  mov     [rcx+rdi+8], rax
0x180014bf8  lea     rax, ??_7ServiceStatus@@6B0@@; const ServiceStatus::`vftable'{for `ServiceStatus'}
0x180014bff  mov     [rdi+10h], rax
0x180014c03  mov     rax, [rdi+18h]
0x180014c07  movsxd  rcx, dword ptr [rax+4]
0x180014c0b  lea     rax, ??_7ServiceStatus@@6BCSimpleRefCount@@@; const ServiceStatus::`vftable'{for `CSimpleRefCount'}
0x180014c12  mov     [rcx+rdi+18h], rax
0x180014c17  lea     rax, ??_7SCMControlHandler@@6BSystemEventSource@@@; const SCMControlHandler::`vftable'{for `SystemEventSource'}
0x180014c1e  mov     [rdi], rax
0x180014c21  lea     rax, ??_7SCMControlHandler@@6BServiceStatus@@@; const SCMControlHandler::`vftable'{for `ServiceStatus'}
0x180014c28  mov     [rdi+10h], rax
0x180014c2c  mov     rax, [rdi+8]
0x180014c30  movsxd  rcx, dword ptr [rax+4]
0x180014c34  lea     rax, ??_7SCMControlHandler@@6BCSimpleRefCount@@@; const SCMControlHandler::`vftable'{for `CSimpleRefCount'}
0x180014c3b  mov     [rcx+rdi+8], rax
0x180014c40  lea     rcx, [rdi+30h]; this
0x180014c44  call    ??0CRIT_SECT@@QEAA@XZ; CRIT_SECT::CRIT_SECT(void)
0x180014c49  lea     rcx, [rdi+98h]; this
0x180014c50  call    ??0CRIT_SECT@@QEAA@XZ; CRIT_SECT::CRIT_SECT(void)
0x180014c55  mov     [rdi+88h], rbp
0x180014c5c  xorps   xmm0, xmm0
0x180014c5f  mov     [rdi+90h], rbp
0x180014c66  xor     r9d, r9d; lpName
0x180014c69  mov     dword ptr [rdi+20h], 55537645h
0x180014c70  xor     r8d, r8d; bInitialState
0x180014c73  mov     [rdi+24h], r14d
0x180014c77  xor     edx, edx; bManualReset
0x180014c79  mov     [rdi+28h], rbp
0x180014c7d  xor     ecx, ecx; lpEventAttributes
0x180014c7f  mov     [rdi+60h], rbp
0x180014c83  movups  xmmword ptr [rdi+68h], xmm0
0x180014c87  movups  xmmword ptr [rdi+74h], xmm0
0x180014c8b  mov     [rdi+0E0h], rbp
0x180014c92  call    cs:__imp_CreateEventW
0x180014c98  mov     [rdi+0D0h], rax
0x180014c9f  test    rax, rax
0x180014ca2  jz      loc_180014E3F
0x180014ca8  xor     r9d, r9d; lpName
0x180014cab  xor     r8d, r8d; bInitialState
0x180014cae  xor     edx, edx; bManualReset
0x180014cb0  xor     ecx, ecx; lpEventAttributes
0x180014cb2  call    cs:__imp_CreateEventW
0x180014cb8  mov     [rdi+0D8h], rax
0x180014cbf  test    rax, rax
0x180014cc2  jz      loc_180014DD3
0x180014cc8  mov     [rsp+58h+lpThreadId], rbp; lpThreadId
0x180014ccd  lea     r8, ?ControlThread@SCMControlHandler@@KAKPEAX@Z; lpStartAddress
0x180014cd4  mov     r9, rdi; lpParameter
0x180014cd7  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x180014cdb  xor     edx, edx; dwStackSize
0x180014cdd  xor     ecx, ecx; lpThreadAttributes
0x180014cdf  call    cs:__imp_CreateThread
0x180014ce5  mov     [rdi+0C8h], rax
0x180014cec  test    rax, rax
0x180014cef  jz      short loc_180014D50
0x180014cf1  mov     rcx, rax; Thread
0x180014cf4  call    cs:__imp_GetThreadId
0x180014cfa  lea     r8, aCreatedControl; "Created control thread Id %u"
0x180014d01  xor     edx, edx
0x180014d03  mov     r9d, eax
0x180014d06  xor     ecx, ecx
0x180014d08  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180014d0d  mov     rdx, rax; char *
0x180014d10  lea     rcx, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014d17  mov     rbx, rax
0x180014d1a  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180014d1f  mov     rcx, rbx; this
0x180014d22  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014d27  mov     rcx, [rdi+0C8h]; Thread
0x180014d2e  call    cs:__imp_GetThreadId
0x180014d34  lea     r8, aCreatedControl; "Created control thread Id %u"
0x180014d3b  xor     edx, edx
0x180014d3d  mov     r9d, eax
0x180014d40  xor     ecx, ecx
0x180014d42  call    WiaTrace_TraceWithSubCompTraceLevel
0x180014d47  lea     r9d, [rbp+4]
0x180014d4b  jmp     loc_180014E84
0x180014d50  call    cs:__imp_GetLastError
0x180014d56  mov     edx, eax
0x180014d58  lea     rcx, aCreatethreadFo; "CreateThread for the control thread fai"...
0x180014d5f  call    WiaTrace_TraceLog
0x180014d64  mov     rdx, rax; char *
0x180014d67  lea     rcx, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014d6e  mov     rbx, rax
0x180014d71  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180014d76  mov     rcx, rbx; this
0x180014d79  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014d7e  call    cs:__imp_GetLastError
0x180014d84  mov     edx, eax
0x180014d86  lea     rcx, aCreatethreadFo; "CreateThread for the control thread fai"...
0x180014d8d  call    WiaTrace_Trace
0x180014d92  mov     r9d, r14d; int
0x180014d95  mov     qword ptr [rsp+58h+dwCreationFlags], rax; lpMem
0x180014d9a  lea     r8, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014da1  call    WiaTrace_ProcessTrace_Ex
0x180014da6  mov     rcx, [rdi+0D0h]; hObject
0x180014dad  call    cs:__imp_CloseHandle
0x180014db3  mov     rcx, [rdi+0D8h]; hObject
0x180014dba  mov     [rdi+0D0h], rbp
0x180014dc1  call    cs:__imp_CloseHandle
0x180014dc7  mov     [rdi+0D8h], rbp
0x180014dce  jmp     loc_180014E95
0x180014dd3  call    cs:__imp_GetLastError
0x180014dd9  mov     edx, eax
0x180014ddb  lea     rcx, aCreateeventRes; "CreateEvent(resume control thread) fail"...
0x180014de2  call    WiaTrace_TraceLog
0x180014de7  mov     rdx, rax; char *
0x180014dea  lea     rcx, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014df1  mov     rbx, rax
0x180014df4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180014df9  mov     rcx, rbx; this
0x180014dfc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014e01  call    cs:__imp_GetLastError
0x180014e07  mov     edx, eax
0x180014e09  lea     rcx, aCreateeventRes; "CreateEvent(resume control thread) fail"...
0x180014e10  call    WiaTrace_Trace
0x180014e15  mov     r9d, r14d; int
0x180014e18  mov     qword ptr [rsp+58h+dwCreationFlags], rax; lpMem
0x180014e1d  lea     r8, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014e24  call    WiaTrace_ProcessTrace_Ex
0x180014e29  mov     rcx, [rdi+0D0h]; hObject
0x180014e30  call    cs:__imp_CloseHandle
0x180014e36  mov     [rdi+0D0h], rbp
0x180014e3d  jmp     short loc_180014E95
0x180014e3f  call    cs:__imp_GetLastError
0x180014e45  mov     edx, eax
0x180014e47  lea     rcx, aCreateeventTer; "CreateEvent(terminate control thread) f"...
0x180014e4e  call    WiaTrace_TraceLog
0x180014e53  mov     rdx, rax; char *
0x180014e56  lea     rcx, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014e5d  mov     rbx, rax
0x180014e60  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180014e65  mov     rcx, rbx; this
0x180014e68  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014e6d  call    cs:__imp_GetLastError
0x180014e73  mov     edx, eax
0x180014e75  lea     rcx, aCreateeventTer; "CreateEvent(terminate control thread) f"...
0x180014e7c  call    WiaTrace_Trace
0x180014e81  mov     r9d, r14d; int
0x180014e84  lea     r8, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014e8b  mov     qword ptr [rsp+58h+dwCreationFlags], rax; lpMem
0x180014e90  call    WiaTrace_ProcessTrace_Ex
0x180014e95  cmp     [rdi+0C8h], rbp
0x180014e9c  jnz     short loc_180014EE4
0x180014e9e  lea     rcx, aControlThreadN; "Control thread not created, reverting t"...
0x180014ea5  call    WiaTrace_TraceLog
0x180014eaa  mov     rdx, rax; char *
0x180014ead  lea     rcx, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014eb4  mov     rbx, rax
0x180014eb7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180014ebc  mov     rcx, rbx; this
0x180014ebf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014ec4  lea     rcx, aControlThreadN; "Control thread not created, reverting t"...
0x180014ecb  call    WiaTrace_Trace
0x180014ed0  mov     r9d, r14d; int
0x180014ed3  mov     qword ptr [rsp+58h+dwCreationFlags], rax; lpMem
0x180014ed8  lea     r8, aScmcontrolhand_2; "SCMControlHandler::SCMControlHandler"
0x180014edf  call    WiaTrace_ProcessTrace_Ex
0x180014ee4  mov     rax, rdi
0x180014ee7  add     rsp, 38h
0x180014eeb  pop     r14
0x180014eed  pop     rdi
0x180014eee  pop     rbp
0x180014eef  pop     rbx
0x180014ef0  retn
```
