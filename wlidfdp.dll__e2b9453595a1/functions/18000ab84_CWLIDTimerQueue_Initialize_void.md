# CWLIDTimerQueue::Initialize(void)

- ea: `0x18000ab84`
- end: `0x18000ac55`
- name: `?Initialize@CWLIDTimerQueue@@QEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(CWLIDTimerQueue *this, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007b00`

## callees

- `0x180003700`
- `0x18000505c`
- `0x1800054dc`
- `0x180008edc`
- `0x18000a310`
- `0x18000ab84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000abf6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000abf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac20`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000ac11`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000ac11`

## pseudocode

```c
__int64 __fastcall CWLIDTimerQueue::Initialize(CWLIDTimerQueue *this, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rdx
  int v6; // r8d
  HANDLE EventW; // rbx
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v12[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v13[5]; // [rsp+30h] [rbp-28h] BYREF
  signed int v14; // [rsp+80h] [rbp+28h] BYREF

  v14 = 0;
  v13[0] = "CWLIDTimerQueue::Initialize";
  v13[1] = &v14;
  v13[2] = 0;
  v13[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
    "CWLIDTimerQueue::Initialize",
    (const char *)0xB7,
    a4,
    v12[0]);
  if ( !*((_QWORD *)this + 6) )
  {
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v12,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 8));
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
        v14 = LastError;
      }
    }
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v12);
  }
  v10 = v14;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v13, v5, v6);
  return v10;
}

```

## disassembly

```asm
0x18000ab84  push    rbp
0x18000ab86  push    rbx
0x18000ab87  push    rsi
0x18000ab88  push    rdi
0x18000ab89  mov     rbp, rsp
0x18000ab8c  sub     rsp, 58h
0x18000ab90  mov     rsi, rcx
0x18000ab93  mov     [rbp+arg_0], 0
0x18000ab9a  lea     rdx, aCwlidtimerqueu_2; "CWLIDTimerQueue::Initialize"
0x18000aba1  mov     [rbp+var_28], rdx
0x18000aba5  lea     rax, [rbp+arg_0]
0x18000aba9  mov     [rbp+var_20], rax
0x18000abad  mov     [rbp+var_18], 0
0x18000abb5  mov     [rbp+var_10], 0
0x18000abbd  mov     r8d, 0B7h; char *
0x18000abc3  lea     rcx, aOnecoreuapRest_0; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000abca  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000abcf  nop
0x18000abd0  cmp     qword ptr [rsi+30h], 0
0x18000abd5  jnz     short loc_18000AC3E
0x18000abd7  lea     rdx, [rsi+8]
0x18000abdb  lea     rcx, [rbp+var_38]
0x18000abdf  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18000abe4  nop
0x18000abe5  cmp     qword ptr [rsi+30h], 0
0x18000abea  jnz     short loc_18000AC35
0x18000abec  xor     r9d, r9d; lpName
0x18000abef  xor     r8d, r8d; bInitialState
0x18000abf2  xor     edx, edx; bManualReset
0x18000abf4  xor     ecx, ecx; lpEventAttributes
0x18000abf6  call    cs:__imp_CreateEventW
0x18000abfc  mov     rbx, rax
0x18000abff  lea     rcx, [rsi+38h]
0x18000ac03  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x18000ac08  mov     [rsi+38h], rbx
0x18000ac0c  test    rbx, rbx
0x18000ac0f  jz      short loc_18000AC20
0x18000ac11  call    cs:__imp_CreateTimerQueue
0x18000ac17  mov     [rsi+30h], rax
0x18000ac1b  test    rax, rax
0x18000ac1e  jnz     short loc_18000AC35
0x18000ac20  call    cs:__imp_GetLastError
0x18000ac26  test    eax, eax
0x18000ac28  jle     short loc_18000AC32
0x18000ac2a  movzx   eax, ax
0x18000ac2d  or      eax, 80070000h
0x18000ac32  mov     [rbp+arg_0], eax
0x18000ac35  lea     rcx, [rbp+var_38]
0x18000ac39  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18000ac3e  mov     ebx, [rbp+arg_0]
0x18000ac41  lea     rcx, [rbp+var_28]
0x18000ac45  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000ac4a  mov     eax, ebx
0x18000ac4c  add     rsp, 58h
0x18000ac50  pop     rdi
0x18000ac51  pop     rsi
0x18000ac52  pop     rbx
0x18000ac53  pop     rbp
0x18000ac54  retn
```
