# COMXProc::CThreadTaskDelayedShutdown::DoCheck(void)

- ea: `0x1800293ac`
- end: `0x1800294c7`
- name: `?DoCheck@CThreadTaskDelayedShutdown@COMXProc@@SAXXZ`
- size: `283`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001bb0`

## callees

- `0x180003570`
- `0x1800137e0`
- `0x1800169e0`
- `0x18001b404`
- `0x1800293ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800293e9`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800293e9`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180029432`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180029432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800293bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800293bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002943f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002943f`

## pseudocode

```c
void COMXProc::CThreadTaskDelayedShutdown::DoCheck(void)
{
  int v0; // edi
  HANDLE WaitableTimer; // rax
  _QWORD *v2; // rax
  void *v3; // rbx
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  EnterCriticalSection(&CriticalSection);
  if ( COMXProc::CThreadTaskDelayedShutdown::s_fInProgress )
  {
    WaitableTimer = COMXProc::CThreadTaskDelayedShutdown::s_hTimer;
  }
  else
  {
    v0 = 1;
    COMXProc::CThreadTaskDelayedShutdown::s_fInProgress = 1;
    WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    COMXProc::CThreadTaskDelayedShutdown::s_hTimer = WaitableTimer;
  }
  if ( WaitableTimer )
  {
    DueTime.QuadPart = -4200000000LL;
    SetWaitableTimer(WaitableTimer, &DueTime, 0, 0, 0, 0);
  }
  LeaveCriticalSection(&CriticalSection);
  if ( v0 )
  {
    v2 = operator new(0x28u);
    v3 = v2;
    if ( !v2 )
      goto LABEL_12;
    v2[1] = 1;
    *((_DWORD *)v2 + 5) = 0;
    v2[4] = 0;
    *((_DWORD *)v2 + 4) = -2147418113;
    v2[3] = 0;
    *v2 = &COMXProc::CThreadTaskDelayedShutdown::`vftable';
    if ( (int)CThreadTaskRegister::RegisterWithService((CThreadTaskRegister *)v2) >= 0 && (int)CThreadTask::Run(v3) >= 0 )
      v0 = 0;
    CRefCounted::Release((CRefCounted *)v3);
    if ( v0 )
LABEL_12:
      COMXProc::CThreadTaskDelayedShutdown::s_fInProgress = 0;
  }
}

```

## disassembly

```asm
0x1800293ac  mov     [rsp+arg_8], rbx
0x1800293b1  push    rdi
0x1800293b2  sub     rsp, 30h
0x1800293b6  lea     rcx, CriticalSection; lpCriticalSection
0x1800293bd  xor     edi, edi
0x1800293bf  call    cs:__imp_EnterCriticalSection
0x1800293c5  cmp     cs:?s_fInProgress@CThreadTaskDelayedShutdown@COMXProc@@1HA, edi; int COMXProc::CThreadTaskDelayedShutdown::s_fInProgress
0x1800293cb  jnz     short loc_1800293F8
0x1800293cd  mov     edi, 1
0x1800293d2  mov     cs:?s_fInProgress@CThreadTaskDelayedShutdown@COMXProc@@1HA, 1; int COMXProc::CThreadTaskDelayedShutdown::s_fInProgress
0x1800293dc  mov     r8d, edi; dwFlags
0x1800293df  xor     edx, edx; lpTimerName
0x1800293e1  xor     ecx, ecx; lpTimerAttributes
0x1800293e3  mov     r9d, 1F0003h; dwDesiredAccess
0x1800293e9  call    cs:__imp_CreateWaitableTimerExW
0x1800293ef  mov     cs:?s_hTimer@CThreadTaskDelayedShutdown@COMXProc@@1PEAXEA, rax; void * COMXProc::CThreadTaskDelayedShutdown::s_hTimer
0x1800293f6  jmp     short loc_1800293FF
0x1800293f8  mov     rax, cs:?s_hTimer@CThreadTaskDelayedShutdown@COMXProc@@1PEAXEA; void * COMXProc::CThreadTaskDelayedShutdown::s_hTimer
0x1800293ff  test    rax, rax
0x180029402  jz      short loc_180029438
0x180029404  mov     rdx, 0FFFFFFFF05A91600h
0x18002940e  mov     [rsp+38h+fResume], 0; fResume
0x180029416  mov     qword ptr [rsp+38h+DueTime], rdx
0x18002941b  xor     r9d, r9d; pfnCompletionRoutine
0x18002941e  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x180029423  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18002942c  xor     r8d, r8d; lPeriod
0x18002942f  mov     rcx, rax; hTimer
0x180029432  call    cs:__imp_SetWaitableTimer
0x180029438  lea     rcx, CriticalSection; lpCriticalSection
0x18002943f  call    cs:__imp_LeaveCriticalSection
0x180029445  test    edi, edi
0x180029447  jz      short loc_1800294BC
0x180029449  mov     ecx, 28h ; '('; Size
0x18002944e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029453  mov     rbx, rax
0x180029456  test    rax, rax
0x180029459  jz      short loc_1800294B2
0x18002945b  mov     qword ptr [rax+8], 1
0x180029463  mov     rcx, rbx; this
0x180029466  mov     dword ptr [rax+14h], 0
0x18002946d  mov     qword ptr [rax+20h], 0
0x180029475  mov     dword ptr [rax+10h], 8000FFFFh
0x18002947c  mov     qword ptr [rax+18h], 0
0x180029484  lea     rax, ??_7CThreadTaskDelayedShutdown@COMXProc@@6B@; const COMXProc::CThreadTaskDelayedShutdown::`vftable'
0x18002948b  mov     [rbx], rax
0x18002948e  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x180029493  test    eax, eax
0x180029495  js      short loc_1800294A6
0x180029497  mov     rcx, rbx; Context
0x18002949a  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x18002949f  xor     ecx, ecx
0x1800294a1  test    eax, eax
0x1800294a3  cmovns  edi, ecx
0x1800294a6  mov     rcx, rbx; this
0x1800294a9  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800294ae  test    edi, edi
0x1800294b0  jz      short loc_1800294BC
0x1800294b2  mov     cs:?s_fInProgress@CThreadTaskDelayedShutdown@COMXProc@@1HA, 0; int COMXProc::CThreadTaskDelayedShutdown::s_fInProgress
0x1800294bc  mov     rbx, [rsp+38h+arg_8]
0x1800294c1  add     rsp, 30h
0x1800294c5  pop     rdi
0x1800294c6  retn
```
