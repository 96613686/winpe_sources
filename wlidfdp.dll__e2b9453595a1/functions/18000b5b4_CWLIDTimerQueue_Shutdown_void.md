# CWLIDTimerQueue::Shutdown(void)

- ea: `0x18000b5b4`
- end: `0x18000b6f8`
- name: `?Shutdown@CWLIDTimerQueue@@QEAAXXZ`
- size: `324`
- prototype: `void __fastcall(CWLIDTimerQueue *this, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009f44`
- `0x18000bbf8`

## callees

- `0x180003700`
- `0x18000505c`
- `0x180008edc`
- `0x180008f6c`
- `0x18000a310`
- `0x18000b5b4`
- `0x18000f4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b686`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b692`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000b62d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000b62d`

## string_xrefs

- `0x18000b65a`: `CWLIDTimerQueue:Shutdown-DeleteTimerQueueEx(m_hTimerQueue) failed with hr=0x%x`

## pseudocode

```c
void __fastcall CWLIDTimerQueue::Shutdown(CWLIDTimerQueue *this, __int64 a2, __int64 a3, unsigned int a4)
{
  void *v5; // rbx
  signed int v6; // eax
  void *v7; // rcx
  DWORD v8; // ebx
  signed int LastError; // eax
  int v10; // r8d
  const unsigned __int16 *v11; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v12; // [rsp+20h] [rbp-38h]
  signed int v13; // [rsp+28h] [rbp-30h]
  _BYTE v14[16]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v15[24]; // [rsp+40h] [rbp-18h] BYREF

  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
    "CWLIDTimerQueue::Shutdown",
    (const char *)0x161,
    a4,
    v11);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v15,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 8));
  if ( *((_QWORD *)this + 6) )
  {
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v14,
      (struct _RTL_CRITICAL_SECTION *)this + 2);
    v5 = (void *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = 0;
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v14);
    if ( DeleteTimerQueueEx(v5, *((HANDLE *)this + 7)) || GetLastError() == 997 )
    {
      v7 = (void *)*((_QWORD *)this + 7);
      if ( v7 )
      {
        v8 = WaitForSingleObject(v7, 0xFFFFFFFF);
        if ( v8 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v13 = LastError;
          LODWORD(v12) = v8;
          TracePrintW(
            2u,
            "onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
            0x17Eu,
            L"CWLIDTimerQueue:Shutdown-WaitForSingleObject dwWaitResult = %d, hr=0x%x",
            v12,
            v13);
        }
      }
    }
    else
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      LODWORD(v12) = v6;
      TracePrintW(
        2u,
        "onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
        0x174u,
        L"CWLIDTimerQueue:Shutdown-DeleteTimerQueueEx(m_hTimerQueue) failed with hr=0x%x",
        v12);
    }
    Auto<void *,HandleFunctor,IWinApiLite>::Clear((char *)this + 56);
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v15);
  MsaTracingInternal::TraceFunctionExit((MsaTracingInternal *)"CWLIDTimerQueue::Shutdown", 0, v10);
}

```

## disassembly

```asm
0x18000b5b4  mov     [rsp+arg_8], rbx
0x18000b5b9  mov     [rsp+arg_10], rsi
0x18000b5be  push    rdi
0x18000b5bf  sub     rsp, 50h
0x18000b5c3  mov     rdi, rcx
0x18000b5c6  lea     rsi, aCwlidtimerqueu; "CWLIDTimerQueue::Shutdown"
0x18000b5cd  mov     [rsp+58h+arg_0], rsi
0x18000b5d2  mov     r8d, 161h; char *
0x18000b5d8  mov     rdx, rsi; char *
0x18000b5db  lea     rcx, aOnecoreuapRest_0; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000b5e2  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000b5e7  nop
0x18000b5e8  lea     rdx, [rdi+8]
0x18000b5ec  lea     rcx, [rsp+58h+var_18]
0x18000b5f1  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18000b5f6  nop
0x18000b5f7  cmp     qword ptr [rdi+30h], 0
0x18000b5fc  jz      loc_18000B6D4
0x18000b602  lea     rdx, [rdi+50h]
0x18000b606  lea     rcx, [rsp+58h+var_28]
0x18000b60b  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18000b610  mov     rbx, [rdi+30h]
0x18000b614  mov     qword ptr [rdi+30h], 0
0x18000b61c  lea     rcx, [rsp+58h+var_28]
0x18000b621  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18000b626  mov     rdx, [rdi+38h]; CompletionEvent
0x18000b62a  mov     rcx, rbx; TimerQueue
0x18000b62d  call    cs:__imp_DeleteTimerQueueEx
0x18000b633  test    eax, eax
0x18000b635  jnz     short loc_18000B67A
0x18000b637  call    cs:__imp_GetLastError
0x18000b63d  cmp     eax, 3E5h
0x18000b642  jz      short loc_18000B67A
0x18000b644  call    cs:__imp_GetLastError
0x18000b64a  test    eax, eax
0x18000b64c  jle     short loc_18000B656
0x18000b64e  movzx   eax, ax
0x18000b651  or      eax, 80070000h
0x18000b656  mov     dword ptr [rsp+58h+var_38], eax
0x18000b65a  lea     r9, aCwlidtimerqueu_0; "CWLIDTimerQueue:Shutdown-DeleteTimerQue"...
0x18000b661  mov     r8d, 174h; unsigned int
0x18000b667  lea     rdx, aOnecoreuapRest_0; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000b66e  mov     ecx, 2; unsigned __int8
0x18000b673  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b678  jmp     short loc_18000B6CA
0x18000b67a  mov     rcx, [rdi+38h]; hHandle
0x18000b67e  test    rcx, rcx
0x18000b681  jz      short loc_18000B6CA
0x18000b683  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b686  call    cs:__imp_WaitForSingleObject
0x18000b68c  mov     ebx, eax
0x18000b68e  test    eax, eax
0x18000b690  jz      short loc_18000B6CA
0x18000b692  call    cs:__imp_GetLastError
0x18000b698  test    eax, eax
0x18000b69a  jle     short loc_18000B6A4
0x18000b69c  movzx   eax, ax
0x18000b69f  or      eax, 80070000h
0x18000b6a4  mov     [rsp+58h+var_30], eax
0x18000b6a8  mov     dword ptr [rsp+58h+var_38], ebx
0x18000b6ac  lea     r9, aCwlidtimerqueu_5; "CWLIDTimerQueue:Shutdown-WaitForSingleO"...
0x18000b6b3  mov     r8d, 17Eh; unsigned int
0x18000b6b9  lea     rdx, aOnecoreuapRest_0; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000b6c0  mov     ecx, 2; unsigned __int8
0x18000b6c5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b6ca  lea     rcx, [rdi+38h]
0x18000b6ce  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x18000b6d3  nop
0x18000b6d4  lea     rcx, [rsp+58h+var_18]
0x18000b6d9  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18000b6de  nop
0x18000b6df  xor     edx, edx; char *
0x18000b6e1  mov     rcx, rsi; this
0x18000b6e4  mov     rbx, [rsp+58h+arg_8]
0x18000b6e9  mov     rsi, [rsp+58h+arg_10]
0x18000b6ee  add     rsp, 50h
0x18000b6f2  pop     rdi
0x18000b6f3  jmp     ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
```
