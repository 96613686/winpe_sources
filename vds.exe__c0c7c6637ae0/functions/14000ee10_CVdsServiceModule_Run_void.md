# CVdsServiceModule::Run(void)

- ea: `0x14000ee10`
- end: `0x14000f160`
- name: `?Run@CVdsServiceModule@@QEAAXXZ`
- size: `848`
- prototype: `void __fastcall(CVdsServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f170`

## callees

- `0x14000ee10`
- `0x140013298`
- `0x140017188`
- `0x14001b050`
- `0x140034b54`
- `0x140035c10`
- `0x14003cf30`

## import_xrefs

- `USER32!DispatchMessageW` at `0x14000f0e0`
- `USER32!DispatchMessageW` at `0x14000f0e0`
- `USER32!GetMessageW` at `0x14000f0cf`
- `USER32!GetMessageW` at `0x14000f0cf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000eef8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000eef8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000ee4e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000ee4e`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000ef32`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000ef32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ef92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f01b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ee3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ee3e`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x14000f009`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x14000f009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f13b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f13b`
- `vdsutil!StopReferenceHistory` at `0x14000f12e`
- `vdsutil!StopReferenceHistory` at `0x14000f12e`
- `vdsutil!WaitForRundownProtectionRelease` at `0x14000f123`
- `vdsutil!WaitForRundownProtectionRelease` at `0x14000f123`
- `vdsutil!StartReferenceHistory` at `0x14000f03a`
- `vdsutil!StartReferenceHistory` at `0x14000f03a`
- `vdsutil!InitializeRundownProtection` at `0x14000f034`
- `vdsutil!InitializeRundownProtection` at `0x14000f034`
- `vdsutil!VdsDisableCOMFatalExceptionHandling` at `0x14000efe7`
- `vdsutil!VdsDisableCOMFatalExceptionHandling` at `0x14000efe7`
- `vdsutil!InitializeSecurityDescriptorHelper` at `0x14000eed9`
- `vdsutil!InitializeSecurityDescriptorHelper` at `0x14000eed9`
- `vdsutil!VdsHeapFree` at `0x14000ef4c`
- `vdsutil!VdsHeapFree` at `0x14000ef68`
- `vdsutil!VdsHeapFree` at `0x14000ef84`
- `vdsutil!VdsHeapFree` at `0x14000efa0`
- `vdsutil!VdsHeapFree` at `0x14000ef4c`
- `vdsutil!VdsHeapFree` at `0x14000ef68`
- `vdsutil!VdsHeapFree` at `0x14000ef84`
- `vdsutil!VdsHeapFree` at `0x14000efa0`
- `vdsutil!VdsTraceEx` at `0x14000ee6b`
- `vdsutil!VdsTraceEx` at `0x14000eef2`
- `vdsutil!VdsTraceEx` at `0x14000efbd`
- `vdsutil!VdsTraceEx` at `0x14000f053`
- `vdsutil!VdsTraceEx` at `0x14000ee6b`
- `vdsutil!VdsTraceEx` at `0x14000eef2`
- `vdsutil!VdsTraceEx` at `0x14000efbd`
- `vdsutil!VdsTraceEx` at `0x14000f053`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000ee37`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f0fd`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000ee37`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f0fd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f116`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f14c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f116`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f14c`
- `vdsutil!?Uninitialize@CVdsPnPNotificationBase@@QEAAXXZ` at `0x14000f10b`
- `vdsutil!?Uninitialize@CVdsPnPNotificationBase@@QEAAXXZ` at `0x14000f10b`

## string_xrefs

- `0x14000ee23`: `CVdsServiceModule::Run()`
- `0x14000ee5f`: `CVdsService::Initialize: CoInitializeEx failed: %X`
- `0x14000eee3`: `CVdsServiceModule::Run: failed to initialize security descriptor: %X`
- `0x14000efb1`: `CVdsServiceModule::Run: CoInitializeSecurity failed: %X`
- `0x14000eff1`: `CVdsServiceModule::Run: VdsDisableCOMFatalExceptionHandling failed: 0x%08X`
- `0x14000f021`: `CVdsServiceModule::Run: failed to initialize semaphore: %X`
- `0x14000f044`: `CVdsServiceModule::Run: StartReferenceHistory failed: %X`
- `0x14000f082`: `CVdsServiceModule::Run: RegisterClassObjects failed: %X`
- `0x14000f0ef`: `CVdsService::Uninitialize()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVdsServiceModule::Run(CVdsServiceModule *this)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  HRESULT v4; // edi
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  int v13; // eax
  DWORD LastError; // eax
  unsigned int started; // eax
  ATL::CComModule *v16; // rcx
  unsigned int v17; // r8d
  int v18; // eax
  ATL::CComModule *v19; // rcx
  int MessageW; // ebx
  _BYTE v21[16]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v22; // [rsp+60h] [rbp-59h] BYREF
  __int64 v23; // [rsp+68h] [rbp-51h] BYREF
  __int64 v24; // [rsp+70h] [rbp-49h] BYREF
  __int64 v25; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v26[16]; // [rsp+80h] [rbp-39h] BYREF
  _OWORD pSecDesc[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v28; // [rsp+B0h] [rbp-9h]
  struct tagMSG Msg; // [rsp+B8h] [rbp-1h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v21, 0x5Eu, "CVdsServiceModule::Run()");
  idThread = GetCurrentThreadId();
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsService::Initialize: CoInitializeEx failed: %X", v1);
    VdsLogError(0xC2000001, 0, 0, v2, 0x2010003u, 0);
    goto LABEL_22;
  }
  memset(pSecDesc, 0, sizeof(pSecDesc));
  v28 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v3 = InitializeSecurityDescriptorHelper(1, pSecDesc, &v22, &v23, &v24, &v25);
  if ( v3 )
  {
    VdsTraceEx(94, 0, "CVdsServiceModule::Run: failed to initialize security descriptor: %X", v3);
LABEL_5:
    CoUninitialize();
    goto LABEL_22;
  }
  v4 = CoInitializeSecurity(pSecDesc, -1, 0, 0, 6u, 2u, 0, 0x2000u, 0);
  v5 = v22;
  ProcessHeap = GetProcessHeap();
  VdsHeapFree(ProcessHeap, 0, v5);
  v22 = 0;
  v7 = v23;
  v8 = GetProcessHeap();
  VdsHeapFree(v8, 0, v7);
  v23 = 0;
  v9 = v24;
  v10 = GetProcessHeap();
  VdsHeapFree(v10, 0, v9);
  v24 = 0;
  v11 = v25;
  v12 = GetProcessHeap();
  VdsHeapFree(v12, 0, v11);
  v25 = 0;
  if ( v4 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsServiceModule::Run: CoInitializeSecurity failed: %X", v4);
    VdsLogError(0xC2000001, 0, 0, v4, 0x2010004u, 0);
    goto LABEL_5;
  }
  v13 = VdsDisableCOMFatalExceptionHandling();
  if ( v13 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsServiceModule::Run: VdsDisableCOMFatalExceptionHandling failed: 0x%08X", (unsigned int)v13);
    goto LABEL_5;
  }
  g_hExclusiveOperationSem = CreateSemaphoreW(0, 1, 1, 0);
  if ( !g_hExclusiveOperationSem )
  {
    LastError = GetLastError();
    VdsTraceEx(94, 0, "CVdsServiceModule::Run: failed to initialize semaphore: %X", LastError);
    goto LABEL_5;
  }
  InitializeRundownProtection(&g_RundownRef);
  started = StartReferenceHistory();
  if ( started )
  {
    VdsTraceEx(94, 0, "CVdsServiceModule::Run: StartReferenceHistory failed: %X", started);
LABEL_14:
    CloseHandle(g_hExclusiveOperationSem);
    g_hExclusiveOperationSem = 0;
    goto LABEL_5;
  }
  v18 = ATL::CComModule::RegisterClassObjects(v16, 0x14u, v17);
  if ( v18 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsServiceModule::Run: RegisterClassObjects failed: %X", (unsigned int)v18);
    goto LABEL_14;
  }
  VdsLogInfo(0x42000003u, 0, 0, 0x2010005u, 0);
  CVdsServiceModule::SetServiceStatus((CVdsServiceModule *)&_ServiceModule, 4u);
  memset(&Msg, 0, sizeof(Msg));
  do
  {
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    if ( MessageW != -1 )
      DispatchMessageW(&Msg);
  }
  while ( MessageW );
  ATL::CComModule::RevokeClassObjects(v19);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v26, 0x5Eu, "CVdsService::Uninitialize()");
  CVdsPnPNotificationBase::Uninitialize((CVdsPnPNotificationBase *)&CVdsService::m_PnPNotificationManager);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v26);
  WaitForRundownProtectionRelease(&g_RundownRef);
  CVdsService::Uninitialize();
  StopReferenceHistory();
  CloseHandle(g_hExclusiveOperationSem);
  g_hExclusiveOperationSem = 0;
LABEL_22:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
}

```

## disassembly

```asm
0x14000ee10  push    rbp
0x14000ee12  push    rbx
0x14000ee13  push    rsi
0x14000ee14  push    rdi
0x14000ee15  push    r14
0x14000ee17  lea     rbp, [rsp-37h]
0x14000ee1c  sub     rsp, 0F0h
0x14000ee23  lea     r8, aCvdsservicemod_21; "CVdsServiceModule::Run()"
0x14000ee2a  mov     r14d, 5Eh ; '^'
0x14000ee30  mov     edx, r14d
0x14000ee33  lea     rcx, [rbp+57h+var_C0]
0x14000ee37  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000ee3d  nop
0x14000ee3e  call    cs:__imp_GetCurrentThreadId
0x14000ee44  mov     cs:idThread, eax
0x14000ee4a  xor     edx, edx; dwCoInit
0x14000ee4c  xor     ecx, ecx; pvReserved
0x14000ee4e  call    cs:__imp_CoInitializeEx
0x14000ee54  mov     ebx, eax
0x14000ee56  xor     esi, esi
0x14000ee58  test    eax, eax
0x14000ee5a  jns     short loc_14000EE95
0x14000ee5c  mov     r9d, eax
0x14000ee5f  lea     r8, aCvdsserviceIni_5; "CVdsService::Initialize: CoInitializeEx"...
0x14000ee66  xor     edx, edx
0x14000ee68  mov     ecx, r14d
0x14000ee6b  call    cs:__imp_VdsTraceEx
0x14000ee71  mov     qword ptr [rsp+110h+dwImpLevel], rsi; unsigned __int16 *
0x14000ee76  mov     [rsp+110h+dwAuthnLevel], 2010003h; unsigned int
0x14000ee7e  mov     r9d, ebx; unsigned int
0x14000ee81  xor     r8d, r8d; void *
0x14000ee84  xor     edx, edx; unsigned int
0x14000ee86  mov     ecx, 0C2000001h; unsigned int
0x14000ee8b  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000ee90  jmp     loc_14000F148
0x14000ee95  xorps   xmm0, xmm0
0x14000ee98  xor     eax, eax
0x14000ee9a  movups  [rbp+57h+pSecDesc], xmm0
0x14000ee9e  movups  [rbp+57h+var_70], xmm0
0x14000eea2  mov     [rbp+57h+var_60], rax
0x14000eea6  mov     [rbp+57h+var_B0], rsi
0x14000eeaa  mov     [rbp+57h+var_A8], rsi
0x14000eeae  mov     [rbp+57h+var_A0], rsi
0x14000eeb2  mov     [rbp+57h+var_98], rsi
0x14000eeb6  lea     rax, [rbp+57h+var_98]
0x14000eeba  mov     qword ptr [rsp+110h+dwImpLevel], rax
0x14000eebf  lea     rax, [rbp+57h+var_A0]
0x14000eec3  mov     qword ptr [rsp+110h+dwAuthnLevel], rax
0x14000eec8  lea     r9, [rbp+57h+var_A8]
0x14000eecc  lea     r8, [rbp+57h+var_B0]
0x14000eed0  lea     rdx, [rbp+57h+pSecDesc]
0x14000eed4  mov     ecx, 1
0x14000eed9  call    cs:__imp_InitializeSecurityDescriptorHelper
0x14000eedf  test    eax, eax
0x14000eee1  jz      short loc_14000EF03
0x14000eee3  lea     r8, aCvdsservicemod_9; "CVdsServiceModule::Run: failed to initi"...
0x14000eeea  mov     r9d, eax
0x14000eeed  xor     edx, edx
0x14000eeef  mov     ecx, r14d
0x14000eef2  call    cs:__imp_VdsTraceEx
0x14000eef8  call    cs:__imp_CoUninitialize
0x14000eefe  jmp     loc_14000F148
0x14000ef03  mov     [rsp+110h+pReserved3], rsi; pReserved3
0x14000ef08  mov     [rsp+110h+dwCapabilities], 2000h; dwCapabilities
0x14000ef10  mov     [rsp+110h+pAuthList], rsi; pAuthList
0x14000ef15  mov     [rsp+110h+dwImpLevel], 2; dwImpLevel
0x14000ef1d  mov     [rsp+110h+dwAuthnLevel], 6; dwAuthnLevel
0x14000ef25  xor     r9d, r9d; pReserved1
0x14000ef28  xor     r8d, r8d; asAuthSvc
0x14000ef2b  or      edx, 0FFFFFFFFh; cAuthSvc
0x14000ef2e  lea     rcx, [rbp+57h+pSecDesc]; pSecDesc
0x14000ef32  call    cs:__imp_CoInitializeSecurity
0x14000ef38  mov     edi, eax
0x14000ef3a  mov     rbx, [rbp+57h+var_B0]
0x14000ef3e  call    cs:__imp_GetProcessHeap
0x14000ef44  mov     r8, rbx
0x14000ef47  xor     edx, edx
0x14000ef49  mov     rcx, rax
0x14000ef4c  call    cs:__imp_VdsHeapFree
0x14000ef52  mov     [rbp+57h+var_B0], rsi
0x14000ef56  mov     rbx, [rbp+57h+var_A8]
0x14000ef5a  call    cs:__imp_GetProcessHeap
0x14000ef60  mov     r8, rbx
0x14000ef63  xor     edx, edx
0x14000ef65  mov     rcx, rax
0x14000ef68  call    cs:__imp_VdsHeapFree
0x14000ef6e  mov     [rbp+57h+var_A8], rsi
0x14000ef72  mov     rbx, [rbp+57h+var_A0]
0x14000ef76  call    cs:__imp_GetProcessHeap
0x14000ef7c  mov     r8, rbx
0x14000ef7f  xor     edx, edx
0x14000ef81  mov     rcx, rax
0x14000ef84  call    cs:__imp_VdsHeapFree
0x14000ef8a  mov     [rbp+57h+var_A0], rsi
0x14000ef8e  mov     rbx, [rbp+57h+var_98]
0x14000ef92  call    cs:__imp_GetProcessHeap
0x14000ef98  mov     r8, rbx
0x14000ef9b  xor     edx, edx
0x14000ef9d  mov     rcx, rax
0x14000efa0  call    cs:__imp_VdsHeapFree
0x14000efa6  mov     [rbp+57h+var_98], rsi
0x14000efaa  test    edi, edi
0x14000efac  jns     short loc_14000EFE7
0x14000efae  mov     r9d, edi
0x14000efb1  lea     r8, aCvdsservicemod_18; "CVdsServiceModule::Run: CoInitializeSec"...
0x14000efb8  xor     edx, edx
0x14000efba  mov     ecx, r14d
0x14000efbd  call    cs:__imp_VdsTraceEx
0x14000efc3  mov     qword ptr [rsp+110h+dwImpLevel], rsi; unsigned __int16 *
0x14000efc8  mov     [rsp+110h+dwAuthnLevel], 2010004h; unsigned int
0x14000efd0  mov     r9d, edi; unsigned int
0x14000efd3  xor     r8d, r8d; void *
0x14000efd6  xor     edx, edx; unsigned int
0x14000efd8  mov     ecx, 0C2000001h; unsigned int
0x14000efdd  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000efe2  jmp     loc_14000EEF8
0x14000efe7  call    cs:__imp_VdsDisableCOMFatalExceptionHandling
0x14000efed  test    eax, eax
0x14000efef  jns     short loc_14000EFFD
0x14000eff1  lea     r8, aCvdsservicemod_16; "CVdsServiceModule::Run: VdsDisableCOMFa"...
0x14000eff8  jmp     loc_14000EEEA
0x14000effd  xor     r9d, r9d; lpName
0x14000f000  lea     edx, [r9+1]; lInitialCount
0x14000f004  xor     ecx, ecx; lpSemaphoreAttributes
0x14000f006  mov     r8d, edx; lMaximumCount
0x14000f009  call    cs:__imp_CreateSemaphoreW
0x14000f00f  mov     cs:?g_hExclusiveOperationSem@@3PEAXEA, rax; void * g_hExclusiveOperationSem
0x14000f016  test    rax, rax
0x14000f019  jnz     short loc_14000F02D
0x14000f01b  call    cs:__imp_GetLastError
0x14000f021  lea     r8, aCvdsservicemod_19; "CVdsServiceModule::Run: failed to initi"...
0x14000f028  jmp     loc_14000EEEA
0x14000f02d  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14000f034  call    cs:__imp_InitializeRundownProtection
0x14000f03a  call    cs:__imp_StartReferenceHistory
0x14000f040  test    eax, eax
0x14000f042  jz      short loc_14000F072
0x14000f044  lea     r8, aCvdsservicemod_0; "CVdsServiceModule::Run: StartReferenceH"...
0x14000f04b  xor     edx, edx
0x14000f04d  mov     r9d, eax
0x14000f050  mov     ecx, r14d
0x14000f053  call    cs:__imp_VdsTraceEx
0x14000f059  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hObject
0x14000f060  call    cs:__imp_CloseHandle
0x14000f066  mov     cs:?g_hExclusiveOperationSem@@3PEAXEA, rsi; void * g_hExclusiveOperationSem
0x14000f06d  jmp     loc_14000EEF8
0x14000f072  mov     edx, 14h; unsigned int
0x14000f077  call    ?RegisterClassObjects@CComModule@ATL@@QEAAJKK@Z; ATL::CComModule::RegisterClassObjects(ulong,ulong)
0x14000f07c  xor     edx, edx; unsigned int
0x14000f07e  test    eax, eax
0x14000f080  jns     short loc_14000F08B
0x14000f082  lea     r8, aCvdsservicemod_2; "CVdsServiceModule::Run: RegisterClassOb"...
0x14000f089  jmp     short loc_14000F04D
0x14000f08b  mov     qword ptr [rsp+110h+dwAuthnLevel], rsi; unsigned __int16 *
0x14000f090  mov     r9d, 2010005h; unsigned int
0x14000f096  xor     r8d, r8d; void *
0x14000f099  mov     ecx, 42000003h; unsigned int
0x14000f09e  call    ?VdsLogInfo@@YAXKKPEAXKPEAGZZ; VdsLogInfo(ulong,ulong,void *,ulong,ushort *,...)
0x14000f0a3  mov     edx, 4; unsigned int
0x14000f0a8  lea     rcx, ?_ServiceModule@@3VCVdsServiceModule@@A; this
0x14000f0af  call    ?SetServiceStatus@CVdsServiceModule@@QEAAXK@Z; CVdsServiceModule::SetServiceStatus(ulong)
0x14000f0b4  xorps   xmm0, xmm0
0x14000f0b7  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000f0bb  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000f0bf  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14000f0c3  xor     r9d, r9d; wMsgFilterMax
0x14000f0c6  xor     r8d, r8d; wMsgFilterMin
0x14000f0c9  xor     edx, edx; hWnd
0x14000f0cb  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000f0cf  call    cs:__imp_GetMessageW
0x14000f0d5  mov     ebx, eax
0x14000f0d7  cmp     eax, 0FFFFFFFFh
0x14000f0da  jz      short loc_14000F0E6
0x14000f0dc  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000f0e0  call    cs:__imp_DispatchMessageW
0x14000f0e6  test    ebx, ebx
0x14000f0e8  jnz     short loc_14000F0C3
0x14000f0ea  call    ?RevokeClassObjects@CComModule@ATL@@QEAAJXZ; ATL::CComModule::RevokeClassObjects(void)
0x14000f0ef  lea     r8, aCvdsserviceUni_25; "CVdsService::Uninitialize()"
0x14000f0f6  mov     edx, r14d
0x14000f0f9  lea     rcx, [rbp+57h+var_90]
0x14000f0fd  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000f103  nop
0x14000f104  lea     rcx, ?m_PnPNotificationManager@CVdsService@@2VCVdsPnPNotificationManager@@A; CVdsPnPNotificationManager CVdsService::m_PnPNotificationManager
0x14000f10b  call    cs:__imp_?Uninitialize@CVdsPnPNotificationBase@@QEAAXXZ; CVdsPnPNotificationBase::Uninitialize(void)
0x14000f111  nop
0x14000f112  lea     rcx, [rbp+57h+var_90]
0x14000f116  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f11c  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14000f123  call    cs:__imp_WaitForRundownProtectionRelease
0x14000f129  call    ?Uninitialize@CVdsService@@SAXXZ; CVdsService::Uninitialize(void)
0x14000f12e  call    cs:__imp_StopReferenceHistory
0x14000f134  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hObject
0x14000f13b  call    cs:__imp_CloseHandle
0x14000f141  mov     cs:?g_hExclusiveOperationSem@@3PEAXEA, rsi; void * g_hExclusiveOperationSem
0x14000f148  lea     rcx, [rbp+57h+var_C0]
0x14000f14c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f152  add     rsp, 0F0h
0x14000f159  pop     r14
0x14000f15b  pop     rdi
0x14000f15c  pop     rsi
0x14000f15d  pop     rbx
0x14000f15e  pop     rbp
0x14000f15f  retn
```
