# CVdsServiceModule::ServiceMain(ulong,ushort * *)

- ea: `0x14000f170`
- end: `0x14000f451`
- name: `?ServiceMain@CVdsServiceModule@@QEAAXKPEAPEAG@Z`
- size: `737`
- prototype: `void __fastcall(CVdsServiceModule *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140036800`

## callees

- `0x14000ee10`
- `0x14000f170`
- `0x140013298`
- `0x14001b050`
- `0x14002cbe8`
- `0x140052e80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000f2d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f2d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000f254`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000f261`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000f254`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000f261`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f41a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f427`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f41a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f30e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000f208`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000f208`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000f1e7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000f1e7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000f40d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000f40d`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x14000f2fc`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x14000f2fc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000f369`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000f3e7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000f369`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000f3e7`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000f226`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000f226`
- `vdsutil!??1CGlobalResource@@QEAA@XZ` at `0x14000f2d0`
- `vdsutil!??1CGlobalResource@@QEAA@XZ` at `0x14000f2d0`
- `vdsutil!UnInitializeGlobalResouce` at `0x14000f38d`
- `vdsutil!UnInitializeGlobalResouce` at `0x14000f38d`
- `vdsutil!?Initialize@CGlobalResource@@QEAAJXZ` at `0x14000f2af`
- `vdsutil!?Initialize@CGlobalResource@@QEAAJXZ` at `0x14000f2af`
- `vdsutil!??0CGlobalResource@@QEAA@XZ` at `0x14000f280`
- `vdsutil!??0CGlobalResource@@QEAA@XZ` at `0x14000f280`
- `vdsutil!VdsTraceEx` at `0x14000f247`
- `vdsutil!VdsTraceEx` at `0x14000f2a1`
- `vdsutil!VdsTraceEx` at `0x14000f2c7`
- `vdsutil!VdsTraceEx` at `0x14000f247`
- `vdsutil!VdsTraceEx` at `0x14000f2a1`
- `vdsutil!VdsTraceEx` at `0x14000f2c7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f19a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f349`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f3be`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f19a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f349`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f3be`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f375`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f3f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f433`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f375`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f3f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f433`

## string_xrefs

- `0x14000f338`: `CVdsServiceModule::SetServiceStatus()`
- `0x14000f3ad`: `CVdsServiceModule::SetServiceStatus()`
- `0x14000f189`: `CVdsServiceModule::ServiceMain()`
- `0x14000f239`: `CVdsServiceModule::ServiceMain, Failed to set redirection trust policy: %u.\n`
- `0x14000f293`: `CVdsService::ServiceMain,1: Error, out of memory`
- `0x14000f2b9`: `CVdsService::ServiceMain,2: Failed to initialize the Global Resources`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVdsServiceModule::ServiceMain(CVdsServiceModule *this, __int64 a2, unsigned __int16 **a3)
{
  DWORD LastError; // eax
  CGlobalResource *v4; // rax
  CGlobalResource *v5; // rbx
  DWORD v6; // eax
  CVdsServiceModule *v7; // rcx
  REGHANDLE v8; // rcx
  int v9; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-20h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v10, 0x5Eu, "CVdsServiceModule::ServiceMain()");
  ProviderId = *(GUID *)&(*off_14009A0B8)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_14009A0D8 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_14009A0B0, &RegHandle) )
    EventSetInformation(RegHandle, 2, (char *)off_14009A0B8, *(unsigned __int16 *)off_14009A0B8);
  v9 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v9, 4) )
  {
    LastError = GetLastError();
    VdsTraceEx(94, 0, "CVdsServiceModule::ServiceMain, Failed to set redirection trust policy: %u.\n", LastError);
  }
  InitializeCriticalSection(&g_GlobalCriticalSection);
  InitializeCriticalSection(&g_OpsInFlight);
  v4 = (CGlobalResource *)operator new(0x58u);
  *(_QWORD *)&ProviderId.Data1 = v4;
  if ( v4 )
    v5 = CGlobalResource::CGlobalResource(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    if ( (int)CGlobalResource::Initialize(v5) >= 0 )
    {
      ServiceStatus.dwCurrentState = 2;
      hServiceStatus = RegisterServiceCtrlHandlerW(&_ServiceModule, (LPHANDLER_FUNCTION)CVdsServiceModule::_Handler);
      if ( hServiceStatus )
      {
        CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)&ProviderId, 0x5Eu, "CVdsServiceModule::SetServiceStatus()");
        *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
        SetServiceStatus(hServiceStatus, &ServiceStatus);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)&ProviderId);
        ServiceStatus.dwWin32ExitCode = 0;
        *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
        CVdsServiceModule::Run(v7);
        UnInitializeGlobalResouce();
        VdsLogInfo(0x42000004u, 0, 0, 0x2010001u, 0);
        CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)&ProviderId, 0x5Eu, "CVdsServiceModule::SetServiceStatus()");
        ServiceStatus.dwCurrentState = 1;
        ServiceStatus.dwControlsAccepted = 1;
        SetServiceStatus(hServiceStatus, &ServiceStatus);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)&ProviderId);
        v8 = RegHandle;
        dword_14009A0B0 = 0;
        RegHandle = 0;
        EventUnregister(v8);
      }
      else
      {
        v6 = GetLastError();
        VdsLogError(0xC2000002, 0, 0, v6, 0x2010000u, 0);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsService::ServiceMain,2: Failed to initialize the Global Resources");
      CGlobalResource::~CGlobalResource(v5);
      operator delete(v5);
    }
    DeleteCriticalSection(&g_GlobalCriticalSection);
    DeleteCriticalSection(&g_OpsInFlight);
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsService::ServiceMain,1: Error, out of memory");
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v10);
}

```

## disassembly

```asm
0x14000f170  mov     [rsp+arg_0], rbx
0x14000f175  push    rdi
0x14000f176  sub     rsp, 60h
0x14000f17a  mov     rax, cs:__security_cookie
0x14000f181  xor     rax, rsp
0x14000f184  mov     [rsp+68h+var_10], rax
0x14000f189  lea     r8, aCvdsservicemod_28; "CVdsServiceModule::ServiceMain()"
0x14000f190  mov     edx, 5Eh ; '^'
0x14000f195  lea     rcx, [rsp+68h+var_30]
0x14000f19a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000f1a0  nop
0x14000f1a1  mov     rax, cs:off_14009A0B8
0x14000f1a8  movups  xmm0, xmmword ptr [rax-10h]
0x14000f1ac  movups  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x14000f1b1  cmp     cs:RegHandle, 0
0x14000f1b9  jz      short loc_14000F1C2
0x14000f1bb  mov     ecx, 5
0x14000f1c0  int     29h; Win8: RtlFailFast(ecx)
0x14000f1c2  xorps   xmm0, xmm0
0x14000f1c5  movdqu  cs:xmmword_14009A0D8, xmm0
0x14000f1cd  lea     r9, RegHandle; RegHandle
0x14000f1d4  lea     r8, dword_14009A0B0; CallbackContext
0x14000f1db  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000f1e2  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x14000f1e7  call    cs:__imp_EventRegister
0x14000f1ed  test    eax, eax
0x14000f1ef  jnz     short loc_14000F20E
0x14000f1f1  mov     r8, cs:off_14009A0B8
0x14000f1f8  movzx   r9d, word ptr [r8]
0x14000f1fc  mov     edx, 2
0x14000f201  mov     rcx, cs:RegHandle
0x14000f208  call    cs:__imp_EventSetInformation
0x14000f20e  mov     [rsp+68h+var_38], 1
0x14000f216  mov     r8d, 4
0x14000f21c  lea     rdx, [rsp+68h+var_38]
0x14000f221  mov     ecx, 10h
0x14000f226  call    cs:__imp_SetProcessMitigationPolicy
0x14000f22c  test    eax, eax
0x14000f22e  jnz     short loc_14000F24D
0x14000f230  call    cs:__imp_GetLastError
0x14000f236  mov     r9d, eax
0x14000f239  lea     r8, aCvdsservicemod_15; "CVdsServiceModule::ServiceMain, Failed "...
0x14000f240  xor     edx, edx
0x14000f242  mov     ecx, 5Eh ; '^'
0x14000f247  call    cs:__imp_VdsTraceEx
0x14000f24d  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f254  call    cs:__imp_InitializeCriticalSection
0x14000f25a  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f261  call    cs:__imp_InitializeCriticalSection
0x14000f267  mov     ecx, 58h ; 'X'; Size
0x14000f26c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f271  mov     qword ptr [rsp+68h+ProviderId.Data1], rax
0x14000f276  xor     edi, edi
0x14000f278  test    rax, rax
0x14000f27b  jz      short loc_14000F28B
0x14000f27d  mov     rcx, rax
0x14000f280  call    cs:__imp_??0CGlobalResource@@QEAA@XZ; CGlobalResource::CGlobalResource(void)
0x14000f286  mov     rbx, rax
0x14000f289  jmp     short loc_14000F28E
0x14000f28b  mov     rbx, rdi
0x14000f28e  test    rbx, rbx
0x14000f291  jnz     short loc_14000F2AC
0x14000f293  lea     r8, aCvdsserviceSer; "CVdsService::ServiceMain,1: Error, out "...
0x14000f29a  xor     edx, edx
0x14000f29c  mov     ecx, 5Eh ; '^'
0x14000f2a1  call    cs:__imp_VdsTraceEx
0x14000f2a7  jmp     loc_14000F42E
0x14000f2ac  mov     rcx, rbx
0x14000f2af  call    cs:__imp_?Initialize@CGlobalResource@@QEAAJXZ; CGlobalResource::Initialize(void)
0x14000f2b5  test    eax, eax
0x14000f2b7  jns     short loc_14000F2E4
0x14000f2b9  lea     r8, aCvdsserviceSer_0; "CVdsService::ServiceMain,2: Failed to i"...
0x14000f2c0  xor     edx, edx
0x14000f2c2  mov     ecx, 5Eh ; '^'
0x14000f2c7  call    cs:__imp_VdsTraceEx
0x14000f2cd  mov     rcx, rbx
0x14000f2d0  call    cs:__imp_??1CGlobalResource@@QEAA@XZ; CGlobalResource::~CGlobalResource(void)
0x14000f2d6  mov     rcx, rbx
0x14000f2d9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f2df  jmp     loc_14000F413
0x14000f2e4  mov     cs:ServiceStatus.dwCurrentState, 2
0x14000f2ee  lea     rdx, ?_Handler@CVdsServiceModule@@CAXK@Z; lpHandlerProc
0x14000f2f5  lea     rcx, ?_ServiceModule@@3VCVdsServiceModule@@A; lpServiceName
0x14000f2fc  call    cs:__imp_RegisterServiceCtrlHandlerW
0x14000f302  mov     cs:hServiceStatus, rax
0x14000f309  test    rax, rax
0x14000f30c  jnz     short loc_14000F338
0x14000f30e  call    cs:__imp_GetLastError
0x14000f314  mov     r9d, eax; unsigned int
0x14000f317  mov     [rsp+68h+var_40], rdi; unsigned __int16 *
0x14000f31c  mov     dword ptr [rsp+68h+var_48], 2010000h; unsigned int
0x14000f324  xor     r8d, r8d; void *
0x14000f327  xor     edx, edx; unsigned int
0x14000f329  mov     ecx, 0C2000002h; unsigned int
0x14000f32e  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000f333  jmp     loc_14000F413
0x14000f338  lea     r8, aCvdsservicemod_13; "CVdsServiceModule::SetServiceStatus()"
0x14000f33f  mov     edx, 5Eh ; '^'
0x14000f344  lea     rcx, [rsp+68h+ProviderId]
0x14000f349  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000f34f  nop
0x14000f350  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x14000f35b  lea     rdx, ServiceStatus; lpServiceStatus
0x14000f362  mov     rcx, cs:hServiceStatus; hServiceStatus
0x14000f369  call    cs:__imp_SetServiceStatus
0x14000f36f  nop
0x14000f370  lea     rcx, [rsp+68h+ProviderId]
0x14000f375  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f37b  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x14000f381  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rdi
0x14000f388  call    ?Run@CVdsServiceModule@@QEAAXXZ; CVdsServiceModule::Run(void)
0x14000f38d  call    cs:__imp_UnInitializeGlobalResouce
0x14000f393  mov     [rsp+68h+var_48], rdi; unsigned __int16 *
0x14000f398  mov     r9d, 2010001h; unsigned int
0x14000f39e  xor     r8d, r8d; void *
0x14000f3a1  xor     edx, edx; unsigned int
0x14000f3a3  mov     ecx, 42000004h; unsigned int
0x14000f3a8  call    ?VdsLogInfo@@YAXKKPEAXKPEAGZZ; VdsLogInfo(ulong,ulong,void *,ulong,ushort *,...)
0x14000f3ad  lea     r8, aCvdsservicemod_13; "CVdsServiceModule::SetServiceStatus()"
0x14000f3b4  mov     edx, 5Eh ; '^'
0x14000f3b9  lea     rcx, [rsp+68h+ProviderId]
0x14000f3be  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000f3c4  nop
0x14000f3c5  mov     cs:ServiceStatus.dwCurrentState, 1
0x14000f3cf  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x14000f3d9  lea     rdx, ServiceStatus; lpServiceStatus
0x14000f3e0  mov     rcx, cs:hServiceStatus; hServiceStatus
0x14000f3e7  call    cs:__imp_SetServiceStatus
0x14000f3ed  nop
0x14000f3ee  lea     rcx, [rsp+68h+ProviderId]
0x14000f3f3  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f3f9  mov     rcx, cs:RegHandle; RegHandle
0x14000f400  mov     cs:dword_14009A0B0, edi
0x14000f406  mov     cs:RegHandle, rdi
0x14000f40d  call    cs:__imp_EventUnregister
0x14000f413  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f41a  call    cs:__imp_DeleteCriticalSection
0x14000f420  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f427  call    cs:__imp_DeleteCriticalSection
0x14000f42d  nop
0x14000f42e  lea     rcx, [rsp+68h+var_30]
0x14000f433  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f439  mov     rcx, [rsp+68h+var_10]
0x14000f43e  xor     rcx, rsp; StackCookie
0x14000f441  call    __security_check_cookie
0x14000f446  mov     rbx, [rsp+68h+arg_0]
0x14000f44b  add     rsp, 60h
0x14000f44f  pop     rdi
0x14000f450  retn
```
