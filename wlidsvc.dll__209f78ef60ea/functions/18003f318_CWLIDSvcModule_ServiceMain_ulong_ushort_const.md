# CWLIDSvcModule::ServiceMain(ulong,ushort const * *)

- ea: `0x18003f318`
- end: `0x18003f4b4`
- name: `?ServiceMain@CWLIDSvcModule@@QEAAXKPEAPEBG@Z`
- size: `412`
- prototype: `void __fastcall(CWLIDSvcModule *__hidden this, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180085260`

## callees

- `0x180019690`
- `0x18003f318`
- `0x18003f4bc`
- `0x18003f5e8`
- `0x18003f6b8`
- `0x18003f6e8`
- `0x18003f714`
- `0x180050b10`
- `0x1800553b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f45c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f45c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003f3cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003f3cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003f423`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003f423`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18003f3ad`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18003f3ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f36b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f36b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003f44a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003f44a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003f4ad`

## string_xrefs

- `0x18003f3fc`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidsvc.cpp`

## pseudocode

```c
void __fastcall CWLIDSvcModule::ServiceMain(CWLIDSvcModule *this, __int64 a2, const unsigned __int16 **a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // eax
  CWLIDSvcModule *v6; // rcx

  wil::g_fResultFailFastUnknownExceptions = 0;
  g_lShutdownInProgress = 0;
  dword_1801C2340 = 0;
  dword_1801C2300 = 32;
  qword_1801C2304 = 1;
  qword_1801C230C = 0;
  dword_1801C2314 = 0;
  dword_1801C2318 = 1500;
  qword_1801C2328 = GetTickCount64();
  qword_1801C2330 = qword_1801C2328;
  McGenEventRegister_EventRegister(v4, v3, &Microsoft_Windows_LiveId_Context, &Microsoft_Windows_LiveId_Context);
  EventSetInformation(
    Microsoft_Windows_LiveId_Context,
    2,
    &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
    (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  dword_1801C3ABC = 4;
  if ( !GetModuleFileNameW(0, &Filename, 0x105u) )
    Filename = 0;
  TraceState();
  v5 = TlgRegisterAggregateProviderEx();
  if ( v5 < 0 )
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\svc\\wlidsvc.cpp",
      0x61u,
      L"TlgRegisterAggregateProvider failed with 0x%x, continuing...",
      v5);
  if ( (qword_1801C2338 || (qword_1801C2338 = CreateEventExW(0, 0, 0, 0x1F0003u)) != 0)
    && (qword_1801C22F8 = (__int64)RegisterServiceCtrlHandlerExW(lpServiceName, CWLIDSvcModule::_HandlerEx, &g_WLIDSvc)) != 0 )
  {
    CWLIDSvcModule::SetServiceStatus((CWLIDSvcModule *)&g_WLIDSvc, 2u);
    CWLIDSvcModule::Run(v6);
  }
  else
  {
    GetLastError();
  }
  TlgUnregisterAggregateProvider();
  TraceState();
  McGenEventUnregister_EventUnregister(&Microsoft_Windows_LiveId_Context);
  qword_1801C2304 = 1;
  SetServiceStatus((SERVICE_STATUS_HANDLE)qword_1801C22F8, (LPSERVICE_STATUS)&dword_1801C2300);
}

```

## disassembly

```asm
0x18003f318  sub     rsp, 38h
0x18003f31c  mov     cs:?g_fResultFailFastUnknownExceptions@wil@@3_NA, 0; bool wil::g_fResultFailFastUnknownExceptions
0x18003f323  mov     cs:?g_lShutdownInProgress@@3JA, 0; long g_lShutdownInProgress
0x18003f32d  mov     cs:dword_1801C2340, 0
0x18003f337  mov     cs:dword_1801C2300, 20h ; ' '
0x18003f341  mov     cs:qword_1801C2304, 1
0x18003f34c  mov     cs:qword_1801C230C, 0
0x18003f357  mov     cs:dword_1801C2314, 0
0x18003f361  mov     cs:dword_1801C2318, 5DCh
0x18003f36b  call    cs:__imp_GetTickCount64
0x18003f371  lea     r9, Microsoft_Windows_LiveId_Context
0x18003f378  mov     cs:qword_1801C2328, rax
0x18003f37f  lea     r8, Microsoft_Windows_LiveId_Context
0x18003f386  mov     cs:qword_1801C2330, rax
0x18003f38d  call    McGenEventRegister_EventRegister
0x18003f392  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18003f39a  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18003f3a1  mov     rcx, cs:Microsoft_Windows_LiveId_Context
0x18003f3a8  mov     edx, 2
0x18003f3ad  call    cs:__imp_EventSetInformation
0x18003f3b3  mov     r8d, 105h; nSize
0x18003f3b9  mov     cs:dword_1801C3ABC, 4
0x18003f3c3  lea     rdx, Filename; lpFilename
0x18003f3ca  xor     ecx, ecx; hModule
0x18003f3cc  call    cs:__imp_GetModuleFileNameW
0x18003f3d2  test    eax, eax
0x18003f3d4  jnz     short loc_18003F3DD
0x18003f3d6  mov     cs:Filename, ax
0x18003f3dd  call    TraceState
0x18003f3e2  call    TlgRegisterAggregateProviderEx
0x18003f3e7  test    eax, eax
0x18003f3e9  jns     short loc_18003F40C
0x18003f3eb  mov     r8d, 61h ; 'a'; unsigned int
0x18003f3f1  mov     [rsp+38h+var_18], eax
0x18003f3f5  lea     r9, aTlgregisteragg; "TlgRegisterAggregateProvider failed wit"...
0x18003f3fc  lea     rdx, aOnecoreuapDsEx_98; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003f403  lea     ecx, [r8-5Fh]; unsigned __int8
0x18003f407  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003f40c  cmp     cs:qword_1801C2338, 0
0x18003f414  jnz     short loc_18003F435
0x18003f416  mov     r9d, 1F0003h; dwDesiredAccess
0x18003f41c  xor     r8d, r8d; dwFlags
0x18003f41f  xor     edx, edx; lpName
0x18003f421  xor     ecx, ecx; lpEventAttributes
0x18003f423  call    cs:__imp_CreateEventExW
0x18003f429  mov     cs:qword_1801C2338, rax
0x18003f430  test    rax, rax
0x18003f433  jz      short loc_18003F45C
0x18003f435  mov     rcx, cs:lpServiceName; lpServiceName
0x18003f43c  lea     r8, ?g_WLIDSvc@@3VCWLIDSvcModule@@A; lpContext
0x18003f443  lea     rdx, ?_HandlerEx@CWLIDSvcModule@@CAKKKPEAX0@Z; lpHandlerProc
0x18003f44a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18003f450  mov     cs:qword_1801C22F8, rax
0x18003f457  test    rax, rax
0x18003f45a  jnz     short loc_18003F464
0x18003f45c  call    cs:__imp_GetLastError
0x18003f462  jmp     short loc_18003F47A
0x18003f464  mov     edx, 2; unsigned int
0x18003f469  lea     rcx, ?g_WLIDSvc@@3VCWLIDSvcModule@@A; this
0x18003f470  call    ?SetServiceStatus@CWLIDSvcModule@@AEAAXK@Z; CWLIDSvcModule::SetServiceStatus(ulong)
0x18003f475  call    ?Run@CWLIDSvcModule@@AEAAXXZ; CWLIDSvcModule::Run(void)
0x18003f47a  call    TlgUnregisterAggregateProvider
0x18003f47f  call    TraceState
0x18003f484  lea     rcx, Microsoft_Windows_LiveId_Context
0x18003f48b  call    McGenEventUnregister_EventUnregister
0x18003f490  mov     rcx, cs:qword_1801C22F8
0x18003f497  lea     rdx, dword_1801C2300
0x18003f49e  mov     cs:qword_1801C2304, 1
0x18003f4a9  add     rsp, 38h
0x18003f4ad  jmp     cs:__imp_SetServiceStatus
```
