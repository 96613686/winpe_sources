# WpnClientTelemetry::~WpnClientTelemetry(void)

- ea: `0x180025f04`
- end: `0x180025f24`
- name: `??1WpnClientTelemetry@@UEAA@XZ`
- size: `32`
- prototype: `void __fastcall(WpnClientTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800260b0`

## callees

- `0x18001cae4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f11`

## pseudocode

```c
void __fastcall WpnClientTelemetry::~WpnClientTelemetry(WpnClientTelemetry *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
}

```

## disassembly

```asm
0x180025f04  push    rbx
0x180025f06  sub     rsp, 20h
0x180025f0a  mov     rbx, rcx
0x180025f0d  add     rcx, 18h; lpCriticalSection
0x180025f11  call    cs:__imp_DeleteCriticalSection
0x180025f17  mov     rcx, rbx; this
0x180025f1a  add     rsp, 20h
0x180025f1e  pop     rbx
0x180025f1f  jmp     ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
```
