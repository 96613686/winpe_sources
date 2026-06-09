# StartServiceCleanup

- ea: `0x1800056e0`
- end: `0x1800059e6`
- name: `StartServiceCleanup`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005e30`

## callees

- `0x1800056e0`
- `0x1800059f0`
- `0x1800067b4`
- `0x180006f00`
- `0x180007110`
- `0x180008020`
- `0x180008404`
- `0x1800089dc`
- `0x180008b90`
- `0x180008d3c`
- `0x18000d444`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005833`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005833`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800059bd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800059bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000586b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000586b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000592b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000592b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005913`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005913`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000580f`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000580f`

## string_xrefs

- `0x1800057c4`: `SetCurrentServiceStatus fails with error %d`
- `0x18000573d`: `StartServiceCleanup`
- `0x18000594d`: `StartServiceCleanup`
- `0x1800058f0`: `Cleanup completed. Stopping trace and setting status`

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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entering %ws", L"StartServiceCleanup");
    if ( (byte_18002E903 & 0x10) != 0 )
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
      if ( !(unsigned int)SetCurrentServiceStatus() && (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v11) = 0;
        LastError = GetLastError();
        FormatRRASErrorString(&v11, L"SetCurrentServiceStatus fails with error %d", LastError);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v11);
      }
      v0 = (volatile __int32 *)SstpSvcGlobals;
    }
    if ( *((_DWORD *)v0 + 190) )
    {
      RpcServerUnregisterIf(qword_18001F400, 0, 1u);
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
      if ( !UnregisterWaitEx(v6, 0) && (byte_18002E903 & 8) != 0 )
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
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"Cleanup completed. Stopping trace and setting status");
    *(_DWORD *)SstpSvcGlobals = 1;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, SstpSvcGlobals);
    SstpSvcGlobals = 0;
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"LEaving %ws", L"StartServiceCleanup");
      if ( (byte_18002E903 & 0x10) != 0 )
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
0x1800056e0  push    rbp
0x1800056e2  push    rbx
0x1800056e3  push    rdi
0x1800056e4  push    r14
0x1800056e6  lea     rbp, [rsp-768h]
0x1800056ee  sub     rsp, 868h
0x1800056f5  mov     rax, cs:__security_cookie
0x1800056fc  xor     rax, rsp
0x1800056ff  mov     [rbp+780h+var_30], rax
0x180005706  xorps   xmm0, xmm0
0x180005709  lea     rcx, [rsp+880h+var_82C]; void *
0x18000570e  xor     eax, eax
0x180005710  xor     edx, edx; Val
0x180005712  movups  xmmword ptr [rsp+880h+ServiceStatus.dwServiceType], xmm0
0x180005717  mov     r8d, 7FCh; Size
0x18000571d  mov     [rsp+880h+var_830], eax
0x180005721  movups  xmmword ptr [rsp+880h+ServiceStatus.dwWin32ExitCode], xmm0
0x180005726  call    memset_0
0x18000572b  test    cs:byte_18002E903, 10h
0x180005732  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005739  jz      short loc_180005777
0x18000573b  xor     eax, eax
0x18000573d  lea     r8, aStartservicecl; "StartServiceCleanup"
0x180005744  lea     rdx, aEnteringWs; "Entering %ws"
0x18000574b  mov     word ptr [rsp+880h+var_830], ax
0x180005750  lea     rcx, [rsp+880h+var_830]
0x180005755  call    FormatRRASErrorString
0x18000575a  test    cs:byte_18002E903, 10h
0x180005761  jz      short loc_180005777
0x180005763  lea     r8, [rsp+880h+var_830]
0x180005768  mov     rcx, r14
0x18000576b  lea     rdx, RasSSTPSvcTraceInfo
0x180005772  call    McTemplateU0z_EventWriteTransfer
0x180005777  mov     rcx, cs:SstpSvcGlobals
0x18000577e  xor     edi, edi
0x180005780  test    rcx, rcx
0x180005783  jz      loc_180005987
0x180005789  cmp     dword ptr [rcx], 4
0x18000578c  mov     rdi, [rcx+28h]
0x180005790  jnz     short loc_1800057F9
0x180005792  xor     eax, eax
0x180005794  mov     qword ptr [rcx], 3
0x18000579b  xchg    eax, [rcx+8]
0x18000579e  call    SetCurrentServiceStatus
0x1800057a3  test    eax, eax
0x1800057a5  jnz     short loc_1800057F2
0x1800057a7  test    cs:byte_18002E903, 8
0x1800057ae  jz      short loc_1800057F2
0x1800057b0  mov     word ptr [rsp+880h+var_830], ax
0x1800057b5  call    cs:__imp_GetLastError
0x1800057bc  nop     dword ptr [rax+rax+00h]
0x1800057c1  mov     r8d, eax
0x1800057c4  lea     rdx, aSetcurrentserv; "SetCurrentServiceStatus fails with erro"...
0x1800057cb  lea     rcx, [rsp+880h+var_830]
0x1800057d0  call    FormatRRASErrorString
0x1800057d5  test    cs:byte_18002E903, 8
0x1800057dc  jz      short loc_1800057F2
0x1800057de  lea     r8, [rsp+880h+var_830]
0x1800057e3  mov     rcx, r14
0x1800057e6  lea     rdx, RasSSTPSvcTraceError
0x1800057ed  call    McTemplateU0z_EventWriteTransfer
0x1800057f2  mov     rcx, cs:SstpSvcGlobals
0x1800057f9  cmp     dword ptr [rcx+2F8h], 0
0x180005800  jz      short loc_18000583F
0x180005802  xor     edx, edx; MgrTypeUuid
0x180005804  lea     rcx, qword_18001F400; IfSpec
0x18000580b  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18000580f  call    cs:__imp_RpcServerUnregisterIf
0x180005816  nop     dword ptr [rax+rax+00h]
0x18000581b  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180005820  mov     rbx, rax
0x180005823  test    rax, rax
0x180005826  jz      short loc_18000583F
0x180005828  mov     rcx, rax; this
0x18000582b  call    ??1TenantGatewayMap@@QEAA@XZ; TenantGatewayMap::~TenantGatewayMap(void)
0x180005830  mov     rcx, rbx
0x180005833  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000583a  nop     dword ptr [rax+rax+00h]
0x18000583f  mov     ecx, 1
0x180005844  call    GetSstpConfigFlag
0x180005849  test    eax, eax
0x18000584b  jz      short loc_180005854
0x18000584d  xor     ecx, ecx
0x18000584f  call    ShutdownSstpServer
0x180005854  call    DeinitializeTransport
0x180005859  mov     r8, cs:SstpSvcGlobals
0x180005860  mov     rcx, [r8+20h]; WaitHandle
0x180005864  test    rcx, rcx
0x180005867  jz      short loc_1800058A9
0x180005869  xor     edx, edx; CompletionEvent
0x18000586b  call    cs:__imp_UnregisterWaitEx
0x180005872  nop     dword ptr [rax+rax+00h]
0x180005877  test    eax, eax
0x180005879  jnz     short loc_18000589A
0x18000587b  test    cs:byte_18002E903, 8
0x180005882  jz      short loc_18000589A
0x180005884  lea     r8, aFailedToUnregi; "Failed to Unregister the wait handle"
0x18000588b  mov     rcx, r14
0x18000588e  lea     rdx, RasSSTPSvcTraceError
0x180005895  call    McTemplateU0z_EventWriteTransfer
0x18000589a  mov     r8, cs:SstpSvcGlobals
0x1800058a1  mov     qword ptr [r8+20h], 0
0x1800058a9  mov     rcx, [r8+18h]; hObject
0x1800058ad  test    rcx, rcx
0x1800058b0  jz      short loc_1800058CD
0x1800058b2  call    cs:__imp_CloseHandle
0x1800058b9  nop     dword ptr [rax+rax+00h]
0x1800058be  mov     r8, cs:SstpSvcGlobals
0x1800058c5  mov     qword ptr [r8+18h], 0
0x1800058cd  lea     r9, [r8+130h]
0x1800058d4  mov     edx, 2
0x1800058d9  add     r8, 128h
0x1800058e0  xor     ecx, ecx
0x1800058e2  call    ConfigureMiniports
0x1800058e7  test    cs:byte_18002E903, 10h
0x1800058ee  jz      short loc_180005906
0x1800058f0  lea     r8, aCleanupComplet; "Cleanup completed. Stopping trace and s"...
0x1800058f7  mov     rcx, r14
0x1800058fa  lea     rdx, RasSSTPSvcTraceInfo
0x180005901  call    McTemplateU0z_EventWriteTransfer
0x180005906  mov     rax, cs:SstpSvcGlobals
0x18000590d  mov     dword ptr [rax], 1
0x180005913  call    cs:__imp_GetProcessHeap
0x18000591a  nop     dword ptr [rax+rax+00h]
0x18000591f  mov     r8, cs:SstpSvcGlobals; lpMem
0x180005926  xor     edx, edx; dwFlags
0x180005928  mov     rcx, rax; hHeap
0x18000592b  call    cs:__imp_HeapFree
0x180005932  nop     dword ptr [rax+rax+00h]
0x180005937  test    cs:byte_18002E903, 10h
0x18000593e  mov     cs:SstpSvcGlobals, 0
0x180005949  jz      short loc_180005987
0x18000594b  xor     eax, eax
0x18000594d  lea     r8, aStartservicecl; "StartServiceCleanup"
0x180005954  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000595b  mov     word ptr [rsp+880h+var_830], ax
0x180005960  lea     rcx, [rsp+880h+var_830]
0x180005965  call    FormatRRASErrorString
0x18000596a  test    cs:byte_18002E903, 10h
0x180005971  jz      short loc_180005987
0x180005973  lea     r8, [rsp+880h+var_830]
0x180005978  mov     rcx, r14
0x18000597b  lea     rdx, RasSSTPSvcTraceInfo
0x180005982  call    McTemplateU0z_EventWriteTransfer
0x180005987  mov     cs:SstpSvchostGlobal, 0
0x180005992  call    RasSstpSvcUnRegisterEtw
0x180005997  test    rdi, rdi
0x18000599a  jz      short loc_1800059C9
0x18000599c  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x1800059a1  mov     [rsp+880h+ServiceStatus.dwServiceType], 20h ; ' '
0x1800059a9  mov     rcx, rdi; hServiceStatus
0x1800059ac  mov     qword ptr [rsp+880h+ServiceStatus.dwCurrentState], 1
0x1800059b5  mov     [rsp+880h+ServiceStatus.dwCheckPoint], 0
0x1800059bd  call    cs:__imp_SetServiceStatus
0x1800059c4  nop     dword ptr [rax+rax+00h]
0x1800059c9  mov     rcx, [rbp+780h+var_30]
0x1800059d0  xor     rcx, rsp; StackCookie
0x1800059d3  call    __security_check_cookie
0x1800059d8  add     rsp, 868h
0x1800059df  pop     r14
0x1800059e1  pop     rdi
0x1800059e2  pop     rbx
0x1800059e3  pop     rbp
0x1800059e4  retn
```
