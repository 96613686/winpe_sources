# WUComTimeout::ComTimeout::~ComTimeout(void)

- ea: `0x1800316bc`
- end: `0x180031706`
- name: `??1ComTimeout@WUComTimeout@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(WUComTimeout::ComTimeout *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800236c4`
- `0x18002e66c`
- `0x18004a807`
- `0x18004ad4e`

## callees

- `0x1800316bc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800316e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800316e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800316ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800316ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800316d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800316d5`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800316fa`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800316fa`

## pseudocode

```c
void __fastcall WUComTimeout::ComTimeout::~ComTimeout(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    CloseThreadpoolTimer(*this);
  }
  if ( *((_BYTE *)this + 12) )
    CoDisableCallCancellation(0);
}

```

## disassembly

```asm
0x1800316bc  push    rbx
0x1800316be  sub     rsp, 20h
0x1800316c2  mov     rbx, rcx
0x1800316c5  mov     rcx, [rcx]; pti
0x1800316c8  test    rcx, rcx
0x1800316cb  jz      short loc_1800316F2
0x1800316cd  xor     r9d, r9d; msWindowLength
0x1800316d0  xor     r8d, r8d; msPeriod
0x1800316d3  xor     edx, edx; pftDueTime
0x1800316d5  call    cs:__imp_SetThreadpoolTimer
0x1800316db  mov     rcx, [rbx]; pti
0x1800316de  mov     edx, 1; fCancelPendingCallbacks
0x1800316e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800316e9  mov     rcx, [rbx]; pti
0x1800316ec  call    cs:__imp_CloseThreadpoolTimer
0x1800316f2  cmp     byte ptr [rbx+0Ch], 0
0x1800316f6  jz      short loc_180031700
0x1800316f8  xor     ecx, ecx; pReserved
0x1800316fa  call    cs:__imp_CoDisableCallCancellation
0x180031700  add     rsp, 20h
0x180031704  pop     rbx
0x180031705  retn
```
