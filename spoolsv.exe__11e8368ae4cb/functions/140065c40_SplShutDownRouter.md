# SplShutDownRouter

- ea: `0x140065c40`
- end: `0x140065ddc`
- name: `SplShutDownRouter`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140048cac`

## callees

- `0x1400079f0`
- `0x140007c00`
- `0x140013fe8`
- `0x14002a870`
- `0x140065c40`
- `0x140066460`
- `0x140067bc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065c8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065c8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065d64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065c67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065c95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065d49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065c67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065c95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065d49`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x140065d40`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x140065d40`
- `WS2_32!__imp_WSACleanup` at `0x140065daf`
- `WS2_32!__imp_WSACleanup` at `0x140065daf`

## string_xrefs

- `0x140065d79`: `NRouter::ReleaseRouterCache`

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
  if ( qword_1400CBC38 )
  {
    NCoreLibrary::TReferenceCount::Release(qword_1400CBC38);
    qword_1400CBC38 = 0;
  }
  LeaveCriticalSection(&RouterNotifySection);
  EnterCriticalSection(&RouterNotifySection);
  if ( qword_1400CBC20 )
  {
    NCoreLibrary::TReferenceCount::Release(qword_1400CBC20);
    qword_1400CBC20 = 0;
  }
  LeaveCriticalSection(&RouterNotifySection);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("UnRegisterForPerMachineConnectionUserEvents", L"Entered");
  v0 = _InterlockedCompareExchange64(&qword_1400CBC40, 0, qword_1400CBC40);
  if ( v0 )
    SplUnregisterForSessionEvents(v0);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("UnRegisterForPolicyConnectionUserEvents", L"Entered.");
  v1 = _InterlockedCompareExchange64(&qword_1400CBB70, 0, qword_1400CBB70);
  if ( v1 )
    SplUnregisterForSessionEvents(v1);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("UnRegisterForUserEvents", L"Entered.");
  SetConsoleCtrlHandler(SpoolerConsoleCtrlHandler, 0);
  EnterCriticalSection(&RouterNotifySection);
  v2 = qword_1400CBC48;
  qword_1400CBC48 = 0;
  LeaveCriticalSection(&RouterNotifySection);
  NCoreLibrary::EasyRelease(v2, v3);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("NRouter::ReleaseRouterCache", L"Entered.");
  dword_1400CBC30 = 0;
  operator delete(qword_1400CBC28, v4);
  qword_1400CBC28 = 0;
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
0x140065c40  mov     [rsp+arg_0], rbx
0x140065c45  push    rsi
0x140065c46  sub     rsp, 20h
0x140065c4a  lea     rdx, aShuttingDownTh; "Shutting down the router."
0x140065c51  lea     rcx, aSplshutdownrou; "SplShutDownRouter"
0x140065c58  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065c5d  lea     rsi, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION RouterNotifySection
0x140065c64  mov     rcx, rsi; lpCriticalSection
0x140065c67  call    cs:__imp_EnterCriticalSection
0x140065c6d  mov     rcx, cs:qword_1400CBC38; this
0x140065c74  test    rcx, rcx
0x140065c77  jz      short loc_140065C89
0x140065c79  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140065c7e  mov     cs:qword_1400CBC38, 0
0x140065c89  mov     rcx, rsi; lpCriticalSection
0x140065c8c  call    cs:__imp_LeaveCriticalSection
0x140065c92  mov     rcx, rsi; lpCriticalSection
0x140065c95  call    cs:__imp_EnterCriticalSection
0x140065c9b  mov     rcx, cs:qword_1400CBC20; this
0x140065ca2  test    rcx, rcx
0x140065ca5  jz      short loc_140065CB7
0x140065ca7  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140065cac  mov     cs:qword_1400CBC20, 0
0x140065cb7  mov     rcx, rsi; lpCriticalSection
0x140065cba  call    cs:__imp_LeaveCriticalSection
0x140065cc0  lea     rdx, aEntered_0; "Entered"
0x140065cc7  lea     rcx, aUnregisterforp; "UnRegisterForPerMachineConnectionUserEv"...
0x140065cce  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065cd3  mov     rax, cs:qword_1400CBC40
0x140065cda  xor     ecx, ecx
0x140065cdc  lock cmpxchg cs:qword_1400CBC40, rcx
0x140065ce5  test    rax, rax
0x140065ce8  jz      short loc_140065CF2
0x140065cea  mov     rcx, rax
0x140065ced  call    SplUnregisterForSessionEvents
0x140065cf2  lea     rdx, aEntered; "Entered."
0x140065cf9  lea     rcx, aUnregisterforp_0; "UnRegisterForPolicyConnectionUserEvents"
0x140065d00  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065d05  mov     rax, cs:qword_1400CBB70
0x140065d0c  xor     ecx, ecx
0x140065d0e  lock cmpxchg cs:qword_1400CBB70, rcx
0x140065d17  test    rax, rax
0x140065d1a  jz      short loc_140065D24
0x140065d1c  mov     rcx, rax
0x140065d1f  call    SplUnregisterForSessionEvents
0x140065d24  lea     rdx, aEntered; "Entered."
0x140065d2b  lea     rcx, aUnregisterforu; "UnRegisterForUserEvents"
0x140065d32  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065d37  xor     edx, edx; Add
0x140065d39  lea     rcx, ?SpoolerConsoleCtrlHandler@@YAHK@Z; HandlerRoutine
0x140065d40  call    cs:__imp_SetConsoleCtrlHandler
0x140065d46  mov     rcx, rsi; lpCriticalSection
0x140065d49  call    cs:__imp_EnterCriticalSection
0x140065d4f  mov     rbx, cs:qword_1400CBC48
0x140065d56  mov     rcx, rsi; lpCriticalSection
0x140065d59  mov     cs:qword_1400CBC48, 0
0x140065d64  call    cs:__imp_LeaveCriticalSection
0x140065d6a  mov     rcx, rbx; this
0x140065d6d  call    ?EasyRelease@NCoreLibrary@@YAXPEAVTReferenceCount@1@@Z; NCoreLibrary::EasyRelease(NCoreLibrary::TReferenceCount *)
0x140065d72  lea     rdx, aEntered; "Entered."
0x140065d79  lea     rcx, aNrouterRelease; "NRouter::ReleaseRouterCache"
0x140065d80  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065d85  mov     rcx, cs:qword_1400CBC28; void *
0x140065d8c  mov     cs:dword_1400CBC30, 0
0x140065d96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140065d9b  cmp     cs:?gbWSASucceeded@@3HA, 0; int gbWSASucceeded
0x140065da2  mov     cs:qword_1400CBC28, 0
0x140065dad  jz      short loc_140065DB5
0x140065daf  call    cs:__imp_WSACleanup
0x140065db5  mov     rcx, cs:?gpSessionIDGen@@3PEAVCCryptRandom@NSecurityLibrary@@EA; this
0x140065dbc  test    rcx, rcx
0x140065dbf  jz      short loc_140065DD1
0x140065dc1  call    ??_GCCryptRandom@NSecurityLibrary@@QEAAPEAXI@Z; NSecurityLibrary::CCryptRandom::`scalar deleting destructor'(uint)
0x140065dc6  mov     cs:?gpSessionIDGen@@3PEAVCCryptRandom@NSecurityLibrary@@EA, 0; NSecurityLibrary::CCryptRandom * gpSessionIDGen
0x140065dd1  mov     rbx, [rsp+28h+arg_0]
0x140065dd6  add     rsp, 20h
0x140065dda  pop     rsi
0x140065ddb  retn
```
