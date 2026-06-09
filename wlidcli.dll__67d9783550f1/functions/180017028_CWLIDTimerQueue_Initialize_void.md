# CWLIDTimerQueue::Initialize(void)

- ea: `0x180017028`
- end: `0x1800170ff`
- name: `?Initialize@CWLIDTimerQueue@@QEAAJXZ`
- size: `215`
- prototype: `__int64 __fastcall(CWLIDTimerQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016c74`

## callees

- `0x18000c270`
- `0x18000c354`
- `0x18000cc9c`
- `0x18000e870`
- `0x180014cc0`
- `0x180017028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800170a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800170a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170ca`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800170bb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800170bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWLIDTimerQueue::Initialize(CWLIDTimerQueue *this)
{
  HANDLE EventW; // rbx
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v7[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v8[5]; // [rsp+30h] [rbp-28h] BYREF
  signed int v9; // [rsp+80h] [rbp+28h] BYREF

  v9 = 0;
  v8[0] = "CWLIDTimerQueue::Initialize";
  v8[1] = &v9;
  v8[2] = 0;
  v8[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
    "CWLIDTimerQueue::Initialize",
    (const char *)0xB7,
    0,
    v7[0]);
  if ( !*((_QWORD *)this + 6) )
  {
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v7,
      (__int64)this + 8,
      1);
    if ( !*((_QWORD *)this + 6) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      Auto<void *,HandleFunctor,IWinApiLite>::Clear((char *)this + 56);
      *((_QWORD *)this + 7) = EventW;
      if ( !EventW || (TimerQueue = CreateTimerQueue(), (*((_QWORD *)this + 6) = TimerQueue) == 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = LastError;
      }
    }
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v7);
  }
  v5 = v9;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v8);
  return v5;
}

```

## disassembly

```asm
0x180017028  push    rbp
0x18001702a  push    rbx
0x18001702b  push    rsi
0x18001702c  push    rdi
0x18001702d  mov     rbp, rsp
0x180017030  sub     rsp, 58h
0x180017034  mov     rsi, rcx
0x180017037  mov     [rbp+arg_0], 0
0x18001703e  lea     rdx, aCwlidtimerqueu_2; "CWLIDTimerQueue::Initialize"
0x180017045  mov     [rbp+var_28], rdx
0x180017049  lea     rax, [rbp+arg_0]
0x18001704d  mov     [rbp+var_20], rax
0x180017051  mov     [rbp+var_18], 0
0x180017059  mov     [rbp+var_10], 0
0x180017061  xor     r9d, r9d; unsigned int
0x180017064  mov     r8d, 0B7h; char *
0x18001706a  lea     rcx, aOnecoreuapRest_1; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x180017071  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180017076  nop
0x180017077  cmp     qword ptr [rsi+30h], 0
0x18001707c  jnz     short loc_1800170E8
0x18001707e  lea     rdx, [rsi+8]
0x180017082  mov     r8b, 1
0x180017085  lea     rcx, [rbp+var_38]
0x180017089  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18001708e  nop
0x18001708f  cmp     qword ptr [rsi+30h], 0
0x180017094  jnz     short loc_1800170DF
0x180017096  xor     r9d, r9d; lpName
0x180017099  xor     r8d, r8d; bInitialState
0x18001709c  xor     edx, edx; bManualReset
0x18001709e  xor     ecx, ecx; lpEventAttributes
0x1800170a0  call    cs:__imp_CreateEventW
0x1800170a6  mov     rbx, rax
0x1800170a9  lea     rcx, [rsi+38h]
0x1800170ad  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x1800170b2  mov     [rsi+38h], rbx
0x1800170b6  test    rbx, rbx
0x1800170b9  jz      short loc_1800170CA
0x1800170bb  call    cs:__imp_CreateTimerQueue
0x1800170c1  mov     [rsi+30h], rax
0x1800170c5  test    rax, rax
0x1800170c8  jnz     short loc_1800170DF
0x1800170ca  call    cs:__imp_GetLastError
0x1800170d0  test    eax, eax
0x1800170d2  jle     short loc_1800170DC
0x1800170d4  movzx   eax, ax
0x1800170d7  or      eax, 80070000h
0x1800170dc  mov     [rbp+arg_0], eax
0x1800170df  lea     rcx, [rbp+var_38]
0x1800170e3  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800170e8  mov     ebx, [rbp+arg_0]
0x1800170eb  lea     rcx, [rbp+var_28]
0x1800170ef  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800170f4  mov     eax, ebx
0x1800170f6  add     rsp, 58h
0x1800170fa  pop     rdi
0x1800170fb  pop     rsi
0x1800170fc  pop     rbx
0x1800170fd  pop     rbp
0x1800170fe  retn
```
