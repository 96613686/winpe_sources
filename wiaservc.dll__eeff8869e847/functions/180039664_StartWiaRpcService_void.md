# StartWiaRpcService(void)

- ea: `0x180039664`
- end: `0x180039b38`
- name: `?StartWiaRpcService@@YAHXZ`
- size: `1236`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800033f4`
- `0x18004c370`

## callees

- `0x180004380`
- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180039664`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x1800396eb`
- `ADVAPI32!OpenServiceW` at `0x1800396eb`
- `ADVAPI32!StartServiceW` at `0x180039705`
- `ADVAPI32!StartServiceW` at `0x180039705`
- `ADVAPI32!OpenSCManagerW` at `0x1800396c6`
- `ADVAPI32!OpenSCManagerW` at `0x1800396c6`
- `ADVAPI32!CloseServiceHandle` at `0x1800399a6`
- `ADVAPI32!CloseServiceHandle` at `0x180039a0a`
- `ADVAPI32!CloseServiceHandle` at `0x1800399a6`
- `ADVAPI32!CloseServiceHandle` at `0x180039a0a`
- `ADVAPI32!QueryServiceStatus` at `0x18003971a`
- `ADVAPI32!QueryServiceStatus` at `0x180039781`
- `ADVAPI32!QueryServiceStatus` at `0x180039908`
- `ADVAPI32!QueryServiceStatus` at `0x18003971a`
- `ADVAPI32!QueryServiceStatus` at `0x180039781`
- `ADVAPI32!QueryServiceStatus` at `0x180039908`
- `KERNEL32!GetTickCount` at `0x180039767`
- `KERNEL32!GetTickCount` at `0x1800397c5`
- `KERNEL32!GetTickCount` at `0x1800397cd`
- `KERNEL32!GetTickCount` at `0x180039767`
- `KERNEL32!GetTickCount` at `0x1800397c5`
- `KERNEL32!GetTickCount` at `0x1800397cd`
- `KERNEL32!WaitForSingleObject` at `0x180039a24`
- `KERNEL32!WaitForSingleObject` at `0x180039a24`
- `KERNEL32!Sleep` at `0x1800397b9`
- `KERNEL32!Sleep` at `0x1800397b9`
- `KERNEL32!GetLastError` at `0x180039724`
- `KERNEL32!GetLastError` at `0x180039752`
- `KERNEL32!GetLastError` at `0x18003989e`
- `KERNEL32!GetLastError` at `0x1800399ae`
- `KERNEL32!GetLastError` at `0x1800399dc`
- `KERNEL32!GetLastError` at `0x180039a76`
- `KERNEL32!GetLastError` at `0x180039aa3`
- `KERNEL32!GetLastError` at `0x180039abc`
- `KERNEL32!GetLastError` at `0x180039ae6`
- `KERNEL32!GetLastError` at `0x180039724`
- `KERNEL32!GetLastError` at `0x180039752`
- `KERNEL32!GetLastError` at `0x18003989e`
- `KERNEL32!GetLastError` at `0x1800399ae`
- `KERNEL32!GetLastError` at `0x1800399dc`
- `KERNEL32!GetLastError` at `0x180039a76`
- `KERNEL32!GetLastError` at `0x180039aa3`
- `KERNEL32!GetLastError` at `0x180039abc`
- `KERNEL32!GetLastError` at `0x180039ae6`

## string_xrefs

- `0x1800396a4`: `StartWiaRpcService`
- `0x18003972d`: `QueryServiceStatus(%ws) failed, error code 0x%08X`
- `0x18003975b`: `QueryServiceStatus(%ws) failed, error code 0x%08X`
- `0x1800397e7`: `The %ws service was successfully started`
- `0x180039810`: `The %ws service was successfully started`
- `0x180039840`: `The %ws service timed out failing to start and enter the SERVICE_RUNNING state. Current state: %d. Exit Code: %d. Check Point: %d. Wait Hint: %d`
- `0x180039877`: `The %ws service timed out failing to start and enter the SERVICE_RUNNING state. Current state: %d. Exit Code: %d. Check Point: %d. Wait Hint: %d`
- `0x1800398b5`: `The %ws service is already running`
- `0x1800398de`: `The %ws service is already running`
- `0x180039927`: `The %ws service appears to be already running but is not in the SERVICE_RUNNING state (current service state: 0x%08X)`
- `0x18003994d`: `The %ws service appears to be already running but is not in the SERVICE_RUNNING state (current service state: 0x%08X)`
- `0x180039959`: `StartService(%ws) failed. Error code 0x%08X`
- `0x180039981`: `StartService(%ws) failed. Error code 0x%08X`
- `0x1800399b7`: `OpenService(%ws, SERVICE_INTERROGATE | SERVICE_QUERY_STATUS | SERVICE_START) failed. Error code 0x%08X`
- `0x1800399e5`: `OpenService(%ws, SERVICE_INTERROGATE | SERVICE_QUERY_STATUS | SERVICE_START) failed. Error code 0x%08X`
- `0x180039ac4`: `OpenSCManager(STANDARD_RIGHTS_READ) failed. Error code 0x%08X`
- `0x180039aee`: `OpenSCManager(STANDARD_RIGHTS_READ) failed. Error code 0x%08X`

## pseudocode

```c
__int64 StartWiaRpcService(void)
{
  unsigned int v0; // edi
  char ***v1; // rax
  char *v2; // rdx
  __int64 v3; // r8
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r15
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rsi
  char *v8; // rbx
  void *v9; // rdx
  __int64 v10; // r8
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  DWORD TickCount; // eax
  DWORD dwCheckPoint; // r14d
  DWORD v16; // ebx
  BOOL v17; // eax
  DWORD dwCurrentState; // r8d
  DWORD v19; // edx
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  char *v25; // rbx
  void *v26; // rdx
  DWORD v27; // r14d
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  char *v35; // rbx
  void *v36; // rdx
  char *v37; // rbx
  void *v38; // rdx
  DWORD v39; // eax
  void **v40; // rax
  void *v41; // rdx
  __int64 v42; // rcx
  DWORD v43; // eax
  char *v44; // rbx
  void *v45; // rdx
  void **v46; // rax
  void *v47; // rdx
  __int64 v48; // rcx
  int v49; // r9d
  DWORD v50; // eax
  char *v51; // rbx
  void *v52; // rdx
  DWORD v53; // eax
  char *v54; // rbx
  void *v55; // rdx
  DWORD LastError; // eax
  unsigned int lpMem; // [rsp+20h] [rbp-79h]
  LPVOID lpMema; // [rsp+20h] [rbp-79h]
  struct tagWiaTraceData_Type *v60; // [rsp+28h] [rbp-71h]
  _BYTE v61[80]; // [rsp+30h] [rbp-69h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-19h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = 0;
  v1 = (char ***)WiaTrace_Trace(&Class);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v61, v2, v3, (char **)"StartWiaRpcService", lpMem, v1);
  v4 = OpenSCManagerW(0, 0, 0x20015u);
  v5 = v4;
  if ( !v4 )
  {
    GetLastError();
    v54 = (char *)WiaTrace_TraceLog("OpenSCManager(STANDARD_RIGHTS_READ) failed. Error code 0x%08X");
    WriteDbgTraceErrorWI("StartWiaRpcService", v54);
    WiaTrcLib::Free((WiaTrcLib *)v54, v55);
    LastError = GetLastError();
    v46 = (void **)WiaTrace_Trace("OpenSCManager(STANDARD_RIGHTS_READ) failed. Error code 0x%08X", LastError);
    v49 = 1;
    goto LABEL_37;
  }
  v6 = OpenServiceW(v4, L"WiaRpc", 0x94u);
  v7 = v6;
  if ( v6 )
  {
    if ( StartServiceW(v6, 0, 0) )
    {
      if ( !QueryServiceStatus(v7, &ServiceStatus) )
      {
LABEL_5:
        GetLastError();
        v8 = (char *)WiaTrace_TraceLog("QueryServiceStatus(%ws) failed, error code 0x%08X");
        WriteDbgTraceErrorWI("StartWiaRpcService", v8);
        WiaTrcLib::Free((WiaTrcLib *)v8, v9);
        v10 = GetLastError();
        v11 = (void **)WiaTrace_Trace("QueryServiceStatus(%ws) failed, error code 0x%08X", L"WiaRpc", v10);
LABEL_27:
        WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"StartWiaRpcService", 1, v11);
        goto LABEL_28;
      }
      TickCount = GetTickCount();
      ServiceStatus.dwCurrentState = 2;
LABEL_7:
      dwCheckPoint = ServiceStatus.dwCheckPoint;
      v16 = TickCount;
      while ( 1 )
      {
        v17 = QueryServiceStatus(v7, &ServiceStatus);
        dwCurrentState = ServiceStatus.dwCurrentState;
        if ( !v17 || ServiceStatus.dwCurrentState != 2 )
          break;
        v19 = ServiceStatus.dwWaitHint / 0xA;
        if ( ServiceStatus.dwWaitHint / 0xA >= 0x3E8 )
        {
          if ( v19 > 0x2710 )
            v19 = 10000;
        }
        else
        {
          v19 = 1000;
        }
        Sleep(v19);
        if ( ServiceStatus.dwCheckPoint > dwCheckPoint )
        {
          TickCount = GetTickCount();
          goto LABEL_7;
        }
        if ( GetTickCount() - v16 > ServiceStatus.dwWaitHint )
        {
          dwCurrentState = ServiceStatus.dwCurrentState;
          break;
        }
      }
      if ( dwCurrentState != 4 )
      {
        v25 = (char *)WiaTrace_TraceLog("The %ws service timed out failing to start and enter the SERVICE_RUNNING state. "
                                        "Current state: %d. Exit Code: %d. Check Point: %d. Wait Hint: %d");
        WriteDbgTraceErrorWI("StartWiaRpcService", v25);
        WiaTrcLib::Free((WiaTrcLib *)v25, v26);
        LODWORD(v60) = ServiceStatus.dwWaitHint;
        LODWORD(lpMema) = ServiceStatus.dwCheckPoint;
        v11 = (void **)WiaTrace_Trace(
                         "The %ws service timed out failing to start and enter the SERVICE_RUNNING state. Current state: "
                         "%d. Exit Code: %d. Check Point: %d. Wait Hint: %d",
                         L"WiaRpc",
                         ServiceStatus.dwCurrentState,
                         ServiceStatus.dwWin32ExitCode,
                         lpMema,
                         v60);
        goto LABEL_27;
      }
      v20 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "The %ws service was successfully started", L"WiaRpc");
      WriteDbgTraceInfoWI("StartWiaRpcService", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      v22 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "The %ws service was successfully started", L"WiaRpc");
      WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"StartWiaRpcService", 4, v22);
    }
    else
    {
      v27 = GetLastError();
      if ( v27 != 1056 )
      {
        v35 = (char *)WiaTrace_TraceLog("StartService(%ws) failed. Error code 0x%08X");
        WriteDbgTraceErrorWI("StartWiaRpcService", v35);
        WiaTrcLib::Free((WiaTrcLib *)v35, v36);
        v11 = (void **)WiaTrace_Trace("StartService(%ws) failed. Error code 0x%08X", L"WiaRpc", v27);
        goto LABEL_27;
      }
      v28 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "The %ws service is already running", L"WiaRpc");
      WriteDbgTraceInfoWI("StartWiaRpcService", v28);
      WiaTrcLib::Free((WiaTrcLib *)v28, v29);
      v30 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "The %ws service is already running", L"WiaRpc");
      WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"StartWiaRpcService", 4, v30);
      if ( !QueryServiceStatus(v7, &ServiceStatus) )
        goto LABEL_5;
      if ( ServiceStatus.dwCurrentState != 4 )
      {
        v33 = (char *)WiaTrace_TraceLog("The %ws service appears to be already running but is not in the SERVICE_RUNNING "
                                        "state (current service state: 0x%08X)");
        WriteDbgTraceErrorWI("StartWiaRpcService", v33);
        WiaTrcLib::Free((WiaTrcLib *)v33, v34);
        v11 = (void **)WiaTrace_Trace(
                         "The %ws service appears to be already running but is not in the SERVICE_RUNNING state (current "
                         "service state: 0x%08X)",
                         L"WiaRpc",
                         ServiceStatus.dwCurrentState);
        goto LABEL_27;
      }
    }
    v0 = 1;
LABEL_28:
    CloseServiceHandle(v7);
    goto LABEL_30;
  }
  GetLastError();
  v37 = (char *)WiaTrace_TraceLog("OpenService(%ws, SERVICE_INTERROGATE | SERVICE_QUERY_STATUS | SERVICE_START) failed. E"
                                  "rror code 0x%08X");
  WriteDbgTraceErrorWI("StartWiaRpcService", v37);
  WiaTrcLib::Free((WiaTrcLib *)v37, v38);
  v39 = GetLastError();
  v40 = (void **)WiaTrace_Trace(
                   "OpenService(%ws, SERVICE_INTERROGATE | SERVICE_QUERY_STATUS | SERVICE_START) failed. Error code 0x%08X",
                   L"WiaRpc",
                   v39);
  WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"StartWiaRpcService", 1, v40);
LABEL_30:
  CloseServiceHandle(v5);
  if ( v0 )
  {
    v43 = WaitForSingleObject(g_hWiaRpcAsyncCallEvent, 0xFA0u);
    if ( v43 == 258 )
    {
      v44 = (char *)WiaTrace_TraceLogWithSubComp(
                      0,
                      "Async RPC call from WiaRpc not received in time. Handling of the current STI/WIA event may fail");
      WriteDbgTraceWarningWI("StartWiaRpcService", v44);
      WiaTrcLib::Free((WiaTrcLib *)v44, v45);
      v46 = (void **)WiaTrace_TraceWithSubComp(
                       0,
                       "Async RPC call from WiaRpc not received in time. Handling of the current STI/WIA event may fail");
LABEL_33:
      v49 = 2;
LABEL_37:
      WiaTrace_ProcessTrace_Ex(v48, v47, (void *)"StartWiaRpcService", v49, v46);
      goto LABEL_38;
    }
    if ( v43 )
    {
      v50 = GetLastError();
      v51 = (char *)WiaTrace_TraceLogWithSubComp(
                      0,
                      "WaitForSingleObject failed. Error code 0x%08X. Handling of the current STI/WIA event may fail",
                      v50);
      WriteDbgTraceWarningWI("StartWiaRpcService", v51);
      WiaTrcLib::Free((WiaTrcLib *)v51, v52);
      v53 = GetLastError();
      v46 = (void **)WiaTrace_TraceWithSubComp(
                       0,
                       "WaitForSingleObject failed. Error code 0x%08X. Handling of the current STI/WIA event may fail",
                       v53);
      goto LABEL_33;
    }
  }
LABEL_38:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v61);
  return v0;
}

```

## disassembly

```asm
0x180039664  push    rbp
0x180039666  push    rbx
0x180039667  push    rsi
0x180039668  push    rdi
0x180039669  push    r12
0x18003966b  push    r13
0x18003966d  push    r14
0x18003966f  push    r15
0x180039671  lea     rbp, [rsp-1Fh]
0x180039676  sub     rsp, 0B8h
0x18003967d  mov     rax, cs:__security_cookie
0x180039684  xor     rax, rsp
0x180039687  mov     [rbp+57h+var_50], rax
0x18003968b  xorps   xmm0, xmm0
0x18003968e  lea     rcx, Class; unsigned __int16 *
0x180039695  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180039699  xor     edi, edi
0x18003969b  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003969f  call    ?WiaTrace_Trace@@YAPEAUtagWiaTraceData_Type@@PEBGZZ; WiaTrace_Trace(ushort const *,...)
0x1800396a4  lea     r12, aStartwiarpcser; "StartWiaRpcService"
0x1800396ab  mov     [rsp+0F0h+var_C8], rax; struct tagWiaTraceData_Type *
0x1800396b0  mov     r9, r12; char *
0x1800396b3  lea     rcx, [rbp+57h+var_C0]; this
0x1800396b7  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800396bc  xor     edx, edx; lpDatabaseName
0x1800396be  xor     ecx, ecx; lpMachineName
0x1800396c0  mov     r8d, 20015h; dwDesiredAccess
0x1800396c6  call    cs:__imp_OpenSCManagerW
0x1800396cc  mov     r15, rax
0x1800396cf  test    rax, rax
0x1800396d2  jz      loc_180039ABC
0x1800396d8  lea     r13, ServiceName; "WiaRpc"
0x1800396df  mov     r8d, 94h; dwDesiredAccess
0x1800396e5  mov     rdx, r13; lpServiceName
0x1800396e8  mov     rcx, rax; hSCManager
0x1800396eb  call    cs:__imp_OpenServiceW
0x1800396f1  mov     rsi, rax
0x1800396f4  test    rax, rax
0x1800396f7  jz      loc_1800399AE
0x1800396fd  xor     r8d, r8d; lpServiceArgVectors
0x180039700  xor     edx, edx; dwNumServiceArgs
0x180039702  mov     rcx, rax; hService
0x180039705  call    cs:__imp_StartServiceW
0x18003970b  test    eax, eax
0x18003970d  jz      loc_18003989E
0x180039713  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180039717  mov     rcx, rsi; hService
0x18003971a  call    cs:__imp_QueryServiceStatus
0x180039720  test    eax, eax
0x180039722  jnz     short loc_180039767
0x180039724  call    cs:__imp_GetLastError
0x18003972a  mov     rdx, r13
0x18003972d  lea     rcx, aQueryservicest; "QueryServiceStatus(%ws) failed, error c"...
0x180039734  mov     r8d, eax
0x180039737  call    WiaTrace_TraceLog
0x18003973c  mov     rdx, rax; char *
0x18003973f  mov     rcx, r12; char *
0x180039742  mov     rbx, rax
0x180039745  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003974a  mov     rcx, rbx; this
0x18003974d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039752  call    cs:__imp_GetLastError
0x180039758  mov     r8d, eax
0x18003975b  lea     rcx, aQueryservicest; "QueryServiceStatus(%ws) failed, error c"...
0x180039762  jmp     loc_180039988
0x180039767  call    cs:__imp_GetTickCount
0x18003976d  mov     [rbp+57h+ServiceStatus.dwCurrentState], 2
0x180039774  mov     r14d, [rbp+57h+ServiceStatus.dwCheckPoint]
0x180039778  mov     ebx, eax
0x18003977a  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18003977e  mov     rcx, rsi; hService
0x180039781  call    cs:__imp_QueryServiceStatus
0x180039787  mov     r8d, [rbp+57h+ServiceStatus.dwCurrentState]
0x18003978b  test    eax, eax
0x18003978d  jz      short loc_1800397DE
0x18003978f  cmp     r8d, 2
0x180039793  jnz     short loc_1800397DE
0x180039795  mov     eax, 0CCCCCCCDh
0x18003979a  mul     [rbp+57h+ServiceStatus.dwWaitHint]
0x18003979d  mov     eax, 3E8h
0x1800397a2  shr     edx, 3
0x1800397a5  cmp     edx, eax
0x1800397a7  jnb     short loc_1800397AD
0x1800397a9  mov     edx, eax
0x1800397ab  jmp     short loc_1800397B7
0x1800397ad  mov     eax, 2710h
0x1800397b2  cmp     edx, eax
0x1800397b4  cmova   edx, eax
0x1800397b7  mov     ecx, edx; dwMilliseconds
0x1800397b9  call    cs:__imp_Sleep
0x1800397bf  cmp     [rbp+57h+ServiceStatus.dwCheckPoint], r14d
0x1800397c3  jbe     short loc_1800397CD
0x1800397c5  call    cs:__imp_GetTickCount
0x1800397cb  jmp     short loc_180039774
0x1800397cd  call    cs:__imp_GetTickCount
0x1800397d3  sub     eax, ebx
0x1800397d5  cmp     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x1800397d8  jbe     short loc_18003977A
0x1800397da  mov     r8d, [rbp+57h+ServiceStatus.dwCurrentState]
0x1800397de  cmp     r8d, 4
0x1800397e2  jnz     short loc_18003983D
0x1800397e4  mov     r9, r13
0x1800397e7  lea     r8, aTheWsServiceWa; "The %ws service was successfully starte"...
0x1800397ee  xor     edx, edx
0x1800397f0  xor     ecx, ecx
0x1800397f2  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800397f7  mov     rdx, rax; char *
0x1800397fa  mov     rcx, r12; char *
0x1800397fd  mov     rbx, rax
0x180039800  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180039805  mov     rcx, rbx; this
0x180039808  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003980d  mov     r9, r13
0x180039810  lea     r8, aTheWsServiceWa; "The %ws service was successfully starte"...
0x180039817  xor     edx, edx
0x180039819  xor     ecx, ecx
0x18003981b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180039820  mov     r9d, 4; int
0x180039826  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18003982b  mov     r8, r12; int
0x18003982e  call    WiaTrace_ProcessTrace_Ex
0x180039833  mov     edi, 1
0x180039838  jmp     loc_1800399A3
0x18003983d  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x180039840  lea     rcx, aTheWsServiceTi; "The %ws service timed out failing to st"...
0x180039847  mov     r9d, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18003984b  mov     rdx, r13
0x18003984e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180039852  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x180039855  mov     dword ptr [rsp+0F0h+lpMem], eax
0x180039859  call    WiaTrace_TraceLog
0x18003985e  mov     rdx, rax; char *
0x180039861  mov     rcx, r12; char *
0x180039864  mov     rbx, rax
0x180039867  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003986c  mov     rcx, rbx; this
0x18003986f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039874  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x180039877  lea     rcx, aTheWsServiceTi; "The %ws service timed out failing to st"...
0x18003987e  mov     r9d, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x180039882  mov     rdx, r13
0x180039885  mov     r8d, [rbp+57h+ServiceStatus.dwCurrentState]
0x180039889  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18003988d  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x180039890  mov     dword ptr [rsp+0F0h+lpMem], eax
0x180039894  call    WiaTrace_Trace
0x180039899  jmp     loc_180039990
0x18003989e  call    cs:__imp_GetLastError
0x1800398a4  mov     r14d, eax
0x1800398a7  cmp     eax, 420h
0x1800398ac  jnz     loc_180039956
0x1800398b2  mov     r9, r13
0x1800398b5  lea     r8, aTheWsServiceIs; "The %ws service is already running"
0x1800398bc  xor     edx, edx
0x1800398be  xor     ecx, ecx
0x1800398c0  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800398c5  mov     rdx, rax; char *
0x1800398c8  mov     rcx, r12; char *
0x1800398cb  mov     rbx, rax
0x1800398ce  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800398d3  mov     rcx, rbx; this
0x1800398d6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800398db  mov     r9, r13
0x1800398de  lea     r8, aTheWsServiceIs; "The %ws service is already running"
0x1800398e5  xor     edx, edx
0x1800398e7  xor     ecx, ecx
0x1800398e9  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800398ee  mov     r9d, 4; int
0x1800398f4  mov     [rsp+0F0h+lpMem], rax; lpMem
0x1800398f9  mov     r8, r12; int
0x1800398fc  call    WiaTrace_ProcessTrace_Ex
0x180039901  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180039905  mov     rcx, rsi; hService
0x180039908  call    cs:__imp_QueryServiceStatus
0x18003990e  test    eax, eax
0x180039910  jz      loc_180039724
0x180039916  mov     r8d, [rbp+57h+ServiceStatus.dwCurrentState]
0x18003991a  cmp     r8d, 4
0x18003991e  jz      loc_180039833
0x180039924  mov     rdx, r13
0x180039927  lea     rcx, aTheWsServiceAp; "The %ws service appears to be already r"...
0x18003992e  call    WiaTrace_TraceLog
0x180039933  mov     rdx, rax; char *
0x180039936  mov     rcx, r12; char *
0x180039939  mov     rbx, rax
0x18003993c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180039941  mov     rcx, rbx; this
0x180039944  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039949  mov     r8d, [rbp+57h+ServiceStatus.dwCurrentState]
0x18003994d  lea     rcx, aTheWsServiceAp; "The %ws service appears to be already r"...
0x180039954  jmp     short loc_180039988
0x180039956  mov     r8d, r14d
0x180039959  lea     rcx, aStartserviceWs; "StartService(%ws) failed. Error code 0x"...
0x180039960  mov     rdx, r13
0x180039963  call    WiaTrace_TraceLog
0x180039968  mov     rdx, rax; char *
0x18003996b  mov     rcx, r12; char *
0x18003996e  mov     rbx, rax
0x180039971  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180039976  mov     rcx, rbx; this
0x180039979  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003997e  mov     r8d, r14d
0x180039981  lea     rcx, aStartserviceWs; "StartService(%ws) failed. Error code 0x"...
0x180039988  mov     rdx, r13
0x18003998b  call    WiaTrace_Trace
0x180039990  mov     r9d, 1; int
0x180039996  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18003999b  mov     r8, r12; int
0x18003999e  call    WiaTrace_ProcessTrace_Ex
0x1800399a3  mov     rcx, rsi; hSCObject
0x1800399a6  call    cs:__imp_CloseServiceHandle
0x1800399ac  jmp     short loc_180039A07
0x1800399ae  call    cs:__imp_GetLastError
0x1800399b4  mov     rdx, r13
0x1800399b7  lea     rcx, aOpenserviceWsS; "OpenService(%ws, SERVICE_INTERROGATE | "...
0x1800399be  mov     r8d, eax
0x1800399c1  call    WiaTrace_TraceLog
0x1800399c6  mov     rdx, rax; char *
0x1800399c9  mov     rcx, r12; char *
0x1800399cc  mov     rbx, rax
0x1800399cf  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800399d4  mov     rcx, rbx; this
0x1800399d7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800399dc  call    cs:__imp_GetLastError
0x1800399e2  mov     rdx, r13
0x1800399e5  lea     rcx, aOpenserviceWsS; "OpenService(%ws, SERVICE_INTERROGATE | "...
0x1800399ec  mov     r8d, eax
0x1800399ef  call    WiaTrace_Trace
0x1800399f4  mov     r9d, 1; int
0x1800399fa  mov     [rsp+0F0h+lpMem], rax; lpMem
0x1800399ff  mov     r8, r12; int
0x180039a02  call    WiaTrace_ProcessTrace_Ex
0x180039a07  mov     rcx, r15; hSCObject
0x180039a0a  call    cs:__imp_CloseServiceHandle
0x180039a10  test    edi, edi
0x180039a12  jz      loc_180039B0D
0x180039a18  mov     rcx, cs:?g_hWiaRpcAsyncCallEvent@@3PEAXEA; hHandle
0x180039a1f  mov     edx, 0FA0h; dwMilliseconds
0x180039a24  call    cs:__imp_WaitForSingleObject
0x180039a2a  cmp     eax, 102h
0x180039a2f  jnz     short loc_180039A6E
0x180039a31  lea     rdx, aAsyncRpcCallFr; "Async RPC call from WiaRpc not received"...
0x180039a38  xor     ecx, ecx
0x180039a3a  call    WiaTrace_TraceLogWithSubComp
0x180039a3f  mov     rdx, rax; char *
0x180039a42  mov     rcx, r12; char *
0x180039a45  mov     rbx, rax
0x180039a48  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180039a4d  mov     rcx, rbx; this
0x180039a50  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039a55  lea     rdx, aAsyncRpcCallFr; "Async RPC call from WiaRpc not received"...
0x180039a5c  xor     ecx, ecx
0x180039a5e  call    WiaTrace_TraceWithSubComp
0x180039a63  mov     r9d, 2
0x180039a69  jmp     loc_180039B00
0x180039a6e  test    eax, eax
0x180039a70  jz      loc_180039B0D
0x180039a76  call    cs:__imp_GetLastError
0x180039a7c  lea     rdx, aWaitforsingleo; "WaitForSingleObject failed. Error code "...
0x180039a83  xor     ecx, ecx
0x180039a85  mov     r8d, eax
0x180039a88  call    WiaTrace_TraceLogWithSubComp
0x180039a8d  mov     rdx, rax; char *
0x180039a90  mov     rcx, r12; char *
0x180039a93  mov     rbx, rax
0x180039a96  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180039a9b  mov     rcx, rbx; this
0x180039a9e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039aa3  call    cs:__imp_GetLastError
0x180039aa9  lea     rdx, aWaitforsingleo; "WaitForSingleObject failed. Error code "...
0x180039ab0  xor     ecx, ecx
0x180039ab2  mov     r8d, eax
0x180039ab5  call    WiaTrace_TraceWithSubComp
0x180039aba  jmp     short loc_180039A63
0x180039abc  call    cs:__imp_GetLastError
0x180039ac2  mov     edx, eax
0x180039ac4  lea     rcx, aOpenscmanagerS; "OpenSCManager(STANDARD_RIGHTS_READ) fai"...
0x180039acb  call    WiaTrace_TraceLog
0x180039ad0  mov     rdx, rax; char *
0x180039ad3  mov     rcx, r12; char *
0x180039ad6  mov     rbx, rax
0x180039ad9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180039ade  mov     rcx, rbx; this
0x180039ae1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039ae6  call    cs:__imp_GetLastError
0x180039aec  mov     edx, eax
0x180039aee  lea     rcx, aOpenscmanagerS; "OpenSCManager(STANDARD_RIGHTS_READ) fai"...
0x180039af5  call    WiaTrace_Trace
0x180039afa  mov     r9d, 1; int
0x180039b00  mov     r8, r12; int
0x180039b03  mov     [rsp+0F0h+lpMem], rax; lpMem
0x180039b08  call    WiaTrace_ProcessTrace_Ex
0x180039b0d  lea     rcx, [rbp+57h+var_C0]; this
0x180039b11  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180039b16  mov     eax, edi
0x180039b18  mov     rcx, [rbp+57h+var_50]
0x180039b1c  xor     rcx, rsp; StackCookie
0x180039b1f  call    __security_check_cookie
0x180039b24  add     rsp, 0B8h
0x180039b2b  pop     r15
  ... truncated ...
```
