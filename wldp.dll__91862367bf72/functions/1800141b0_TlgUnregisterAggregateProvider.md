# TlgUnregisterAggregateProvider

- ea: `0x1800141b0`
- end: `0x180014339`
- name: `TlgUnregisterAggregateProvider`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c620`

## callees

- `0x1800141b0`
- `0x180014340`
- `0x1800143e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001422f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014313`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001422f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014313`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800141da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800141da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014249`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001429d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014249`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001429d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014268`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800142bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014268`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800142bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001425b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800142af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001425b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800142af`

## pseudocode

```c
int __fastcall TlgUnregisterAggregateProvider(__int64 a1)
{
  __int64 *i; // rcx
  __int64 v3; // rbx
  struct _TP_TIMER *v4; // rcx
  struct _TP_TIMER *v5; // rcx
  HANDLE ProcessHeap; // rax
  int result; // eax

  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) != TlgAggregateInternalRegisteredProviderEtwCallback )
    return ((__int64 (*)(void))TraceLoggingUnregister_EventUnregister)();
  AcquireSRWLockExclusive(&SRWLock);
  for ( i = &qword_18005AFB0; ; i = (__int64 *)(v3 + 336) )
  {
    v3 = *i;
    if ( !*i )
    {
      ReleaseSRWLockExclusive(&SRWLock);
      result = TraceLoggingUnregister_EventUnregister(a1);
      *(_QWORD *)(a1 + 40) = 0;
      return result;
    }
    if ( *(_QWORD *)(v3 + 328) == a1 )
      break;
  }
  *i = *(_QWORD *)(v3 + 336);
  LookUpTableFlushComplete(v3);
  if ( !qword_18005AFB0 )
    TraceLoggingUnregister_EventUnregister(&dword_18005A340);
  ReleaseSRWLockExclusive(&SRWLock);
  v4 = *(struct _TP_TIMER **)(v3 + 344);
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(v3 + 344), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(v3 + 344));
    *(_QWORD *)(v3 + 344) = 0;
  }
  TraceLoggingUnregister_EventUnregister(a1);
  *(_QWORD *)(a1 + 40) = 0;
  v5 = *(struct _TP_TIMER **)(v3 + 344);
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(v3 + 344), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(v3 + 344));
    *(_QWORD *)(v3 + 344) = 0;
  }
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, (LPVOID)v3);
}

```

## disassembly

```asm
0x1800141b0  mov     [rsp+arg_8], rsi
0x1800141b5  push    rdi
0x1800141b6  sub     rsp, 20h
0x1800141ba  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x1800141c1  mov     rdi, rcx
0x1800141c4  cmp     [rcx+28h], rax
0x1800141c8  jnz     loc_1800142F1
0x1800141ce  lea     rcx, SRWLock; SRWLock
0x1800141d5  mov     [rsp+28h+arg_0], rbx
0x1800141da  call    cs:__imp_AcquireSRWLockExclusive
0x1800141e0  lea     rcx, qword_18005AFB0
0x1800141e7  mov     rbx, [rcx]
0x1800141ea  test    rbx, rbx
0x1800141ed  jz      loc_18001430C
0x1800141f3  cmp     [rbx+148h], rdi
0x1800141fa  jnz     loc_180014300
0x180014200  mov     rax, [rbx+150h]
0x180014207  mov     [rcx], rax
0x18001420a  mov     rcx, rbx
0x18001420d  call    LookUpTableFlushComplete
0x180014212  cmp     cs:qword_18005AFB0, 0
0x18001421a  jnz     short loc_180014228
0x18001421c  lea     rcx, dword_18005A340
0x180014223  call    TraceLoggingUnregister_EventUnregister
0x180014228  lea     rcx, SRWLock; SRWLock
0x18001422f  call    cs:__imp_ReleaseSRWLockExclusive
0x180014235  mov     rcx, [rbx+158h]; pti
0x18001423c  test    rcx, rcx
0x18001423f  jz      short loc_180014279
0x180014241  xor     r9d, r9d; msWindowLength
0x180014244  xor     r8d, r8d; msPeriod
0x180014247  xor     edx, edx; pftDueTime
0x180014249  call    cs:__imp_SetThreadpoolTimer
0x18001424f  mov     rcx, [rbx+158h]; pti
0x180014256  mov     edx, 1; fCancelPendingCallbacks
0x18001425b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014261  mov     rcx, [rbx+158h]; pti
0x180014268  call    cs:__imp_CloseThreadpoolTimer
0x18001426e  mov     qword ptr [rbx+158h], 0
0x180014279  mov     rcx, rdi
0x18001427c  call    TraceLoggingUnregister_EventUnregister
0x180014281  mov     qword ptr [rdi+28h], 0
0x180014289  mov     rcx, [rbx+158h]; pti
0x180014290  test    rcx, rcx
0x180014293  jz      short loc_1800142CD
0x180014295  xor     r9d, r9d; msWindowLength
0x180014298  xor     r8d, r8d; msPeriod
0x18001429b  xor     edx, edx; pftDueTime
0x18001429d  call    cs:__imp_SetThreadpoolTimer
0x1800142a3  mov     rcx, [rbx+158h]; pti
0x1800142aa  mov     edx, 1; fCancelPendingCallbacks
0x1800142af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800142b5  mov     rcx, [rbx+158h]; pti
0x1800142bc  call    cs:__imp_CloseThreadpoolTimer
0x1800142c2  mov     qword ptr [rbx+158h], 0
0x1800142cd  call    cs:__imp_GetProcessHeap
0x1800142d3  mov     r8, rbx
0x1800142d6  xor     edx, edx
0x1800142d8  mov     rcx, rax
0x1800142db  mov     rbx, [rsp+28h+arg_0]
0x1800142e0  mov     rsi, [rsp+28h+arg_8]
0x1800142e5  add     rsp, 20h
0x1800142e9  pop     rdi
0x1800142ea  jmp     cs:__imp_HeapFree
0x1800142f1  mov     rsi, [rsp+28h+arg_8]
0x1800142f6  add     rsp, 20h
0x1800142fa  pop     rdi
0x1800142fb  jmp     TraceLoggingUnregister_EventUnregister
0x180014300  lea     rcx, [rbx+150h]
0x180014307  jmp     loc_1800141E7
0x18001430c  lea     rcx, SRWLock; SRWLock
0x180014313  call    cs:__imp_ReleaseSRWLockExclusive
0x180014319  mov     rcx, rdi
0x18001431c  call    TraceLoggingUnregister_EventUnregister
0x180014321  mov     rbx, [rsp+28h+arg_0]
0x180014326  mov     rsi, [rsp+28h+arg_8]
0x18001432b  mov     qword ptr [rdi+28h], 0
0x180014333  add     rsp, 20h
0x180014337  pop     rdi
0x180014338  retn
```
