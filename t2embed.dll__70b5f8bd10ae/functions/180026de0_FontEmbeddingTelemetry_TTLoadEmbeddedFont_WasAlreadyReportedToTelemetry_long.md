# FontEmbeddingTelemetry::TTLoadEmbeddedFont::WasAlreadyReportedToTelemetry(long)

- ea: `0x180026de0`
- end: `0x180026dee`
- name: `?WasAlreadyReportedToTelemetry@TTLoadEmbeddedFont@FontEmbeddingTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(FontEmbeddingTelemetry::TTLoadEmbeddedFont *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall FontEmbeddingTelemetry::TTLoadEmbeddedFont::WasAlreadyReportedToTelemetry(
        FontEmbeddingTelemetry::TTLoadEmbeddedFont *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x180026de0  mov     eax, edx
0x180026de2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x180026de8  cmp     eax, edx
0x180026dea  setz    al
0x180026ded  retn
```
