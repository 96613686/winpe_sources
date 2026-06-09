# Telemetry4UpdateCli::RunCmd::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000cef0`
- end: `0x18000cf02`
- name: `?WasAlreadyReportedToTelemetry@RunCmd@Telemetry4UpdateCli@@MEAA_NJ@Z`
- size: `18`
- prototype: `bool __fastcall(Telemetry4UpdateCli::RunCmd *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
bool __fastcall Telemetry4UpdateCli::RunCmd::WasAlreadyReportedToTelemetry(Telemetry4UpdateCli::RunCmd *this, int a2)
{
  bool v2; // zf

  v2 = `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen == a2;
  `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen = a2;
  return v2;
}

```

## disassembly

```asm
0x18000cef0  mov     eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000cef6  cmp     eax, edx
0x18000cef8  mov     cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC, edx; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000cefe  setz    al
0x18000cf01  retn
```
