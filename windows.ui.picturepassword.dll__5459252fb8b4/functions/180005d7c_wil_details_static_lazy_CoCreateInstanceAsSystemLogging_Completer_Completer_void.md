# wil::details::static_lazy<CoCreateInstanceAsSystemLogging>::Completer::~Completer(void)

- ea: `0x180005d7c`
- end: `0x180005db1`
- name: `??1Completer@?$static_lazy@VCoCreateInstanceAsSystemLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b704`
- `0x1800181ec`
- `0x18001e1e0`

## callees

- `0x180005d7c`
- `0x180008dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005daa`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CoCreateInstanceAsSystemLogging>::Completer::~Completer(
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
0x180005d7c  push    rbx
0x180005d7e  sub     rsp, 20h
0x180005d82  cmp     dword ptr [rcx+8], 0
0x180005d86  mov     rbx, rcx
0x180005d89  jnz     short loc_180005D9B
0x180005d8b  mov     rcx, [rcx]
0x180005d8e  add     rcx, 8; this
0x180005d92  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180005d96  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180005d9b  mov     rcx, [rbx]
0x180005d9e  mov     edx, [rbx+8]
0x180005da1  lea     r8, [rcx+8]
0x180005da5  add     rsp, 20h
0x180005da9  pop     rbx
0x180005daa  jmp     cs:__imp_InitOnceComplete
```
