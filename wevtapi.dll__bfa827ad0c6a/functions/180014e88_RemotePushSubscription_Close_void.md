# RemotePushSubscription::Close(void)

- ea: `0x180014e88`
- end: `0x18001507b`
- name: `?Close@RemotePushSubscription@@AEAAXXZ`
- size: `499`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180014e70`
- `0x180029270`

## callees

- `0x180014b90`
- `0x180014e88`
- `0x1800158d4`
- `0x180023548`
- `0x180029294`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014ee2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014ee2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014eb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014fc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014eb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014fc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014ed1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015030`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014ed1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001500a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001500a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180014fe8`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180014fe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e9c`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180014f29`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x180014f29`
- `RPCRT4!RpcAsyncCancelCall` at `0x180014f3c`
- `RPCRT4!RpcAsyncCancelCall` at `0x180014f3c`

## pseudocode

```c
void __fastcall RemotePushSubscription::Close(char *pv)
{
  int v2; // ebx
  char v3; // bl
  struct _TP_WAIT *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  DWORD LastError; // eax

  v2 = *((_DWORD *)pv + 85);
  if ( GetCurrentThreadId() == v2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids);
    }
    AcquireSRWLockExclusive((PSRWLOCK)pv + 28);
    pv[344] = 1;
    _InterlockedAdd((volatile signed __int32 *)pv + 2, 1u);
    if ( !TrySubmitThreadpoolCallback(RemotePushSubscription::DeferredClose, pv, &g_wevtapiModuleCallbackEnvironment)
      && WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, LastError);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 28);
  }
  else
  {
    v3 = 1;
    AcquireSRWLockExclusive((PSRWLOCK)pv + 28);
    pv[344] = 1;
    if ( pv[345] )
    {
      v5 = EvtRpcCancel(*((_QWORD *)pv + 30));
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, v5);
        }
        *((_QWORD *)pv + 29) = 0;
      }
      if ( RpcAsyncGetCallStatus((PRPC_ASYNC_STATE)(pv + 80)) == 997 )
      {
        v6 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)(pv + 80), 1);
        if ( v6 != 1818 )
        {
          if ( v6 )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, v6);
            }
            v3 = 0;
          }
        }
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 28);
    if ( v3 )
      WaitForSingleObject(*((HANDLE *)pv + 9), 0xFFFFFFFF);
    v4 = (struct _TP_WAIT *)*((_QWORD *)pv + 8);
    *((_QWORD *)pv + 8) = 0;
    if ( v4 )
      RemotePushSubscription::WaitAndCloseThreadpoolWait(v4);
  }
}

```

## disassembly

```asm
0x180014e88  push    rbx
0x180014e8a  push    rbp
0x180014e8b  push    rsi
0x180014e8c  push    rdi
0x180014e8d  push    r14
0x180014e8f  sub     rsp, 20h
0x180014e93  mov     rdi, rcx
0x180014e96  mov     ebx, [rcx+154h]
0x180014e9c  call    cs:__imp_GetCurrentThreadId
0x180014ea2  cmp     eax, ebx
0x180014ea4  jz      loc_180014F84
0x180014eaa  mov     ebx, 1
0x180014eaf  lea     rbp, [rdi+0E0h]
0x180014eb6  mov     rcx, rbp; SRWLock
0x180014eb9  call    cs:__imp_AcquireSRWLockExclusive
0x180014ebf  mov     [rdi+158h], bl
0x180014ec5  cmp     byte ptr [rdi+159h], 0
0x180014ecc  jnz     short loc_180014F0A
0x180014ece  mov     rcx, rbp; SRWLock
0x180014ed1  call    cs:__imp_ReleaseSRWLockExclusive
0x180014ed7  test    bl, bl
0x180014ed9  jz      short loc_180014EE8
0x180014edb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014ede  mov     rcx, [rdi+48h]; hHandle
0x180014ee2  call    cs:__imp_WaitForSingleObject
0x180014ee8  mov     rcx, [rdi+40h]; pwa
0x180014eec  mov     qword ptr [rdi+40h], 0
0x180014ef4  test    rcx, rcx
0x180014ef7  jz      short loc_180014EFF
0x180014ef9  call    ?WaitAndCloseThreadpoolWait@RemotePushSubscription@@CAXPEAU_TP_WAIT@@@Z; RemotePushSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *)
0x180014efe  nop
0x180014eff  add     rsp, 20h
0x180014f03  pop     r14
0x180014f05  pop     rdi
0x180014f06  pop     rsi
0x180014f07  pop     rbp
0x180014f08  pop     rbx
0x180014f09  retn
0x180014f0a  mov     rcx, [rdi+0F0h]
0x180014f11  call    EvtRpcCancel
0x180014f16  lea     rsi, WPP_GLOBAL_Control
0x180014f1d  test    eax, eax
0x180014f1f  jnz     loc_18001503B
0x180014f25  lea     rcx, [rdi+50h]; pAsync
0x180014f29  call    cs:__imp_RpcAsyncGetCallStatus
0x180014f2f  cmp     eax, 3E5h
0x180014f34  jnz     short loc_180014ECE
0x180014f36  mov     edx, ebx; fAbort
0x180014f38  lea     rcx, [rdi+50h]; pAsync
0x180014f3c  call    cs:__imp_RpcAsyncCancelCall
0x180014f42  cmp     eax, 71Ah
0x180014f47  jz      short loc_180014ECE
0x180014f49  test    eax, eax
0x180014f4b  jz      short loc_180014ECE
0x180014f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f54  cmp     rcx, rsi
0x180014f57  jz      short loc_180014F7D
0x180014f59  test    byte ptr [rcx+1Ch], 40h
0x180014f5d  jz      short loc_180014F7D
0x180014f5f  cmp     byte ptr [rcx+19h], 2
0x180014f63  jb      short loc_180014F7D
0x180014f65  mov     edx, 11h
0x180014f6a  mov     r9d, eax
0x180014f6d  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180014f74  mov     rcx, [rcx+10h]
0x180014f78  call    WPP_SF_D
0x180014f7d  xor     bl, bl
0x180014f7f  jmp     loc_180014ECE
0x180014f84  lea     rsi, WPP_GLOBAL_Control
0x180014f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f92  cmp     rcx, rsi
0x180014f95  jz      short loc_180014FB8
0x180014f97  test    byte ptr [rcx+1Ch], 40h
0x180014f9b  jz      short loc_180014FB8
0x180014f9d  cmp     byte ptr [rcx+19h], 4
0x180014fa1  jb      short loc_180014FB8
0x180014fa3  mov     edx, 0Eh
0x180014fa8  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180014faf  mov     rcx, [rcx+10h]
0x180014fb3  call    WPP_SF_
0x180014fb8  lea     rbp, [rdi+0E0h]
0x180014fbf  mov     rcx, rbp; SRWLock
0x180014fc2  call    cs:__imp_AcquireSRWLockExclusive
0x180014fc8  mov     ebx, 1
0x180014fcd  mov     [rdi+158h], bl
0x180014fd3  lock add [rdi+8], ebx
0x180014fd7  lea     r8, ?g_wevtapiModuleCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180014fde  mov     rdx, rdi; pv
0x180014fe1  lea     rcx, ?DeferredClose@RemotePushSubscription@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180014fe8  call    cs:__imp_TrySubmitThreadpoolCallback
0x180014fee  test    eax, eax
0x180014ff0  jnz     short loc_18001502D
0x180014ff2  mov     rax, cs:WPP_GLOBAL_Control
0x180014ff9  cmp     rax, rsi
0x180014ffc  jz      short loc_18001502D
0x180014ffe  test    byte ptr [rax+1Ch], 40h
0x180015002  jz      short loc_18001502D
0x180015004  cmp     byte ptr [rax+19h], 2
0x180015008  jb      short loc_18001502D
0x18001500a  call    cs:__imp_GetLastError
0x180015010  lea     edx, [rbx+0Eh]
0x180015013  mov     r9d, eax
0x180015016  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x18001501d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015024  mov     rcx, [rcx+10h]
0x180015028  call    WPP_SF_D
0x18001502d  mov     rcx, rbp; SRWLock
0x180015030  call    cs:__imp_ReleaseSRWLockExclusive
0x180015036  jmp     loc_180014EFF
0x18001503b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015042  cmp     rcx, rsi
0x180015045  jz      short loc_18001506B
0x180015047  test    byte ptr [rcx+1Ch], 40h
0x18001504b  jz      short loc_18001506B
0x18001504d  cmp     byte ptr [rcx+19h], 2
0x180015051  jb      short loc_18001506B
0x180015053  mov     edx, 10h
0x180015058  mov     r9d, eax
0x18001505b  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180015062  mov     rcx, [rcx+10h]
0x180015066  call    WPP_SF_D
0x18001506b  mov     qword ptr [rdi+0E8h], 0
0x180015076  jmp     loc_180014F25
```
