# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x180025ec8`
- end: `0x180025efd`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026854`
- `0x18002c28c`

## callees

- `0x180025ec8`
- `0x18002629c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180025ef6`

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
0x180025ec8  push    rbx
0x180025eca  sub     rsp, 20h
0x180025ece  cmp     dword ptr [rcx+8], 0
0x180025ed2  mov     rbx, rcx
0x180025ed5  jnz     short loc_180025EE7
0x180025ed7  mov     rcx, [rcx]
0x180025eda  add     rcx, 8; this
0x180025ede  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180025ee2  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180025ee7  mov     rcx, [rbx]
0x180025eea  mov     edx, [rbx+8]
0x180025eed  lea     r8, [rcx+8]
0x180025ef1  add     rsp, 20h
0x180025ef5  pop     rbx
0x180025ef6  jmp     cs:__imp_InitOnceComplete
```
