# wil::details::static_lazy<PerfLibLogging>::Completer::~Completer(void)

- ea: `0x180013e40`
- end: `0x180013e7a`
- name: `??1Completer@?$static_lazy@VPerfLibLogging@@@details@wil@@QEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001465c`

## callees

- `0x180013e40`
- `0x18001409c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013e6e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PerfLibLogging>::Completer::~Completer(
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
0x180013e40  push    rbx
0x180013e42  sub     rsp, 20h
0x180013e46  cmp     dword ptr [rcx+8], 0
0x180013e4a  mov     rbx, rcx
0x180013e4d  jnz     short loc_180013E5F
0x180013e4f  mov     rcx, [rcx]
0x180013e52  add     rcx, 8; this
0x180013e56  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180013e5a  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180013e5f  mov     rcx, [rbx]
0x180013e62  mov     edx, [rbx+8]
0x180013e65  lea     r8, [rcx+8]
0x180013e69  add     rsp, 20h
0x180013e6d  pop     rbx
0x180013e6e  jmp     cs:__imp_InitOnceComplete
```
