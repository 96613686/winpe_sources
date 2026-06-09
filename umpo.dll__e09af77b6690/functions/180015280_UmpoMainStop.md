# UmpoMainStop

- ea: `0x180015280`
- end: `0x1800154a5`
- name: `UmpoMainStop`
- size: `549`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ed10`

## callees

- `0x1800010b8`
- `0x18000410c`
- `0x180007ee8`
- `0x18000dc64`
- `0x18000f3dc`
- `0x18000f484`
- `0x180010946`
- `0x1800115f0`
- `0x180013630`
- `0x18001523c`
- `0x180015280`
- `0x18001728c`
- `0x180019010`

## import_xrefs

- `ntdll!RtlDestroyHeap` at `0x18001547d`
- `ntdll!RtlDestroyHeap` at `0x18001547d`
- `ntdll!EtwEventUnregister` at `0x1800153d0`
- `ntdll!EtwEventUnregister` at `0x1800153d0`
- `ntdll!DbgPrint` at `0x180015385`
- `ntdll!DbgPrint` at `0x180015385`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001544d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001544d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001542d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001542d`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800152d8`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800152d8`
- `RPCRT4!RpcBindingFree` at `0x1800152b7`
- `RPCRT4!RpcBindingFree` at `0x1800152b7`
- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataClose` at `0x180015402`
- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataClose` at `0x180015402`

## pseudocode

```c
__int64 __fastcall UmpoMainStop(unsigned int a1)
{
  int v2; // eax
  PVOID v3; // rax
  __int64 v4; // rdx

  if ( UmpoHvPowerRequestClientInitialized )
  {
    if ( UmpoHvRpcPowerRequestClientHandle )
    {
      RpcBindingFree(&UmpoHvRpcPowerRequestClientHandle);
      UmpoHvRpcPowerRequestClientHandle = 0;
    }
    UmpoHvPowerRequestClientInitialized = 0;
  }
  else if ( UmpoHvRpcPowerRequestClientHandle )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  RpcServerUnregisterIfEx(qword_18001B230, 0, 1);
  UmpoAlpcClose();
  if ( qword_180024690 )
    qword_180024690();
  if ( qword_1800246B8 )
    qword_1800246B8();
  if ( qword_180024678 )
    qword_180024678();
  if ( qword_1800246F0 )
    qword_1800246F0();
  if ( !UmpoIsServerSku() )
  {
    if ( qword_180024750 )
      qword_180024750();
    if ( qword_180024708 )
    {
      v2 = qword_180024708();
      if ( v2 )
      {
        if ( (UmpoDebug & 1) != 0 )
          DbgPrint("%s: [%s] Error %08x, line %d\n", "UmpoMainStop", "EXT(StopSleepStudyTracing)", v2, 698);
      }
    }
    if ( (unsigned int)Feature_WISEBatteryDischargeTimeEstimate__private_IsEnabledDeviceUsageNoInline()
      && qword_180024760 )
    {
      qword_180024760();
    }
    if ( qword_180024740 )
      qword_180024740();
  }
  UmpoNotifyClose();
  if ( UmpoProviderHandle )
  {
    TraceLoggingUnregister_EventUnregister();
    EtwEventUnregister(UmpoProviderHandle);
    UmpoProviderHandle = 0;
  }
  memset_0(&UmpoExtensions, 0, 0xF8u);
  UmpoSmartPresenceCleanup();
  if ( UmpoSmartSuspendPFIUData )
    PfIuPredictionsDataClose();
  UmpoSmartSuspendState = 0;
  UmpoSmartSuspendDisableReason = 1;
  UmpoInternalPowerPolicyCleanup();
  if ( byte_180024AC8 )
  {
    DeleteCriticalSection(&PowerRequestLock);
    byte_180024AC8 = 0;
  }
  while ( 1 )
  {
    v3 = RtlEnumerateGenericTableAvl(&UmpoPowerRequestTable, 1u);
    if ( !v3 )
      break;
    UmpoPowerRequestDeleteEntry(v3, v4);
  }
  UmpoInVAILContainer = 0;
  if ( UmpoHeapHandle && UmpoHeapHandle != NtCurrentPeb()->ProcessHeap )
  {
    RtlDestroyHeap(UmpoHeapHandle);
    UmpoHeapHandle = 0;
  }
  return UmpoSetStatus(1, a1, 0, 0);
}

```

## disassembly

```asm
0x180015280  mov     [rsp+arg_0], rbx
0x180015285  push    rdi
0x180015286  sub     rsp, 30h
0x18001528a  xor     edi, edi
0x18001528c  mov     ebx, ecx
0x18001528e  cmp     cs:UmpoHvPowerRequestClientInitialized, dil
0x180015295  jnz     short loc_1800152A7
0x180015297  cmp     cs:UmpoHvRpcPowerRequestClientHandle, rdi
0x18001529e  jz      short loc_1800152CB
0x1800152a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800152a5  jmp     short loc_1800152CB
0x1800152a7  cmp     cs:UmpoHvRpcPowerRequestClientHandle, rdi
0x1800152ae  jz      short loc_1800152C4
0x1800152b0  lea     rcx, UmpoHvRpcPowerRequestClientHandle; Binding
0x1800152b7  call    cs:__imp_RpcBindingFree
0x1800152bd  mov     cs:UmpoHvRpcPowerRequestClientHandle, rdi
0x1800152c4  mov     cs:UmpoHvPowerRequestClientInitialized, dil
0x1800152cb  xor     edx, edx; MgrTypeUuid
0x1800152cd  lea     rcx, qword_18001B230; IfSpec
0x1800152d4  lea     r8d, [rdx+1]; RundownContextHandles
0x1800152d8  call    cs:__imp_RpcServerUnregisterIfEx
0x1800152de  call    UmpoAlpcClose
0x1800152e3  mov     rax, cs:qword_180024690
0x1800152ea  test    rax, rax
0x1800152ed  jz      short loc_1800152F4
0x1800152ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152f4  mov     rax, cs:qword_1800246B8
0x1800152fb  test    rax, rax
0x1800152fe  jz      short loc_180015305
0x180015300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015305  mov     rax, cs:qword_180024678
0x18001530c  test    rax, rax
0x18001530f  jz      short loc_180015316
0x180015311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015316  mov     rax, cs:qword_1800246F0
0x18001531d  test    rax, rax
0x180015320  jz      short loc_180015327
0x180015322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015327  call    UmpoIsServerSku
0x18001532c  test    al, al
0x18001532e  jnz     loc_1800153B6
0x180015334  mov     rax, cs:qword_180024750
0x18001533b  test    rax, rax
0x18001533e  jz      short loc_180015345
0x180015340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015345  mov     rax, cs:qword_180024708
0x18001534c  test    rax, rax
0x18001534f  jz      short loc_18001538B
0x180015351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015356  test    eax, eax
0x180015358  jz      short loc_18001538B
0x18001535a  mov     ecx, cs:UmpoDebug
0x180015360  test    cl, 1
0x180015363  jz      short loc_18001538B
0x180015365  mov     r9d, eax
0x180015368  mov     [rsp+38h+var_18], 2BAh
0x180015370  lea     r8, aExtStopsleepst; "EXT(StopSleepStudyTracing)"
0x180015377  lea     rdx, aUmpomainstop; "UmpoMainStop"
0x18001537e  lea     rcx, aSSError08xLine; "%s: [%s] Error %08x, line %d\n"
0x180015385  call    cs:__imp_DbgPrint
0x18001538b  call    Feature_WISEBatteryDischargeTimeEstimate__private_IsEnabledDeviceUsageNoInline
0x180015390  test    eax, eax
0x180015392  jz      short loc_1800153A5
0x180015394  mov     rax, cs:qword_180024760
0x18001539b  test    rax, rax
0x18001539e  jz      short loc_1800153A5
0x1800153a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a5  mov     rax, cs:qword_180024740
0x1800153ac  test    rax, rax
0x1800153af  jz      short loc_1800153B6
0x1800153b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153b6  call    UmpoNotifyClose
0x1800153bb  cmp     cs:UmpoProviderHandle, rdi
0x1800153c2  jz      short loc_1800153DD
0x1800153c4  call    TraceLoggingUnregister_EventUnregister
0x1800153c9  mov     rcx, cs:UmpoProviderHandle
0x1800153d0  call    cs:__imp_EtwEventUnregister
0x1800153d6  mov     cs:UmpoProviderHandle, rdi
0x1800153dd  xor     edx, edx; Val
0x1800153df  lea     rcx, UmpoExtensions; void *
0x1800153e6  mov     r8d, 0F8h; Size
0x1800153ec  call    memset_0
0x1800153f1  call    UmpoSmartPresenceCleanup
0x1800153f6  mov     rcx, cs:UmpoSmartSuspendPFIUData
0x1800153fd  test    rcx, rcx
0x180015400  jz      short loc_180015408
0x180015402  call    cs:__imp_PfIuPredictionsDataClose
0x180015408  mov     cs:UmpoSmartSuspendState, edi
0x18001540e  mov     cs:UmpoSmartSuspendDisableReason, 1
0x180015418  call    UmpoInternalPowerPolicyCleanup
0x18001541d  cmp     cs:byte_180024AC8, dil
0x180015424  jz      short loc_180015444
0x180015426  lea     rcx, PowerRequestLock; lpCriticalSection
0x18001542d  call    cs:__imp_DeleteCriticalSection
0x180015433  mov     cs:byte_180024AC8, dil
0x18001543a  jmp     short loc_180015444
0x18001543c  mov     rcx, rax
0x18001543f  call    UmpoPowerRequestDeleteEntry
0x180015444  mov     dl, 1; Restart
0x180015446  lea     rcx, UmpoPowerRequestTable; Table
0x18001544d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180015453  test    rax, rax
0x180015456  jnz     short loc_18001543C
0x180015458  cmp     cs:UmpoHeapHandle, rdi
0x18001545f  mov     cs:UmpoInVAILContainer, edi
0x180015465  jz      short loc_18001548A
0x180015467  mov     rax, gs:60h
0x180015470  mov     rcx, cs:UmpoHeapHandle; Heap
0x180015477  cmp     rcx, [rax+30h]
0x18001547b  jz      short loc_18001548A
0x18001547d  call    cs:__imp_RtlDestroyHeap
0x180015483  mov     cs:UmpoHeapHandle, rdi
0x18001548a  xor     r9d, r9d
0x18001548d  xor     r8d, r8d
0x180015490  mov     edx, ebx
0x180015492  lea     ecx, [r9+1]
0x180015496  mov     rbx, [rsp+38h+arg_0]
0x18001549b  add     rsp, 30h
0x18001549f  pop     rdi
0x1800154a0  jmp     UmpoSetStatus
```
