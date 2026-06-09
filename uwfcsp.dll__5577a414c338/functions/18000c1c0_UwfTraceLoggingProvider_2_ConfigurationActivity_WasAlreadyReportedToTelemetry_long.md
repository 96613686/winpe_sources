# UwfTraceLoggingProvider<2>::ConfigurationActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000c1c0`
- end: `0x18000c1ce`
- name: `?WasAlreadyReportedToTelemetry@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(__int64, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
bool __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::WasAlreadyReportedToTelemetry(
        __int64 a1,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000c1c0  mov     eax, edx
0x18000c1c2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000c1c8  cmp     eax, edx
0x18000c1ca  setz    al
0x18000c1cd  retn
```
