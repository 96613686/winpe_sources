# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x140046028`
- end: `0x14004605d`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14004ac3c`
- `0x14005e300`

## callees

- `0x140046028`
- `0x140049100`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140046056`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(
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
0x140046028  push    rbx
0x14004602a  sub     rsp, 20h
0x14004602e  cmp     dword ptr [rcx+8], 0
0x140046032  mov     rbx, rcx
0x140046035  jnz     short loc_140046047
0x140046037  mov     rcx, [rcx]
0x14004603a  add     rcx, 8; this
0x14004603e  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x140046042  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140046047  mov     rcx, [rbx]
0x14004604a  mov     edx, [rbx+8]
0x14004604d  lea     r8, [rcx+8]
0x140046051  add     rsp, 20h
0x140046055  pop     rbx
0x140046056  jmp     cs:__imp_InitOnceComplete
```
