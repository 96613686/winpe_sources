# WpnprvTelemetry::~WpnprvTelemetry(void)

- ea: `0x180033e0c`
- end: `0x180033e36`
- name: `??1WpnprvTelemetry@@UEAA@XZ`
- size: `42`
- prototype: `void __fastcall(WpnprvTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033f10`

## callees

- `0x180014c58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033e19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033e23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033e19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033e23`

## pseudocode

```c
void __fastcall WpnprvTelemetry::~WpnprvTelemetry(WpnprvTelemetry *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
}

```

## disassembly

```asm
0x180033e0c  push    rbx
0x180033e0e  sub     rsp, 20h
0x180033e12  mov     rbx, rcx
0x180033e15  add     rcx, 40h ; '@'; lpCriticalSection
0x180033e19  call    cs:__imp_DeleteCriticalSection
0x180033e1f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180033e23  call    cs:__imp_DeleteCriticalSection
0x180033e29  mov     rcx, rbx; this
0x180033e2c  add     rsp, 20h
0x180033e30  pop     rbx
0x180033e31  jmp     ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
```
