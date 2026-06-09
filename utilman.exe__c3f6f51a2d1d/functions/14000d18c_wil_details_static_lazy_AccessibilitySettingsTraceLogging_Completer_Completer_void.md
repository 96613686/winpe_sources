# wil::details::static_lazy<AccessibilitySettingsTraceLogging>::Completer::~Completer(void)

- ea: `0x14000d18c`
- end: `0x14000d1c6`
- name: `??1Completer@?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010680`
- `0x14001bbd0`
- `0x140022f58`

## callees

- `0x14000d18c`
- `0x14000ed7c`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14000d1ba`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<AccessibilitySettingsTraceLogging>::Completer::~Completer(
        _DWORD *a1,
        __int64 a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  if ( !a1[2] )
    wil::TraceLoggingProvider::Register(
      (wil::TraceLoggingProvider *)(*(_QWORD *)a1 + 8LL),
      *(const struct _tlgProvider_t *const *)(*(_QWORD *)a1 + 32LL),
      a3);
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x14000d18c  push    rbx
0x14000d18e  sub     rsp, 20h
0x14000d192  cmp     dword ptr [rcx+8], 0
0x14000d196  mov     rbx, rcx
0x14000d199  jnz     short loc_14000D1AB
0x14000d19b  mov     rcx, [rcx]
0x14000d19e  add     rcx, 8; this
0x14000d1a2  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x14000d1a6  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x14000d1ab  mov     rcx, [rbx]
0x14000d1ae  mov     edx, [rbx+8]
0x14000d1b1  lea     r8, [rcx+8]
0x14000d1b5  add     rsp, 20h
0x14000d1b9  pop     rbx
0x14000d1ba  jmp     cs:__imp_InitOnceComplete
```
