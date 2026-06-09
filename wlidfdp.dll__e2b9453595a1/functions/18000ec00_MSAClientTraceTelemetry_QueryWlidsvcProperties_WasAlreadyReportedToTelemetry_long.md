# MSAClientTraceTelemetry::QueryWlidsvcProperties::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000ec00`
- end: `0x18000ec0e`
- name: `?WasAlreadyReportedToTelemetry@QueryWlidsvcProperties@MSAClientTraceTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
bool __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::WasAlreadyReportedToTelemetry(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000ec00  mov     eax, edx
0x18000ec02  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000ec08  cmp     eax, edx
0x18000ec0a  setz    al
0x18000ec0d  retn
```
