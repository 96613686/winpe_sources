# UsoScheduler::~UsoScheduler(void)

- ea: `0x180070188`
- end: `0x180070233`
- name: `??1UsoScheduler@@QEAA@XZ`
- size: `171`
- prototype: `void __fastcall(UsoScheduler *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000f324`
- `0x180013bd0`
- `0x180014650`
- `0x1800164f0`
- `0x1800165b8`
- `0x180016b5c`
- `0x180017158`
- `0x1800172fc`
- `0x1800187f0`
- `0x18001dfa0`

## callees

- `0x180011680`
- `0x180070188`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007022c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800701a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800701f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800701a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800701f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180070219`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180070219`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007020a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007020a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800701b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070201`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800701b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070201`

## pseudocode

```c
void __fastcall UsoScheduler::~UsoScheduler(UsoScheduler *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rcx
  struct _TP_TIMER *v4; // rdi
  struct _TP_POOL *v5; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 15), 1);
  }
  v3 = *((_QWORD *)this + 34);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  std::wstring::~wstring((_QWORD *)this + 16);
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 15);
  if ( v4 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 15), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
  v5 = (struct _TP_POOL *)*((_QWORD *)this + 14);
  if ( v5 )
    CloseThreadpool(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180070188  mov     [rsp+arg_0], rbx
0x18007018d  push    rdi
0x18007018e  sub     rsp, 20h
0x180070192  mov     rbx, rcx
0x180070195  mov     rcx, [rcx+78h]; pti
0x180070199  test    rcx, rcx
0x18007019c  jz      short loc_1800701BB
0x18007019e  xor     r9d, r9d; msWindowLength
0x1800701a1  xor     r8d, r8d; msPeriod
0x1800701a4  xor     edx, edx; pftDueTime
0x1800701a6  call    cs:__imp_SetThreadpoolTimer
0x1800701ac  mov     rcx, [rbx+78h]; pti
0x1800701b0  mov     edx, 1; fCancelPendingCallbacks
0x1800701b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800701bb  mov     rcx, [rbx+110h]
0x1800701c2  test    rcx, rcx
0x1800701c5  jz      short loc_1800701D3
0x1800701c7  mov     rax, [rcx]
0x1800701ca  mov     rax, [rax+18h]
0x1800701ce  call    _guard_dispatch_icall
0x1800701d3  lea     rcx, [rbx+80h]; void *
0x1800701da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800701df  mov     rdi, [rbx+78h]
0x1800701e3  test    rdi, rdi
0x1800701e6  jz      short loc_180070210
0x1800701e8  xor     r9d, r9d; msWindowLength
0x1800701eb  xor     r8d, r8d; msPeriod
0x1800701ee  xor     edx, edx; pftDueTime
0x1800701f0  mov     rcx, rdi; pti
0x1800701f3  call    cs:__imp_SetThreadpoolTimer
0x1800701f9  mov     edx, 1; fCancelPendingCallbacks
0x1800701fe  mov     rcx, rdi; pti
0x180070201  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180070207  mov     rcx, rdi; pti
0x18007020a  call    cs:__imp_CloseThreadpoolTimer
0x180070210  mov     rcx, [rbx+70h]; ptpp
0x180070214  test    rcx, rcx
0x180070217  jz      short loc_18007021F
0x180070219  call    cs:__imp_CloseThreadpool
0x18007021f  mov     rcx, rbx
0x180070222  mov     rbx, [rsp+28h+arg_0]
0x180070227  add     rsp, 20h
0x18007022b  pop     rdi
0x18007022c  jmp     cs:__imp_DeleteCriticalSection
```
