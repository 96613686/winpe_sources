# wil::details::static_lazy<PerfLibLogging>::Completer::~Completer(void)

- ea: `0x18001270c`
- end: `0x180012741`
- name: `??1Completer@?$static_lazy@VPerfLibLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012f04`

## callees

- `0x18001270c`
- `0x18001295c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001273a`

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
0x18001270c  push    rbx
0x18001270e  sub     rsp, 20h
0x180012712  cmp     dword ptr [rcx+8], 0
0x180012716  mov     rbx, rcx
0x180012719  jnz     short loc_18001272B
0x18001271b  mov     rcx, [rcx]
0x18001271e  add     rcx, 8; this
0x180012722  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180012726  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001272b  mov     rcx, [rbx]
0x18001272e  mov     edx, [rbx+8]
0x180012731  lea     r8, [rcx+8]
0x180012735  add     rsp, 20h
0x180012739  pop     rbx
0x18001273a  jmp     cs:__imp_InitOnceComplete
```
