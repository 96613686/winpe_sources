# CWLIDTimerQueue::Shutdown(void)

- ea: `0x180019778`
- end: `0x1800198c5`
- name: `?Shutdown@CWLIDTimerQueue@@QEAAXXZ`
- size: `333`
- prototype: `void __fastcall(CWLIDTimerQueue *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019db0`
- `0x180023328`

## callees

- `0x18000c270`
- `0x18000c354`
- `0x18000e870`
- `0x18000e9a4`
- `0x180014cc0`
- `0x180019778`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019853`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001985f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001985f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800197fa`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800197fa`

## string_xrefs

- `0x180019827`: `CWLIDTimerQueue:Shutdown-DeleteTimerQueueEx(m_hTimerQueue) failed with hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWLIDTimerQueue::Shutdown(CWLIDTimerQueue *this)
{
  void *v2; // rbx
  signed int v3; // eax
  void *v4; // rcx
  DWORD v5; // ebx
  signed int LastError; // eax
  int v7; // r8d
  const unsigned __int16 *v8; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v9; // [rsp+20h] [rbp-38h]
  signed int v10; // [rsp+28h] [rbp-30h]
  _BYTE v11[16]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v12[24]; // [rsp+40h] [rbp-18h] BYREF

  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
    "CWLIDTimerQueue::Shutdown",
    (const char *)0x161,
    0,
    v8);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v12,
    (__int64)this + 8,
    1);
  if ( *((_QWORD *)this + 6) )
  {
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v11,
      (__int64)this + 80,
      1);
    v2 = (void *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = 0;
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v11);
    if ( DeleteTimerQueueEx(v2, *((HANDLE *)this + 7)) || GetLastError() == 997 )
    {
      v4 = (void *)*((_QWORD *)this + 7);
      if ( v4 )
      {
        v5 = WaitForSingleObject(v4, 0xFFFFFFFF);
        if ( v5 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v10 = LastError;
          LODWORD(v9) = v5;
          TracePrintW(
            2u,
            "onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
            0x17Eu,
            L"CWLIDTimerQueue:Shutdown-WaitForSingleObject dwWaitResult = %d, hr=0x%x",
            v9,
            v10);
        }
      }
    }
    else
    {
      v3 = GetLastError();
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      LODWORD(v9) = v3;
      TracePrintW(
        2u,
        "onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
        0x174u,
        L"CWLIDTimerQueue:Shutdown-DeleteTimerQueueEx(m_hTimerQueue) failed with hr=0x%x",
        v9);
    }
    Auto<void *,HandleFunctor,IWinApiLite>::Clear((char *)this + 56);
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v12);
  MsaTracingInternal::TraceFunctionExit((MsaTracingInternal *)"CWLIDTimerQueue::Shutdown", 0, v7);
}

```

## disassembly

```asm
0x180019778  mov     [rsp+arg_8], rbx
0x18001977d  mov     [rsp+arg_10], rbp
0x180019782  push    rdi
0x180019783  sub     rsp, 50h
0x180019787  mov     rdi, rcx
0x18001978a  lea     rbp, aCwlidtimerqueu; "CWLIDTimerQueue::Shutdown"
0x180019791  mov     [rsp+58h+arg_0], rbp
0x180019796  xor     r9d, r9d; unsigned int
0x180019799  mov     r8d, 161h; char *
0x18001979f  mov     rdx, rbp; char *
0x1800197a2  lea     rcx, aOnecoreuapRest_1; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x1800197a9  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800197ae  nop
0x1800197af  lea     rdx, [rdi+8]
0x1800197b3  mov     r8b, 1
0x1800197b6  lea     rcx, [rsp+58h+var_18]
0x1800197bb  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x1800197c0  nop
0x1800197c1  cmp     qword ptr [rdi+30h], 0
0x1800197c6  jz      loc_1800198A1
0x1800197cc  lea     rdx, [rdi+50h]
0x1800197d0  mov     r8b, 1
0x1800197d3  lea     rcx, [rsp+58h+var_28]
0x1800197d8  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x1800197dd  mov     rbx, [rdi+30h]
0x1800197e1  mov     qword ptr [rdi+30h], 0
0x1800197e9  lea     rcx, [rsp+58h+var_28]
0x1800197ee  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800197f3  mov     rdx, [rdi+38h]; CompletionEvent
0x1800197f7  mov     rcx, rbx; TimerQueue
0x1800197fa  call    cs:__imp_DeleteTimerQueueEx
0x180019800  test    eax, eax
0x180019802  jnz     short loc_180019847
0x180019804  call    cs:__imp_GetLastError
0x18001980a  cmp     eax, 3E5h
0x18001980f  jz      short loc_180019847
0x180019811  call    cs:__imp_GetLastError
0x180019817  test    eax, eax
0x180019819  jle     short loc_180019823
0x18001981b  movzx   eax, ax
0x18001981e  or      eax, 80070000h
0x180019823  mov     dword ptr [rsp+58h+var_38], eax
0x180019827  lea     r9, aCwlidtimerqueu_0; "CWLIDTimerQueue:Shutdown-DeleteTimerQue"...
0x18001982e  mov     r8d, 174h; unsigned int
0x180019834  lea     rdx, aOnecoreuapRest_1; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18001983b  mov     ecx, 2; unsigned __int8
0x180019840  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180019845  jmp     short loc_180019897
0x180019847  mov     rcx, [rdi+38h]; hHandle
0x18001984b  test    rcx, rcx
0x18001984e  jz      short loc_180019897
0x180019850  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019853  call    cs:__imp_WaitForSingleObject
0x180019859  mov     ebx, eax
0x18001985b  test    eax, eax
0x18001985d  jz      short loc_180019897
0x18001985f  call    cs:__imp_GetLastError
0x180019865  test    eax, eax
0x180019867  jle     short loc_180019871
0x180019869  movzx   eax, ax
0x18001986c  or      eax, 80070000h
0x180019871  mov     [rsp+58h+var_30], eax
0x180019875  mov     dword ptr [rsp+58h+var_38], ebx
0x180019879  lea     r9, aCwlidtimerqueu_5; "CWLIDTimerQueue:Shutdown-WaitForSingleO"...
0x180019880  mov     r8d, 17Eh; unsigned int
0x180019886  lea     rdx, aOnecoreuapRest_1; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18001988d  mov     ecx, 2; unsigned __int8
0x180019892  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180019897  lea     rcx, [rdi+38h]
0x18001989b  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x1800198a0  nop
0x1800198a1  lea     rcx, [rsp+58h+var_18]
0x1800198a6  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800198ab  nop
0x1800198ac  xor     edx, edx; char *
0x1800198ae  mov     rcx, rbp; this
0x1800198b1  mov     rbx, [rsp+58h+arg_8]
0x1800198b6  mov     rbp, [rsp+58h+arg_10]
0x1800198bb  add     rsp, 50h
0x1800198bf  pop     rdi
0x1800198c0  jmp     ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
```
