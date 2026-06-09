# SplShutDownRouter

- ea: `0x14006c120`
- end: `0x14006c2ed`
- name: `SplShutDownRouter`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004d2d4`

## callees

- `0x140008550`
- `0x1400087f0`
- `0x140015290`
- `0x14002cd50`
- `0x14006c120`
- `0x14006ca10`
- `0x14006e348`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c1ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c1ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006c268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006c147`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006c181`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006c247`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006c147`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006c181`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006c247`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x14006c238`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x14006c238`
- `WS2_32!__imp_WSACleanup` at `0x14006c2b9`
- `WS2_32!__imp_WSACleanup` at `0x14006c2b9`

## string_xrefs

- `0x14006c283`: `NRouter::ReleaseRouterCache`

## pseudocode

```c
void SplShutDownRouter()
{
  signed __int64 v0; // rax
  signed __int64 v1; // rax
  NCoreLibrary *v2; // rbx
  struct NCoreLibrary::TReferenceCount *v3; // rdx
  unsigned __int64 v4; // rdx
  unsigned int v5; // edx

  PrvSpoolssTelemetry::WriteDbgTraceInfo("SplShutDownRouter", L"Shutting down the router.");
  EnterCriticalSection(&RouterNotifySection);
  if ( qword_1400D2DB8 )
  {
    NCoreLibrary::TReferenceCount::Release(qword_1400D2DB8);
    qword_1400D2DB8 = 0;
  }
  LeaveCriticalSection(&RouterNotifySection);
  EnterCriticalSection(&RouterNotifySection);
  if ( qword_1400D2D98 )
  {
    NCoreLibrary::TReferenceCount::Release(qword_1400D2D98);
    qword_1400D2D98 = 0;
  }
  LeaveCriticalSection(&RouterNotifySection);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("UnRegisterForPerMachineConnectionUserEvents", L"Entered");
  v0 = _InterlockedCompareExchange64(&qword_1400D2DC0, 0, qword_1400D2DC0);
  if ( v0 )
    SplUnregisterForSessionEvents(v0);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("UnRegisterForPolicyConnectionUserEvents", L"Entered.");
  v1 = _InterlockedCompareExchange64(&qword_1400D2CE8, 0, qword_1400D2CE8);
  if ( v1 )
    SplUnregisterForSessionEvents(v1);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("UnRegisterForUserEvents", L"Entered.");
  SetConsoleCtrlHandler(SpoolerConsoleCtrlHandler, 0);
  EnterCriticalSection(&RouterNotifySection);
  v2 = qword_1400D2DC8;
  qword_1400D2DC8 = 0;
  LeaveCriticalSection(&RouterNotifySection);
  NCoreLibrary::EasyRelease(v2, v3);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("NRouter::ReleaseRouterCache", L"Entered.");
  dword_1400D2DA0 = 0;
  operator delete(qword_1400D2DA8, v4);
  qword_1400D2DA8 = 0;
  if ( gbWSASucceeded )
    WSACleanup();
  if ( gpSessionIDGen )
  {
    NSecurityLibrary::CCryptRandom::`scalar deleting destructor'(gpSessionIDGen, v5);
    gpSessionIDGen = 0;
  }
}

```

## disassembly

```asm
0x14006c120  mov     [rsp+arg_0], rbx
0x14006c125  push    rsi
0x14006c126  sub     rsp, 20h
0x14006c12a  lea     rdx, aShuttingDownTh; "Shutting down the router."
0x14006c131  lea     rcx, aSplshutdownrou; "SplShutDownRouter"
0x14006c138  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c13d  lea     rsi, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION RouterNotifySection
0x14006c144  mov     rcx, rsi; lpCriticalSection
0x14006c147  call    cs:__imp_EnterCriticalSection
0x14006c14e  nop     dword ptr [rax+rax+00h]
0x14006c153  mov     rcx, cs:qword_1400D2DB8; this
0x14006c15a  test    rcx, rcx
0x14006c15d  jz      short loc_14006C16F
0x14006c15f  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x14006c164  mov     cs:qword_1400D2DB8, 0
0x14006c16f  mov     rcx, rsi; lpCriticalSection
0x14006c172  call    cs:__imp_LeaveCriticalSection
0x14006c179  nop     dword ptr [rax+rax+00h]
0x14006c17e  mov     rcx, rsi; lpCriticalSection
0x14006c181  call    cs:__imp_EnterCriticalSection
0x14006c188  nop     dword ptr [rax+rax+00h]
0x14006c18d  mov     rcx, cs:qword_1400D2D98; this
0x14006c194  test    rcx, rcx
0x14006c197  jz      short loc_14006C1A9
0x14006c199  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x14006c19e  mov     cs:qword_1400D2D98, 0
0x14006c1a9  mov     rcx, rsi; lpCriticalSection
0x14006c1ac  call    cs:__imp_LeaveCriticalSection
0x14006c1b3  nop     dword ptr [rax+rax+00h]
0x14006c1b8  lea     rdx, aEntered_0; "Entered"
0x14006c1bf  lea     rcx, aUnregisterforp; "UnRegisterForPerMachineConnectionUserEv"...
0x14006c1c6  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c1cb  mov     rax, cs:qword_1400D2DC0
0x14006c1d2  xor     ecx, ecx
0x14006c1d4  lock cmpxchg cs:qword_1400D2DC0, rcx
0x14006c1dd  test    rax, rax
0x14006c1e0  jz      short loc_14006C1EA
0x14006c1e2  mov     rcx, rax
0x14006c1e5  call    SplUnregisterForSessionEvents
0x14006c1ea  lea     rdx, aEntered; "Entered."
0x14006c1f1  lea     rcx, aUnregisterforp_0; "UnRegisterForPolicyConnectionUserEvents"
0x14006c1f8  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c1fd  mov     rax, cs:qword_1400D2CE8
0x14006c204  xor     ecx, ecx
0x14006c206  lock cmpxchg cs:qword_1400D2CE8, rcx
0x14006c20f  test    rax, rax
0x14006c212  jz      short loc_14006C21C
0x14006c214  mov     rcx, rax
0x14006c217  call    SplUnregisterForSessionEvents
0x14006c21c  lea     rdx, aEntered; "Entered."
0x14006c223  lea     rcx, aUnregisterforu; "UnRegisterForUserEvents"
0x14006c22a  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c22f  xor     edx, edx; Add
0x14006c231  lea     rcx, ?SpoolerConsoleCtrlHandler@@YAHK@Z; HandlerRoutine
0x14006c238  call    cs:__imp_SetConsoleCtrlHandler
0x14006c23f  nop     dword ptr [rax+rax+00h]
0x14006c244  mov     rcx, rsi; lpCriticalSection
0x14006c247  call    cs:__imp_EnterCriticalSection
0x14006c24e  nop     dword ptr [rax+rax+00h]
0x14006c253  mov     rbx, cs:qword_1400D2DC8
0x14006c25a  mov     rcx, rsi; lpCriticalSection
0x14006c25d  mov     cs:qword_1400D2DC8, 0
0x14006c268  call    cs:__imp_LeaveCriticalSection
0x14006c26f  nop     dword ptr [rax+rax+00h]
0x14006c274  mov     rcx, rbx; this
0x14006c277  call    ?EasyRelease@NCoreLibrary@@YAXPEAVTReferenceCount@1@@Z; NCoreLibrary::EasyRelease(NCoreLibrary::TReferenceCount *)
0x14006c27c  lea     rdx, aEntered; "Entered."
0x14006c283  lea     rcx, aNrouterRelease; "NRouter::ReleaseRouterCache"
0x14006c28a  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c28f  mov     rcx, cs:qword_1400D2DA8; void *
0x14006c296  mov     cs:dword_1400D2DA0, 0
0x14006c2a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006c2a5  cmp     cs:?gbWSASucceeded@@3HA, 0; int gbWSASucceeded
0x14006c2ac  mov     cs:qword_1400D2DA8, 0
0x14006c2b7  jz      short loc_14006C2C5
0x14006c2b9  call    cs:__imp_WSACleanup
0x14006c2c0  nop     dword ptr [rax+rax+00h]
0x14006c2c5  mov     rcx, cs:?gpSessionIDGen@@3PEAVCCryptRandom@NSecurityLibrary@@EA; this
0x14006c2cc  test    rcx, rcx
0x14006c2cf  jz      short loc_14006C2E1
0x14006c2d1  call    ??_GCCryptRandom@NSecurityLibrary@@QEAAPEAXI@Z; NSecurityLibrary::CCryptRandom::`scalar deleting destructor'(uint)
0x14006c2d6  mov     cs:?gpSessionIDGen@@3PEAVCCryptRandom@NSecurityLibrary@@EA, 0; NSecurityLibrary::CCryptRandom * gpSessionIDGen
0x14006c2e1  mov     rbx, [rsp+28h+arg_0]
0x14006c2e6  add     rsp, 20h
0x14006c2ea  pop     rsi
0x14006c2eb  retn
```
