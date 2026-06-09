# UmpoSmartPresenceTimerStop

- ea: `0x1800092a4`
- end: `0x180009381`
- name: `UmpoSmartPresenceTimerStop`
- size: `221`
- prototype: `ULONG()`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009ad0`
- `0x18000c1b4`
- `0x18000c6e0`

## callees

- `0x1800092a4`
- `0x180009f14`
- `0x18000f3dc`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000934f`
- `ntdll!DbgPrint` at `0x18000934f`
- `ntdll!RtlNtStatusToDosError` at `0x18000930d`
- `ntdll!RtlPublishWnfStateData` at `0x180009374`
- `ntdll!RtlPublishWnfStateData` at `0x180009374`
- `ntdll!NtSetIRTimer` at `0x1800092fd`
- `ntdll!NtSetIRTimer` at `0x1800092fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800092ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800092ee`

## pseudocode

```c
ULONG UmpoSmartPresenceTimerStop()
{
  NTSTATUS v0; // eax

  if ( !UmpoSmartPresenceAwayTime )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !UmpoSmartPresenceAwayTimeCount )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( UmpoSmartPresenceSuspendCount )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !byte_1800247D0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  WaitForThreadpoolWaitCallbacks(UmpoTimerWork, 1);
  v0 = NtSetIRTimer(h, 0);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  byte_1800247D0 = 0;
  if ( UmpoSmartPresenceLastPublishedAwayTime )
  {
    UmpoSmartPresenceLastPublishedAwayTime = 0;
    UmpoTraceSmartPresencePrediction(0);
    if ( (UmpoDebug & 2) != 0 )
      DbgPrint(
        "%s: Sending WNF_PO_USER_AWAY_PREDICTION notification (UserAwayEndTime=0)\n",
        "UmpoSmartPresenceTimerStop");
    RtlPublishWnfStateData(WNF_PO_USER_AWAY_PREDICTION, 0, &UmpoSmartPresenceLastPublishedAwayTime, 8, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800092a4  sub     rsp, 38h
0x1800092a8  cmp     cs:UmpoSmartPresenceAwayTime, 0
0x1800092b0  jnz     short loc_1800092B7
0x1800092b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800092b7  cmp     cs:UmpoSmartPresenceAwayTimeCount, 0
0x1800092be  jnz     short loc_1800092C5
0x1800092c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800092c5  cmp     cs:UmpoSmartPresenceSuspendCount, 0
0x1800092cc  jz      short loc_1800092D3
0x1800092ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800092d3  mov     al, cs:byte_1800247D0
0x1800092d9  test    al, al
0x1800092db  jnz     short loc_1800092E2
0x1800092dd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800092e2  mov     rcx, cs:UmpoTimerWork; pwa
0x1800092e9  mov     edx, 1; fCancelPendingCallbacks
0x1800092ee  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800092f4  mov     rcx, cs:h
0x1800092fb  xor     edx, edx
0x1800092fd  call    cs:__imp_NtSetIRTimer
0x180009303  test    eax, eax
0x180009305  jns     short loc_180009314
0x180009307  mov     ecx, eax
0x180009309  add     rsp, 38h
0x18000930d  jmp     cs:__imp_RtlNtStatusToDosError
0x180009314  cmp     cs:UmpoSmartPresenceLastPublishedAwayTime, 0
0x18000931c  mov     cs:byte_1800247D0, 0
0x180009323  jz      short loc_18000937A
0x180009325  xor     ecx, ecx
0x180009327  mov     cs:UmpoSmartPresenceLastPublishedAwayTime, 0
0x180009332  call    UmpoTraceSmartPresencePrediction
0x180009337  mov     eax, cs:UmpoDebug
0x18000933d  test    al, 2
0x18000933f  jz      short loc_180009355
0x180009341  lea     rdx, aUmposmartprese; "UmpoSmartPresenceTimerStop"
0x180009348  lea     rcx, aSSendingWnfPoU; "%s: Sending WNF_PO_USER_AWAY_PREDICTION"...
0x18000934f  call    cs:__imp_DbgPrint
0x180009355  mov     rcx, cs:WNF_PO_USER_AWAY_PREDICTION
0x18000935c  lea     r8, UmpoSmartPresenceLastPublishedAwayTime
0x180009363  mov     r9d, 8
0x180009369  mov     [rsp+38h+var_18], 0
0x180009372  xor     edx, edx
0x180009374  call    cs:__imp_RtlPublishWnfStateData
0x18000937a  xor     eax, eax
0x18000937c  add     rsp, 38h
0x180009380  retn
```
