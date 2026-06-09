# UmpoSmartPresenceFreeIntervals

- ea: `0x180009ad0`
- end: `0x180009b47`
- name: `UmpoSmartPresenceFreeIntervals`
- size: `119`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098e4`
- `0x18000c960`
- `0x18001728c`

## callees

- `0x1800092a4`
- `0x180009ad0`
- `0x18000c9f4`
- `0x18000f3dc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180009b06`
- `ntdll!RtlFreeHeap` at `0x180009b06`

## pseudocode

```c
__int64 UmpoSmartPresenceFreeIntervals()
{
  __int64 result; // rax

  if ( !UmpoSmartPresenceAwayTime )
  {
    if ( UmpoSmartPresenceAwayTimeCount )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( byte_1800247D0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    return 0;
  }
  if ( !byte_1800247D0 || (result = UmpoSmartPresenceTimerStop(), !(_DWORD)result) )
  {
    UmpoTraceSmartPresenceClearAwayIntervals();
    RtlFreeHeap(UmpoHeapHandle, 0, UmpoSmartPresenceAwayTime);
    UmpoSmartPresenceAwayTime = 0;
    UmpoSmartPresenceAwayTimeCount = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009ad0  sub     rsp, 28h
0x180009ad4  cmp     cs:UmpoSmartPresenceAwayTime, 0
0x180009adc  jz      short loc_180009B23
0x180009ade  mov     al, cs:byte_1800247D0
0x180009ae4  test    al, al
0x180009ae6  jz      short loc_180009AF1
0x180009ae8  call    UmpoSmartPresenceTimerStop
0x180009aed  test    eax, eax
0x180009aef  jnz     short loc_180009B42
0x180009af1  call    UmpoTraceSmartPresenceClearAwayIntervals
0x180009af6  mov     r8, cs:UmpoSmartPresenceAwayTime; P
0x180009afd  xor     edx, edx; Flags
0x180009aff  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180009b06  call    cs:__imp_RtlFreeHeap
0x180009b0c  mov     cs:UmpoSmartPresenceAwayTime, 0
0x180009b17  mov     cs:UmpoSmartPresenceAwayTimeCount, 0
0x180009b21  jmp     short loc_180009B40
0x180009b23  cmp     cs:UmpoSmartPresenceAwayTimeCount, 0
0x180009b2a  jz      short loc_180009B31
0x180009b2c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009b31  mov     al, cs:byte_1800247D0
0x180009b37  test    al, al
0x180009b39  jz      short loc_180009B40
0x180009b3b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009b40  xor     eax, eax
0x180009b42  add     rsp, 28h
0x180009b46  retn
```
