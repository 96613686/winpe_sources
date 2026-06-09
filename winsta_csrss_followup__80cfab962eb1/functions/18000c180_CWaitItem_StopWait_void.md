# CWaitItem::StopWait(void)

- ea: `0x18000c180`
- end: `0x18000c46f`
- name: `?StopWait@CWaitItem@@QEAAJXZ`
- size: `751`
- prototype: `__int64 __fastcall(CWaitItem *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000129c`
- `0x18000b7f8`
- `0x18000c060`
- `0x18000d2ac`
- `0x18000d360`
- `0x180010490`

## callees

- `0x180005b40`
- `0x18000c180`
- `0x18000c478`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x18000c439`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c439`
- `ntdll!NtQuerySystemTime` at `0x18000c2a0`
- `ntdll!NtQuerySystemTime` at `0x18000c2a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c30f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c30f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c212`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003337e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003337e`
- `RPCRT4!NdrClientCall3` at `0x18000c345`
- `RPCRT4!NdrClientCall3` at `0x18000c36f`
- `RPCRT4!NdrClientCall3` at `0x18000c345`
- `RPCRT4!NdrClientCall3` at `0x18000c36f`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000c253`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000c253`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x18000c233`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x18000c233`

## string_xrefs

- `0x18000c459`: `Loader lock held or DLL is getting unloaded failed: 0x%x in %s`

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
      v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800350F0, 2u, 0, v11).Pointer;
      Pointer = (unsigned int)v12.Pointer;
      BackTraceHash.Pointer = v12.Pointer;
    }
    else
    {
      v16.Simple = 0;
      v16.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800352C0, 3u, 0, v11).Pointer;
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
0x18000c180  push    rbx
0x18000c182  push    rsi
0x18000c183  push    rdi
0x18000c184  push    r12
0x18000c186  push    r13
0x18000c188  push    r14
0x18000c18a  push    r15
0x18000c18c  sub     rsp, 30h
0x18000c190  mov     rdi, rcx
0x18000c193  mov     rax, gs:60h
0x18000c19c  mov     rax, [rax+110h]
0x18000c1a3  mov     rcx, gs:30h
0x18000c1ac  mov     rax, [rax+10h]
0x18000c1b0  cmp     [rcx+48h], rax
0x18000c1b4  jz      loc_18000C44A
0x18000c1ba  mov     rax, gs:60h
0x18000c1c3  mov     rcx, [rax+18h]
0x18000c1c7  cmp     byte ptr [rcx+48h], 0
0x18000c1cb  jnz     loc_18000C44A
0x18000c1d1  lea     rsi, [rdi+50h]
0x18000c1d5  mov     [rsp+68h+var_40], rsi
0x18000c1da  cmp     qword ptr [rsi], 0
0x18000c1de  jz      loc_18000C41E
0x18000c1e4  mov     ebx, 80004001h
0x18000c1e9  xor     r13b, r13b
0x18000c1ec  call    cs:__imp_GetLastError
0x18000c1f3  nop     dword ptr [rax+rax+00h]
0x18000c1f8  mov     r12d, eax
0x18000c1fb  mov     [rsp+68h+arg_10], eax
0x18000c202  cmp     dword ptr [rdi+608h], 0
0x18000c209  jz      short loc_18000C21E
0x18000c20b  lea     rcx, [rdi+5E0h]; lpCriticalSection
0x18000c212  call    cs:__imp_EnterCriticalSection
0x18000c219  nop     dword ptr [rax+rax+00h]
0x18000c21e  lea     r14, [rdi+0C8h]
0x18000c225  cmp     dword ptr [r14], 2
0x18000c229  jnz     loc_18000C3FA
0x18000c22f  lea     rcx, [rdi+58h]; pAsync
0x18000c233  call    cs:__imp_RpcAsyncGetCallStatus
0x18000c23a  nop     dword ptr [rax+rax+00h]
0x18000c23f  cmp     eax, 3E5h
0x18000c244  jnz     loc_18000C3E6
0x18000c24a  mov     edx, 1; fAbort
0x18000c24f  lea     rcx, [rdi+58h]; pAsync
0x18000c253  call    cs:__imp_RpcAsyncCancelCall
0x18000c25a  nop     dword ptr [rax+rax+00h]
0x18000c25f  test    eax, eax
0x18000c261  jnz     short loc_18000C26D
0x18000c263  cmp     dword ptr [r14], 4
0x18000c267  jnz     loc_18000C40C
0x18000c26d  mov     r8d, eax
0x18000c270  lea     rdx, aRpcasynccancel_0; "RpcAsyncCancelCall() failed: status=%#x"
0x18000c277  mov     ecx, 4; int
0x18000c27c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c281  mov     eax, 1
0x18000c286  lock xadd [r14+4], eax
0x18000c28c  inc     eax
0x18000c28e  and     eax, 0Fh
0x18000c291  lea     r13, [rax+rax*4]
0x18000c295  shl     r13, 4
0x18000c299  add     r13, r14
0x18000c29c  lea     rcx, [r13+10h]; SystemTime
0x18000c2a0  call    cs:__imp_NtQuerySystemTime
0x18000c2a7  nop     dword ptr [rax+rax+00h]
0x18000c2ac  mov     dword ptr [rsp+68h+BackTraceHash], 0
0x18000c2b4  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18000c2bb  jz      loc_18000C426
0x18000c2c1  mov     eax, [r14]
0x18000c2c4  mov     [r13+8], eax
0x18000c2c8  mov     dword ptr [r14], 4
0x18000c2cf  mov     dword ptr [r13+0Ch], 4
0x18000c2d7  mov     r13b, 1
0x18000c2da  xor     r14d, r14d
0x18000c2dd  cmp     [rdi+608h], r14d
0x18000c2e4  jz      short loc_18000C2F9
0x18000c2e6  lea     rcx, [rdi+5E0h]; lpCriticalSection
0x18000c2ed  call    cs:__imp_LeaveCriticalSection
0x18000c2f4  nop     dword ptr [rax+rax+00h]
0x18000c2f9  test    r13b, r13b
0x18000c2fc  jz      short loc_18000C31B
0x18000c2fe  mov     rcx, [rdi+5D8h]; hHandle
0x18000c305  test    rcx, rcx
0x18000c308  jz      short loc_18000C31B
0x18000c30a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000c30f  call    cs:__imp_WaitForSingleObject
0x18000c316  nop     dword ptr [rax+rax+00h]
0x18000c31b  cmp     qword ptr [rsi], 0
0x18000c31f  jz      loc_18000C3C4
0x18000c325  mov     r9, rsi
0x18000c328  xor     r8d, r8d; pReturnValue
0x18000c32b  cmp     [rdi+60Ch], r8d
0x18000c332  jz      short loc_18000C35B
0x18000c334  mov     [rsp+68h+BackTraceHash], r14
0x18000c339  mov     edx, 2; nProcNum
0x18000c33e  lea     rcx, stru_1800350F0; pProxyInfo
0x18000c345  call    cs:__imp_NdrClientCall3
0x18000c34c  nop     dword ptr [rax+rax+00h]
0x18000c351  mov     rbx, rax
0x18000c354  mov     [rsp+68h+BackTraceHash], rax
0x18000c359  jmp     short loc_18000C385
0x18000c35b  mov     [rsp+68h+arg_18], r14
0x18000c363  mov     edx, 3; nProcNum
0x18000c368  lea     rcx, stru_1800352C0; pProxyInfo
0x18000c36f  call    cs:__imp_NdrClientCall3
0x18000c376  nop     dword ptr [rax+rax+00h]
0x18000c37b  mov     [rsp+68h+arg_18], rax
0x18000c383  mov     ebx, eax
0x18000c385  mov     [rsp+68h+var_48], eax
0x18000c389  jmp     short loc_18000C3C1
0x18000c38b  test    eax, eax
0x18000c38d  jle     short loc_18000C397
0x18000c38f  movzx   eax, ax
0x18000c392  or      eax, 80070000h
0x18000c397  mov     ebx, eax
0x18000c399  mov     [rsp+68h+var_48], eax
0x18000c39d  mov     r8d, eax
0x18000c3a0  lea     rdx, aRpcunregistera; "RpcUnRegisterAsyncNotification threw an"...
0x18000c3a7  mov     ecx, 8; int
0x18000c3ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c3b1  xor     r14d, r14d
0x18000c3b4  mov     r12d, [rsp+68h+arg_10]
0x18000c3bc  mov     rsi, [rsp+68h+var_40]
0x18000c3c1  mov     [rsi], r14
0x18000c3c4  mov     ecx, r12d; dwErrCode
0x18000c3c7  call    cs:__imp_SetLastError
0x18000c3ce  nop     dword ptr [rax+rax+00h]
0x18000c3d3  mov     eax, ebx
0x18000c3d5  add     rsp, 30h
0x18000c3d9  pop     r15
0x18000c3db  pop     r14
0x18000c3dd  pop     r13
0x18000c3df  pop     r12
0x18000c3e1  pop     rdi
0x18000c3e2  pop     rsi
0x18000c3e3  pop     rbx
0x18000c3e4  retn
0x18000c3e6  mov     r8d, eax
0x18000c3e9  lea     rdx, aCwaititemStopw; "CWaitItem::StopWait(): myStatus=CallPen"...
0x18000c3f0  mov     ecx, 4; int
0x18000c3f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c3fa  mov     edx, 4
0x18000c3ff  mov     rcx, r14
0x18000c402  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000c407  jmp     loc_18000C2DA
0x18000c40c  mov     edx, 3
0x18000c411  mov     rcx, r14
0x18000c414  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000c419  jmp     loc_18000C2D7
0x18000c41e  xor     r14d, r14d
0x18000c421  mov     ebx, r14d
0x18000c424  jmp     short loc_18000C3D3
0x18000c426  lea     r8, [r13+18h]; BackTrace
0x18000c42a  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x18000c42f  mov     edx, 8; FramesToCapture
0x18000c434  mov     ecx, 1; FramesToSkip
0x18000c439  call    cs:__imp_RtlCaptureStackBackTrace
0x18000c440  nop     dword ptr [rax+rax+00h]
0x18000c445  jmp     loc_18000C2C1
0x18000c44a  mov     ebx, 80004005h
0x18000c44f  lea     r9, aCwaititemStopw_0; "CWaitItem::StopWait"
0x18000c456  mov     r8d, ebx
0x18000c459  lea     rdx, aLoaderLockHeld; "Loader lock held or DLL is getting unlo"...
0x18000c460  mov     ecx, 8; int
0x18000c465  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c46a  jmp     loc_18000C3D3
0x180033370  push    rbp
0x180033372  sub     rsp, 20h
0x180033376  mov     rbp, rdx
0x180033379  mov     rcx, [rcx]
0x18003337c  mov     ecx, [rcx]; ExceptionCode
0x18003337e  call    cs:__imp_I_RpcExceptionFilter
0x180033385  nop     dword ptr [rax+rax+00h]
0x18003338a  nop
0x18003338b  add     rsp, 20h
0x18003338f  pop     rbp
0x180033390  retn
```
