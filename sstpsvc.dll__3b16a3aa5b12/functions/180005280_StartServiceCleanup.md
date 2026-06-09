# StartServiceCleanup

- ea: `0x180005280`
- end: `0x180005555`
- name: `StartServiceCleanup`
- size: `725`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005920`

## callees

- `0x180005280`
- `0x180005560`
- `0x180006214`
- `0x1800068e0`
- `0x180006a50`
- `0x1800078a4`
- `0x180007c34`
- `0x18000827c`
- `0x180008360`
- `0x1800084e0`
- `0x18000c8d0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800053c7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800053c7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005533`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000543a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000543a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800053f9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800053f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005495`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005495`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800053a9`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800053a9`

## string_xrefs

- `0x18000535e`: `SetCurrentServiceStatus fails with error %d`
- `0x1800052dd`: `StartServiceCleanup`
- `0x1800054c3`: `StartServiceCleanup`
- `0x180005472`: `Cleanup completed. Stopping trace and setting status`

## pseudocode

```c
int StartServiceCleanup()
{
  volatile __int32 *v0; // rcx
  SERVICE_STATUS_HANDLE v1; // rdi
  DWORD LastError; // eax
  TenantGatewayMap *Instance; // rax
  TenantGatewayMap *v4; // rbx
  _QWORD *v5; // r8
  void *v6; // rcx
  void *v7; // rcx
  HANDLE ProcessHeap; // rax
  int result; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-D8h] BYREF
  int v11; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[2044]; // [rsp+54h] [rbp-ACh] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entering %ws", L"StartServiceCleanup");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
  v0 = (volatile __int32 *)SstpSvcGlobals;
  v1 = 0;
  if ( SstpSvcGlobals )
  {
    v1 = (SERVICE_STATUS_HANDLE)*((_QWORD *)SstpSvcGlobals + 5);
    if ( *(_DWORD *)SstpSvcGlobals == 4 )
    {
      *(_QWORD *)SstpSvcGlobals = 3;
      _InterlockedExchange(v0 + 2, 0);
      if ( !(unsigned int)SetCurrentServiceStatus() && (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v11) = 0;
        LastError = GetLastError();
        FormatRRASErrorString(&v11, L"SetCurrentServiceStatus fails with error %d", LastError);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v11);
      }
      v0 = (volatile __int32 *)SstpSvcGlobals;
    }
    if ( *((_DWORD *)v0 + 190) )
    {
      RpcServerUnregisterIf(qword_18001E400, 0, 1u);
      Instance = TenantGatewayMap::GetInstance();
      v4 = Instance;
      if ( Instance )
      {
        TenantGatewayMap::~TenantGatewayMap(Instance);
        operator delete(v4);
      }
    }
    if ( (unsigned int)GetSstpConfigFlag(1) )
      ShutdownSstpServer(0);
    DeinitializeTransport();
    v5 = SstpSvcGlobals;
    v6 = (void *)*((_QWORD *)SstpSvcGlobals + 4);
    if ( v6 )
    {
      if ( !UnregisterWaitEx(v6, 0) && (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasSSTPSvcTraceError,
          L"Failed to Unregister the wait handle");
      v5 = SstpSvcGlobals;
      *((_QWORD *)SstpSvcGlobals + 4) = 0;
    }
    v7 = (void *)v5[3];
    if ( v7 )
    {
      CloseHandle(v7);
      v5 = SstpSvcGlobals;
      *((_QWORD *)SstpSvcGlobals + 3) = 0;
    }
    ConfigureMiniports(0, 2, v5 + 37, v5 + 38);
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"Cleanup completed. Stopping trace and setting status");
    *(_DWORD *)SstpSvcGlobals = 1;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, SstpSvcGlobals);
    SstpSvcGlobals = 0;
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"LEaving %ws", L"StartServiceCleanup");
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
    }
  }
  SstpSvchostGlobal = 0;
  result = RasSstpSvcUnRegisterEtw();
  if ( v1 )
  {
    ServiceStatus.dwServiceType = 32;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwCheckPoint = 0;
    return SetServiceStatus(v1, &ServiceStatus);
  }
  return result;
}

```

## disassembly

```asm
0x180005280  push    rbp
0x180005282  push    rbx
0x180005283  push    rdi
0x180005284  push    r14
0x180005286  lea     rbp, [rsp-768h]
0x18000528e  sub     rsp, 868h
0x180005295  mov     rax, cs:__security_cookie
0x18000529c  xor     rax, rsp
0x18000529f  mov     [rbp+780h+var_30], rax
0x1800052a6  xorps   xmm0, xmm0
0x1800052a9  lea     rcx, [rsp+880h+var_82C]; void *
0x1800052ae  xor     eax, eax
0x1800052b0  xor     edx, edx; Val
0x1800052b2  movups  xmmword ptr [rsp+880h+ServiceStatus.dwServiceType], xmm0
0x1800052b7  mov     r8d, 7FCh; Size
0x1800052bd  mov     [rsp+880h+var_830], eax
0x1800052c1  movups  xmmword ptr [rsp+880h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800052c6  call    memset_0
0x1800052cb  test    cs:byte_18002D803, 10h
0x1800052d2  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800052d9  jz      short loc_180005317
0x1800052db  xor     eax, eax
0x1800052dd  lea     r8, aStartservicecl; "StartServiceCleanup"
0x1800052e4  lea     rdx, aEnteringWs; "Entering %ws"
0x1800052eb  mov     word ptr [rsp+880h+var_830], ax
0x1800052f0  lea     rcx, [rsp+880h+var_830]
0x1800052f5  call    FormatRRASErrorString
0x1800052fa  test    cs:byte_18002D803, 10h
0x180005301  jz      short loc_180005317
0x180005303  lea     r8, [rsp+880h+var_830]
0x180005308  mov     rcx, r14
0x18000530b  lea     rdx, RasSSTPSvcTraceInfo
0x180005312  call    McTemplateU0z_EventWriteTransfer
0x180005317  mov     rcx, cs:SstpSvcGlobals
0x18000531e  xor     edi, edi
0x180005320  test    rcx, rcx
0x180005323  jz      loc_1800054FD
0x180005329  cmp     dword ptr [rcx], 4
0x18000532c  mov     rdi, [rcx+28h]
0x180005330  jnz     short loc_180005393
0x180005332  xor     eax, eax
0x180005334  mov     qword ptr [rcx], 3
0x18000533b  xchg    eax, [rcx+8]
0x18000533e  call    SetCurrentServiceStatus
0x180005343  test    eax, eax
0x180005345  jnz     short loc_18000538C
0x180005347  test    cs:byte_18002D803, 8
0x18000534e  jz      short loc_18000538C
0x180005350  mov     word ptr [rsp+880h+var_830], ax
0x180005355  call    cs:__imp_GetLastError
0x18000535b  mov     r8d, eax
0x18000535e  lea     rdx, aSetcurrentserv; "SetCurrentServiceStatus fails with erro"...
0x180005365  lea     rcx, [rsp+880h+var_830]
0x18000536a  call    FormatRRASErrorString
0x18000536f  test    cs:byte_18002D803, 8
0x180005376  jz      short loc_18000538C
0x180005378  lea     r8, [rsp+880h+var_830]
0x18000537d  mov     rcx, r14
0x180005380  lea     rdx, RasSSTPSvcTraceError
0x180005387  call    McTemplateU0z_EventWriteTransfer
0x18000538c  mov     rcx, cs:SstpSvcGlobals
0x180005393  cmp     dword ptr [rcx+2F8h], 0
0x18000539a  jz      short loc_1800053CD
0x18000539c  xor     edx, edx; MgrTypeUuid
0x18000539e  lea     rcx, qword_18001E400; IfSpec
0x1800053a5  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x1800053a9  call    cs:__imp_RpcServerUnregisterIf
0x1800053af  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x1800053b4  mov     rbx, rax
0x1800053b7  test    rax, rax
0x1800053ba  jz      short loc_1800053CD
0x1800053bc  mov     rcx, rax; this
0x1800053bf  call    ??1TenantGatewayMap@@QEAA@XZ; TenantGatewayMap::~TenantGatewayMap(void)
0x1800053c4  mov     rcx, rbx
0x1800053c7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800053cd  mov     ecx, 1
0x1800053d2  call    GetSstpConfigFlag
0x1800053d7  test    eax, eax
0x1800053d9  jz      short loc_1800053E2
0x1800053db  xor     ecx, ecx
0x1800053dd  call    ShutdownSstpServer
0x1800053e2  call    DeinitializeTransport
0x1800053e7  mov     r8, cs:SstpSvcGlobals
0x1800053ee  mov     rcx, [r8+20h]; WaitHandle
0x1800053f2  test    rcx, rcx
0x1800053f5  jz      short loc_180005431
0x1800053f7  xor     edx, edx; CompletionEvent
0x1800053f9  call    cs:__imp_UnregisterWaitEx
0x1800053ff  test    eax, eax
0x180005401  jnz     short loc_180005422
0x180005403  test    cs:byte_18002D803, 8
0x18000540a  jz      short loc_180005422
0x18000540c  lea     r8, aFailedToUnregi; "Failed to Unregister the wait handle"
0x180005413  mov     rcx, r14
0x180005416  lea     rdx, RasSSTPSvcTraceError
0x18000541d  call    McTemplateU0z_EventWriteTransfer
0x180005422  mov     r8, cs:SstpSvcGlobals
0x180005429  mov     qword ptr [r8+20h], 0
0x180005431  mov     rcx, [r8+18h]; hObject
0x180005435  test    rcx, rcx
0x180005438  jz      short loc_18000544F
0x18000543a  call    cs:__imp_CloseHandle
0x180005440  mov     r8, cs:SstpSvcGlobals
0x180005447  mov     qword ptr [r8+18h], 0
0x18000544f  lea     r9, [r8+130h]
0x180005456  mov     edx, 2
0x18000545b  add     r8, 128h
0x180005462  xor     ecx, ecx
0x180005464  call    ConfigureMiniports
0x180005469  test    cs:byte_18002D803, 10h
0x180005470  jz      short loc_180005488
0x180005472  lea     r8, aCleanupComplet; "Cleanup completed. Stopping trace and s"...
0x180005479  mov     rcx, r14
0x18000547c  lea     rdx, RasSSTPSvcTraceInfo
0x180005483  call    McTemplateU0z_EventWriteTransfer
0x180005488  mov     rax, cs:SstpSvcGlobals
0x18000548f  mov     dword ptr [rax], 1
0x180005495  call    cs:__imp_GetProcessHeap
0x18000549b  mov     r8, cs:SstpSvcGlobals; lpMem
0x1800054a2  xor     edx, edx; dwFlags
0x1800054a4  mov     rcx, rax; hHeap
0x1800054a7  call    cs:__imp_HeapFree
0x1800054ad  test    cs:byte_18002D803, 10h
0x1800054b4  mov     cs:SstpSvcGlobals, 0
0x1800054bf  jz      short loc_1800054FD
0x1800054c1  xor     eax, eax
0x1800054c3  lea     r8, aStartservicecl; "StartServiceCleanup"
0x1800054ca  lea     rdx, aLeavingWs; "LEaving %ws"
0x1800054d1  mov     word ptr [rsp+880h+var_830], ax
0x1800054d6  lea     rcx, [rsp+880h+var_830]
0x1800054db  call    FormatRRASErrorString
0x1800054e0  test    cs:byte_18002D803, 10h
0x1800054e7  jz      short loc_1800054FD
0x1800054e9  lea     r8, [rsp+880h+var_830]
0x1800054ee  mov     rcx, r14
0x1800054f1  lea     rdx, RasSSTPSvcTraceInfo
0x1800054f8  call    McTemplateU0z_EventWriteTransfer
0x1800054fd  mov     cs:SstpSvchostGlobal, 0
0x180005508  call    RasSstpSvcUnRegisterEtw
0x18000550d  test    rdi, rdi
0x180005510  jz      short loc_180005539
0x180005512  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180005517  mov     [rsp+880h+ServiceStatus.dwServiceType], 20h ; ' '
0x18000551f  mov     rcx, rdi; hServiceStatus
0x180005522  mov     qword ptr [rsp+880h+ServiceStatus.dwCurrentState], 1
0x18000552b  mov     [rsp+880h+ServiceStatus.dwCheckPoint], 0
0x180005533  call    cs:__imp_SetServiceStatus
0x180005539  mov     rcx, [rbp+780h+var_30]
0x180005540  xor     rcx, rsp; StackCookie
0x180005543  call    __security_check_cookie
0x180005548  add     rsp, 868h
0x18000554f  pop     r14
0x180005551  pop     rdi
0x180005552  pop     rbx
0x180005553  pop     rbp
0x180005554  retn
```
