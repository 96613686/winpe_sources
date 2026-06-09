# CWaitItem::StopWait(void)

- ea: `0x1800023a0`
- end: `0x18000264c`
- name: `?StopWait@CWaitItem@@QEAAJXZ`
- size: `684`
- prototype: `__int64 __fastcall(CWaitItem *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800011c0`
- `0x18000159c`
- `0x18000171c`
- `0x180001a98`
- `0x180002290`
- `0x18000f950`

## callees

- `0x1800023a0`
- `0x180002654`
- `0x180007890`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x18000261c`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000261c`
- `ntdll!NtQuerySystemTime` at `0x1800024a8`
- `ntdll!NtQuerySystemTime` at `0x1800024a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000240c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000240c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000250b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000250b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000242c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000242c`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002ff8e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002ff8e`
- `RPCRT4!NdrClientCall3` at `0x18000253b`
- `RPCRT4!NdrClientCall3` at `0x18000255f`
- `RPCRT4!NdrClientCall3` at `0x18000253b`
- `RPCRT4!NdrClientCall3` at `0x18000255f`
- `RPCRT4!RpcAsyncCancelCall` at `0x180002461`
- `RPCRT4!RpcAsyncCancelCall` at `0x180002461`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180002447`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180002447`

## string_xrefs

- `0x180002636`: `Loader lock held or DLL is getting unloaded failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CWaitItem::StopWait(CWaitItem *this)
{
  _QWORD *v2; // rsi
  unsigned int Pointer; // ebx
  char v4; // r13
  DWORD LastError; // r12d
  _DWORD *v6; // r14
  RPC_STATUS v7; // eax
  RPC_STATUS v8; // eax
  _DWORD *v9; // r13
  void *v10; // rcx
  char *v11; // r9
  CLIENT_CALL_RETURN v12; // rax
  CLIENT_CALL_RETURN BackTraceHash; // [rsp+78h] [rbp+10h] BYREF
  DWORD v15; // [rsp+80h] [rbp+18h]
  CLIENT_CALL_RETURN v16; // [rsp+88h] [rbp+20h]

  if ( NtCurrentTeb()->ClientId.UniqueThread == NtCurrentPeb()->LoaderLock->OwningThread
    || NtCurrentPeb()->Ldr->ShutdownInProgress )
  {
    Pointer = -2147467259;
    _DbgPrintMessage(
      8,
      "Loader lock held or DLL is getting unloaded failed: 0x%x in %s",
      -2147467259,
      "CWaitItem::StopWait");
    return Pointer;
  }
  v2 = (_QWORD *)((char *)this + 80);
  if ( !*((_QWORD *)this + 10) )
    return 0;
  Pointer = -2147467263;
  v4 = 0;
  LastError = GetLastError();
  v15 = LastError;
  if ( *((_DWORD *)this + 386) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
  v6 = (_DWORD *)((char *)this + 200);
  if ( *((_DWORD *)this + 50) == 2 )
  {
    v7 = RpcAsyncGetCallStatus((PRPC_ASYNC_STATE)((char *)this + 88));
    if ( v7 == 997 )
    {
      v8 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 88), 1);
      if ( v8 || *v6 == 4 )
      {
        _DbgPrintMessage(4, "RpcAsyncCancelCall() failed: status=%#x", v8);
        v9 = &v6[20 * (((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)this + 51, 1u) + 1) & 0xF)];
        NtQuerySystemTime((PLARGE_INTEGER)v9 + 2);
        LODWORD(BackTraceHash.Pointer) = 0;
        if ( g_bCaptureObjectStackTrace == 1 )
          RtlCaptureStackBackTrace(1u, 8u, (PVOID *)v9 + 3, (PULONG)&BackTraceHash);
        v9[2] = *v6;
        *v6 = 4;
        v9[3] = 4;
      }
      else
      {
        StateTracker<enum CWaitItem::WaitItemCallState>::operator=((char *)this + 200, 3);
      }
      v4 = 1;
      goto LABEL_14;
    }
    _DbgPrintMessage(4, "CWaitItem::StopWait(): myStatus=CallPending; but RpcStatus is %#x", v7);
  }
  StateTracker<enum CWaitItem::WaitItemCallState>::operator=((char *)this + 200, 4);
LABEL_14:
  if ( *((_DWORD *)this + 386) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
  if ( v4 )
  {
    v10 = (void *)*((_QWORD *)this + 187);
    if ( v10 )
      WaitForSingleObject(v10, 0xFFFFFFFF);
  }
  if ( *v2 )
  {
    v11 = (char *)this + 80;
    if ( *((_DWORD *)this + 387) )
    {
      BackTraceHash.Simple = 0;
      v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032018, 2u, 0, v11).Pointer;
      Pointer = (unsigned int)v12.Pointer;
      BackTraceHash.Pointer = v12.Pointer;
    }
    else
    {
      v16.Simple = 0;
      v16.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, v11).Pointer;
      Pointer = (unsigned int)v16.Pointer;
    }
    *v2 = 0;
  }
  SetLastError(LastError);
  return Pointer;
}

```

## disassembly

```asm
0x1800023a0  push    rbx
0x1800023a2  push    rsi
0x1800023a3  push    rdi
0x1800023a4  push    r12
0x1800023a6  push    r13
0x1800023a8  push    r14
0x1800023aa  push    r15
0x1800023ac  sub     rsp, 30h
0x1800023b0  mov     rdi, rcx
0x1800023b3  mov     rax, gs:60h
0x1800023bc  mov     rax, [rax+110h]
0x1800023c3  mov     rcx, gs:30h
0x1800023cc  mov     rax, [rax+10h]
0x1800023d0  cmp     [rcx+48h], rax
0x1800023d4  jz      loc_180002627
0x1800023da  mov     rax, gs:60h
0x1800023e3  mov     rcx, [rax+18h]
0x1800023e7  cmp     byte ptr [rcx+48h], 0
0x1800023eb  jnz     loc_180002627
0x1800023f1  lea     rsi, [rdi+50h]
0x1800023f5  mov     [rsp+68h+var_40], rsi
0x1800023fa  cmp     qword ptr [rsi], 0
0x1800023fe  jz      loc_180002601
0x180002404  mov     ebx, 80004001h
0x180002409  xor     r13b, r13b
0x18000240c  call    cs:__imp_GetLastError
0x180002412  mov     r12d, eax
0x180002415  mov     [rsp+68h+arg_10], eax
0x18000241c  cmp     dword ptr [rdi+608h], 0
0x180002423  jz      short loc_180002432
0x180002425  lea     rcx, [rdi+5E0h]; lpCriticalSection
0x18000242c  call    cs:__imp_EnterCriticalSection
0x180002432  lea     r14, [rdi+0C8h]
0x180002439  cmp     dword ptr [r14], 2
0x18000243d  jnz     loc_1800025DD
0x180002443  lea     rcx, [rdi+58h]; pAsync
0x180002447  call    cs:__imp_RpcAsyncGetCallStatus
0x18000244d  cmp     eax, 3E5h
0x180002452  jnz     loc_1800025C9
0x180002458  mov     edx, 1; fAbort
0x18000245d  lea     rcx, [rdi+58h]; pAsync
0x180002461  call    cs:__imp_RpcAsyncCancelCall
0x180002467  test    eax, eax
0x180002469  jnz     short loc_180002475
0x18000246b  cmp     dword ptr [r14], 4
0x18000246f  jnz     loc_1800025EF
0x180002475  mov     r8d, eax
0x180002478  lea     rdx, aRpcasynccancel_0; "RpcAsyncCancelCall() failed: status=%#x"
0x18000247f  mov     ecx, 4; int
0x180002484  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002489  mov     eax, 1
0x18000248e  lock xadd [r14+4], eax
0x180002494  inc     eax
0x180002496  and     eax, 0Fh
0x180002499  lea     r13, [rax+rax*4]
0x18000249d  shl     r13, 4
0x1800024a1  add     r13, r14
0x1800024a4  lea     rcx, [r13+10h]; SystemTime
0x1800024a8  call    cs:__imp_NtQuerySystemTime
0x1800024ae  mov     dword ptr [rsp+68h+BackTraceHash], 0
0x1800024b6  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x1800024bd  jz      loc_180002609
0x1800024c3  mov     eax, [r14]
0x1800024c6  mov     [r13+8], eax
0x1800024ca  mov     dword ptr [r14], 4
0x1800024d1  mov     dword ptr [r13+0Ch], 4
0x1800024d9  mov     r13b, 1
0x1800024dc  xor     r14d, r14d
0x1800024df  cmp     [rdi+608h], r14d
0x1800024e6  jz      short loc_1800024F5
0x1800024e8  lea     rcx, [rdi+5E0h]; lpCriticalSection
0x1800024ef  call    cs:__imp_LeaveCriticalSection
0x1800024f5  test    r13b, r13b
0x1800024f8  jz      short loc_180002511
0x1800024fa  mov     rcx, [rdi+5D8h]; hHandle
0x180002501  test    rcx, rcx
0x180002504  jz      short loc_180002511
0x180002506  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000250b  call    cs:__imp_WaitForSingleObject
0x180002511  cmp     qword ptr [rsi], 0
0x180002515  jz      loc_1800025AE
0x18000251b  mov     r9, rsi
0x18000251e  xor     r8d, r8d; pReturnValue
0x180002521  cmp     [rdi+60Ch], r8d
0x180002528  jz      short loc_18000254B
0x18000252a  mov     [rsp+68h+BackTraceHash], r14
0x18000252f  mov     edx, 2; nProcNum
0x180002534  lea     rcx, stru_180032018; pProxyInfo
0x18000253b  call    cs:__imp_NdrClientCall3
0x180002541  mov     rbx, rax
0x180002544  mov     [rsp+68h+BackTraceHash], rax
0x180002549  jmp     short loc_18000256F
0x18000254b  mov     [rsp+68h+arg_18], r14
0x180002553  mov     edx, 3; nProcNum
0x180002558  lea     rcx, pProxyInfo; pProxyInfo
0x18000255f  call    cs:__imp_NdrClientCall3
0x180002565  mov     [rsp+68h+arg_18], rax
0x18000256d  mov     ebx, eax
0x18000256f  mov     [rsp+68h+var_48], eax
0x180002573  jmp     short loc_1800025AB
0x180002575  test    eax, eax
0x180002577  jle     short loc_180002581
0x180002579  movzx   eax, ax
0x18000257c  or      eax, 80070000h
0x180002581  mov     ebx, eax
0x180002583  mov     [rsp+68h+var_48], eax
0x180002587  mov     r8d, eax
0x18000258a  lea     rdx, aRpcunregistera; "RpcUnRegisterAsyncNotification threw an"...
0x180002591  mov     ecx, 8; int
0x180002596  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000259b  xor     r14d, r14d
0x18000259e  mov     r12d, [rsp+68h+arg_10]
0x1800025a6  mov     rsi, [rsp+68h+var_40]
0x1800025ab  mov     [rsi], r14
0x1800025ae  mov     ecx, r12d; dwErrCode
0x1800025b1  call    cs:__imp_SetLastError
0x1800025b7  mov     eax, ebx
0x1800025b9  add     rsp, 30h
0x1800025bd  pop     r15
0x1800025bf  pop     r14
0x1800025c1  pop     r13
0x1800025c3  pop     r12
0x1800025c5  pop     rdi
0x1800025c6  pop     rsi
0x1800025c7  pop     rbx
0x1800025c8  retn
0x1800025c9  mov     r8d, eax
0x1800025cc  lea     rdx, aCwaititemStopw; "CWaitItem::StopWait(): myStatus=CallPen"...
0x1800025d3  mov     ecx, 4; int
0x1800025d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800025dd  mov     edx, 4
0x1800025e2  mov     rcx, r14
0x1800025e5  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x1800025ea  jmp     loc_1800024DC
0x1800025ef  mov     edx, 3
0x1800025f4  mov     rcx, r14
0x1800025f7  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x1800025fc  jmp     loc_1800024D9
0x180002601  xor     r14d, r14d
0x180002604  mov     ebx, r14d
0x180002607  jmp     short loc_1800025B7
0x180002609  lea     r8, [r13+18h]; BackTrace
0x18000260d  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x180002612  mov     edx, 8; FramesToCapture
0x180002617  mov     ecx, 1; FramesToSkip
0x18000261c  call    cs:__imp_RtlCaptureStackBackTrace
0x180002622  jmp     loc_1800024C3
0x180002627  mov     ebx, 80004005h
0x18000262c  lea     r9, aCwaititemStopw_0; "CWaitItem::StopWait"
0x180002633  mov     r8d, ebx
0x180002636  lea     rdx, aLoaderLockHeld; "Loader lock held or DLL is getting unlo"...
0x18000263d  mov     ecx, 8; int
0x180002642  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002647  jmp     loc_1800025B7
0x18002ff80  push    rbp
0x18002ff82  sub     rsp, 20h
0x18002ff86  mov     rbp, rdx
0x18002ff89  mov     rcx, [rcx]
0x18002ff8c  mov     ecx, [rcx]; ExceptionCode
0x18002ff8e  call    cs:__imp_I_RpcExceptionFilter
0x18002ff94  nop
0x18002ff95  add     rsp, 20h
0x18002ff99  pop     rbp
0x18002ff9a  retn
```
