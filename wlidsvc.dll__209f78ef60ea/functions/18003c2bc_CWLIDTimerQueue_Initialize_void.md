# CWLIDTimerQueue::Initialize(void)

- ea: `0x18003c2bc`
- end: `0x18003c3b7`
- name: `?Initialize@CWLIDTimerQueue@@QEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(CWLIDTimerQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800bcff0`

## callees

- `0x18001a9c0`
- `0x18001ad00`
- `0x18003c2bc`
- `0x18003c3c0`
- `0x18003c814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c35c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c341`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c374`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c326`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c326`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18003c37c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18003c37c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWLIDTimerQueue::Initialize(CWLIDTimerQueue *this)
{
  HANDLE EventW; // rbx
  signed int LastError; // eax
  HANDLE TimerQueue; // rax
  unsigned int v5; // ebx
  const unsigned __int16 *v7; // [rsp+20h] [rbp-30h] BYREF
  char v8; // [rsp+28h] [rbp-28h]
  _QWORD v9[4]; // [rsp+30h] [rbp-20h] BYREF
  signed int v10; // [rsp+70h] [rbp+20h] BYREF

  v10 = 0;
  v9[0] = "CWLIDTimerQueue::Initialize";
  v9[1] = &v10;
  v9[2] = 0;
  v9[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\Live\\identity\\Include\\TimerQueue.h",
    "CWLIDTimerQueue::Initialize",
    (const char *)0xB7,
    0,
    v7);
  if ( !*((_QWORD *)this + 6) )
  {
    v7 = (const unsigned __int16 *)((char *)this + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v8 = 1;
    if ( *((_QWORD *)this + 6)
      || (EventW = CreateEventW(0, 0, 0, 0),
          Auto<void *,HandleFunctor,IWinApiLite>::Clear((char *)this + 56),
          (*((_QWORD *)this + 7) = EventW) != 0)
      && (TimerQueue = CreateTimerQueue(), (*((_QWORD *)this + 6) = TimerQueue) != 0) )
    {
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v7);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = LastError;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    }
  }
  v5 = v10;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v9);
  return v5;
}

```

## disassembly

```asm
0x18003c2bc  mov     [rsp-18h+arg_8], rbx
0x18003c2c1  mov     [rsp-18h+arg_10], rsi
0x18003c2c6  push    rbp
0x18003c2c7  push    rdi
0x18003c2c8  push    r14
0x18003c2ca  mov     rbp, rsp
0x18003c2cd  sub     rsp, 50h
0x18003c2d1  mov     r14, rcx
0x18003c2d4  mov     [rbp+arg_0], 0
0x18003c2db  lea     rdx, aCwlidtimerqueu_2; "CWLIDTimerQueue::Initialize"
0x18003c2e2  mov     [rbp+var_20], rdx
0x18003c2e6  lea     rax, [rbp+arg_0]
0x18003c2ea  mov     [rbp+var_18], rax
0x18003c2ee  mov     [rbp+var_10], 0
0x18003c2f6  mov     [rbp+var_8], 0
0x18003c2fe  xor     r9d, r9d; unsigned int
0x18003c301  mov     r8d, 0B7h; char *
0x18003c307  lea     rcx, aOnecoreuapDsEx_81; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18003c30e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003c313  nop
0x18003c314  cmp     qword ptr [r14+30h], 0
0x18003c319  jnz     short loc_18003C394
0x18003c31b  lea     rsi, [r14+8]
0x18003c31f  mov     [rbp+var_30], rsi
0x18003c323  mov     rcx, rsi; lpCriticalSection
0x18003c326  call    cs:__imp_EnterCriticalSection
0x18003c32c  mov     [rbp+var_28], 1
0x18003c330  cmp     qword ptr [r14+30h], 0
0x18003c335  jnz     short loc_18003C38B
0x18003c337  xor     r9d, r9d; lpName
0x18003c33a  xor     r8d, r8d; bInitialState
0x18003c33d  xor     edx, edx; bManualReset
0x18003c33f  xor     ecx, ecx; lpEventAttributes
0x18003c341  call    cs:__imp_CreateEventW
0x18003c347  mov     rbx, rax
0x18003c34a  lea     rcx, [r14+38h]
0x18003c34e  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x18003c353  mov     [r14+38h], rbx
0x18003c357  test    rbx, rbx
0x18003c35a  jnz     short loc_18003C37C
0x18003c35c  call    cs:__imp_GetLastError
0x18003c362  test    eax, eax
0x18003c364  jle     short loc_18003C36E
0x18003c366  movzx   eax, ax
0x18003c369  or      eax, 80070000h
0x18003c36e  mov     [rbp+arg_0], eax
0x18003c371  mov     rcx, rsi; lpCriticalSection
0x18003c374  call    cs:__imp_LeaveCriticalSection
0x18003c37a  jmp     short loc_18003C394
0x18003c37c  call    cs:__imp_CreateTimerQueue
0x18003c382  mov     [r14+30h], rax
0x18003c386  test    rax, rax
0x18003c389  jz      short loc_18003C35C
0x18003c38b  lea     rcx, [rbp+var_30]
0x18003c38f  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18003c394  mov     ebx, [rbp+arg_0]
0x18003c397  lea     rcx, [rbp+var_20]
0x18003c39b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003c3a0  mov     eax, ebx
0x18003c3a2  lea     r11, [rsp+50h+var_s0]
0x18003c3a7  mov     rbx, [r11+28h]
0x18003c3ab  mov     rsi, [r11+30h]
0x18003c3af  mov     rsp, r11
0x18003c3b2  pop     r14
0x18003c3b4  pop     rdi
0x18003c3b5  pop     rbp
0x18003c3b6  retn
```
