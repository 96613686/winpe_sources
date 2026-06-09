# SVSThreadPool::Worker(void)

- ea: `0x1800246f0`
- end: `0x1800248f4`
- name: `?Worker@SVSThreadPool@@IEAAXXZ`
- size: `516`
- prototype: `void __fastcall(SVSThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180052970`

## callees

- `0x1800246f0`
- `0x1800248fc`
- `0x1800249e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024817`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024817`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024780`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024843`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024780`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024843`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002473d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002473d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024878`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024878`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248e3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800248a6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800248a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800248be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800248be`

## pseudocode

```c
void __fastcall SVSThreadPool::Worker(SVSThreadPool *this)
{
  void *v2; // rsi
  int v3; // r14d
  DWORD DelayUntilNextEvent; // ebp
  struct SVSThreadBlock *NextJobFromQueue; // rsi
  struct SVSThreadBlock **v6; // r14
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  HANDLE Thread; // rax

  if ( *((_DWORD *)this + 22) )
  {
    while ( 1 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 1, 0) )
      {
        v2 = (void *)*((_QWORD *)this + 9);
        v3 = 0;
        DelayUntilNextEvent = 300000;
      }
      else
      {
        v2 = (void *)*((_QWORD *)this + 10);
        v3 = 1;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        DelayUntilNextEvent = SVSThreadPool::GetDelayUntilNextEvent(this);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      }
      if ( WaitForSingleObject(v2, DelayUntilNextEvent) == 258 )
        break;
      if ( v3 )
        goto LABEL_10;
LABEL_6:
      if ( !*((_DWORD *)this + 22) )
        goto LABEL_7;
    }
    if ( !v3 )
      goto LABEL_7;
LABEL_10:
    *((_DWORD *)this + 27) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    NextJobFromQueue = SVSThreadPool::GetNextJobFromQueue(this);
    if ( NextJobFromQueue )
    {
      ++*((_DWORD *)this + 24);
      if ( --*((_DWORD *)this + 25) )
      {
        SetEvent(*((HANDLE *)this + 9));
      }
      else if ( *((_DWORD *)this + 24) < *((_DWORD *)this + 23) )
      {
        Thread = CreateThread(0, 0, SVSThreadPool::SVSThreadPoolWorkerThread, this, 0, 0);
        if ( Thread )
        {
          CloseHandle(Thread);
          ++*((_DWORD *)this + 25);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      (*(void (__fastcall **)(_QWORD))NextJobFromQueue)(*((_QWORD *)NextJobFromQueue + 1));
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      v6 = (struct SVSThreadBlock **)*((_QWORD *)this + 8);
      v7 = (struct _RTL_CRITICAL_SECTION *)v6[2];
      if ( v7 )
        EnterCriticalSection(v7);
      *(_QWORD *)NextJobFromQueue = *v6;
      v8 = (struct _RTL_CRITICAL_SECTION *)v6[2];
      *v6 = NextJobFromQueue;
      if ( v8 )
        LeaveCriticalSection(v8);
      ++*((_DWORD *)this + 25);
      --*((_DWORD *)this + 24);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    goto LABEL_6;
  }
LABEL_7:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  --*((_DWORD *)this + 25);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800246f0  push    rbx
0x1800246f2  push    rdi
0x1800246f3  sub     rsp, 38h
0x1800246f7  cmp     dword ptr [rcx+58h], 0
0x1800246fb  mov     rbx, rcx
0x1800246fe  jz      short loc_18002477C
0x180024700  mov     [rsp+48h+arg_0], rbp
0x180024705  mov     [rsp+48h+arg_8], rsi
0x18002470a  mov     [rsp+48h+arg_10], r12
0x18002470f  xor     r12d, r12d
0x180024712  mov     [rsp+48h+var_18], r15
0x180024717  mov     r15d, 1
0x18002471d  mov     [rsp+48h+arg_18], r14
0x180024722  xor     eax, eax
0x180024724  lock cmpxchg [rbx+6Ch], r15d
0x18002472a  jz      short loc_1800247A5
0x18002472c  mov     rsi, [rbx+48h]
0x180024730  mov     r14d, r12d
0x180024733  mov     ebp, 493E0h
0x180024738  mov     edx, ebp; dwMilliseconds
0x18002473a  mov     rcx, rsi; hHandle
0x18002473d  call    cs:__imp_WaitForSingleObject
0x180024744  nop     dword ptr [rax+rax+00h]
0x180024749  cmp     eax, 102h
0x18002474e  jz      loc_1800247DB
0x180024754  test    r14d, r14d
0x180024757  jnz     loc_1800247E0
0x18002475d  cmp     [rbx+58h], r12d
0x180024761  jnz     short loc_180024722
0x180024763  mov     r14, [rsp+48h+arg_18]
0x180024768  mov     r12, [rsp+48h+arg_10]
0x18002476d  mov     rsi, [rsp+48h+arg_8]
0x180024772  mov     rbp, [rsp+48h+arg_0]
0x180024777  mov     r15, [rsp+48h+var_18]
0x18002477c  lea     rcx, [rbx+18h]; lpCriticalSection
0x180024780  call    cs:__imp_EnterCriticalSection
0x180024787  nop     dword ptr [rax+rax+00h]
0x18002478c  dec     dword ptr [rbx+64h]
0x18002478f  lea     rcx, [rbx+18h]
0x180024793  add     rsp, 38h
0x180024797  pop     rdi
0x180024798  pop     rbx
0x180024799  jmp     cs:__imp_LeaveCriticalSection
0x1800247a5  mov     rsi, [rbx+50h]
0x1800247a9  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800247ad  mov     r14d, r15d
0x1800247b0  call    cs:__imp_EnterCriticalSection
0x1800247b7  nop     dword ptr [rax+rax+00h]
0x1800247bc  mov     rcx, rbx; this
0x1800247bf  call    ?GetDelayUntilNextEvent@SVSThreadPool@@IEAAKXZ; SVSThreadPool::GetDelayUntilNextEvent(void)
0x1800247c4  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800247c8  mov     ebp, eax
0x1800247ca  call    cs:__imp_LeaveCriticalSection
0x1800247d1  nop     dword ptr [rax+rax+00h]
0x1800247d6  jmp     loc_180024738
0x1800247db  test    r14d, r14d
0x1800247de  jz      short loc_180024763
0x1800247e0  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800247e4  mov     [rbx+6Ch], r12d
0x1800247e8  call    cs:__imp_EnterCriticalSection
0x1800247ef  nop     dword ptr [rax+rax+00h]
0x1800247f4  mov     rcx, rbx; this
0x1800247f7  call    ?GetNextJobFromQueue@SVSThreadPool@@IEAAPEAVSVSThreadBlock@@XZ; SVSThreadPool::GetNextJobFromQueue(void)
0x1800247fc  mov     rsi, rax
0x1800247ff  test    rax, rax
0x180024802  jz      short loc_180024874
0x180024804  inc     dword ptr [rbx+60h]
0x180024807  dec     dword ptr [rbx+64h]
0x18002480a  mov     eax, [rbx+60h]
0x18002480d  cmp     [rbx+64h], r12d
0x180024811  jz      short loc_180024889
0x180024813  mov     rcx, [rbx+48h]; hEvent
0x180024817  call    cs:__imp_SetEvent
0x18002481e  nop     dword ptr [rax+rax+00h]
0x180024823  lea     rcx, [rbx+18h]; lpCriticalSection
0x180024827  call    cs:__imp_LeaveCriticalSection
0x18002482e  nop     dword ptr [rax+rax+00h]
0x180024833  mov     rcx, [rsi+8]
0x180024837  mov     rax, [rsi]
0x18002483a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002483f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180024843  call    cs:__imp_EnterCriticalSection
0x18002484a  nop     dword ptr [rax+rax+00h]
0x18002484f  mov     r14, [rbx+40h]
0x180024853  mov     rcx, [r14+10h]; lpCriticalSection
0x180024857  test    rcx, rcx
0x18002485a  jnz     short loc_1800248D2
0x18002485c  mov     rax, [r14]
0x18002485f  mov     [rsi], rax
0x180024862  mov     rcx, [r14+10h]; lpCriticalSection
0x180024866  mov     [r14], rsi
0x180024869  test    rcx, rcx
0x18002486c  jnz     short loc_1800248E3
0x18002486e  inc     dword ptr [rbx+64h]
0x180024871  dec     dword ptr [rbx+60h]
0x180024874  lea     rcx, [rbx+18h]; lpCriticalSection
0x180024878  call    cs:__imp_LeaveCriticalSection
0x18002487f  nop     dword ptr [rax+rax+00h]
0x180024884  jmp     loc_18002475D
0x180024889  cmp     eax, [rbx+5Ch]
0x18002488c  jnb     short loc_180024823
0x18002488e  mov     [rsp+48h+lpThreadId], r12; lpThreadId
0x180024893  lea     r8, ?SVSThreadPoolWorkerThread@SVSThreadPool@@KAKPEAX@Z; lpStartAddress
0x18002489a  mov     r9, rbx; lpParameter
0x18002489d  mov     [rsp+48h+dwCreationFlags], r12d; dwCreationFlags
0x1800248a2  xor     edx, edx; dwStackSize
0x1800248a4  xor     ecx, ecx; lpThreadAttributes
0x1800248a6  call    cs:__imp_CreateThread
0x1800248ad  nop     dword ptr [rax+rax+00h]
0x1800248b2  test    rax, rax
0x1800248b5  jz      loc_180024823
0x1800248bb  mov     rcx, rax; hObject
0x1800248be  call    cs:__imp_CloseHandle
0x1800248c5  nop     dword ptr [rax+rax+00h]
0x1800248ca  inc     dword ptr [rbx+64h]
0x1800248cd  jmp     loc_180024823
0x1800248d2  call    cs:__imp_EnterCriticalSection
0x1800248d9  nop     dword ptr [rax+rax+00h]
0x1800248de  jmp     loc_18002485C
0x1800248e3  call    cs:__imp_LeaveCriticalSection
0x1800248ea  nop     dword ptr [rax+rax+00h]
0x1800248ef  jmp     loc_18002486E
```
