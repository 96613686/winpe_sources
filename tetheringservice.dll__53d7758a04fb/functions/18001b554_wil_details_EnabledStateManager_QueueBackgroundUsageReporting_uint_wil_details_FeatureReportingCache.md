# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001b554`
- end: `0x18001b70c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001bf34`

## callees

- `0x180002ffa`
- `0x180003088`
- `0x18000a35c`
- `0x18001b554`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b605`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b62d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b605`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b62d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b6f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b6f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b5a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b67b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b6ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b6ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b6a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b6a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b669`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b68e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b6e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b68e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b6e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b69c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b69c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v14 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v14);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v15 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v15 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v15, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)_o__errno(v10, v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18001b554  push    rbx
0x18001b556  push    rbp
0x18001b557  push    rsi
0x18001b558  push    rdi
0x18001b559  push    r14
0x18001b55b  push    r15
0x18001b55d  sub     rsp, 28h
0x18001b561  mov     rbp, r8
0x18001b564  mov     r14d, edx
0x18001b567  mov     rdi, rcx
0x18001b56a  mov     eax, [rcx]
0x18001b56c  test    eax, eax
0x18001b56e  jz      loc_18001B6FF
0x18001b574  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001b57b  jnz     loc_18001B6FF
0x18001b581  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001b588  test    rax, rax
0x18001b58b  jz      short loc_18001B59A
0x18001b58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b592  test    al, al
0x18001b594  jnz     loc_18001B6FF
0x18001b59a  lea     rsi, [rdi+8]
0x18001b59e  mov     rcx, rsi; SRWLock
0x18001b5a1  call    cs:__imp_AcquireSRWLockExclusive
0x18001b5a7  mov     eax, [rdi]
0x18001b5a9  test    eax, eax
0x18001b5ab  jz      loc_18001B6F0
0x18001b5b1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001b5b8  jnz     loc_18001B6F0
0x18001b5be  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001b5c5  test    rax, rax
0x18001b5c8  jz      short loc_18001B5D7
0x18001b5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5cf  test    al, al
0x18001b5d1  jnz     loc_18001B6F0
0x18001b5d7  xor     r15d, r15d
0x18001b5da  lea     edx, [r15+10h]; unsigned __int64
0x18001b5de  lea     rcx, [rdi+20h]; this
0x18001b5e2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001b5e7  test    al, al
0x18001b5e9  jz      short loc_18001B643
0x18001b5eb  mov     rcx, [rdi+28h]; void *
0x18001b5ef  mov     rax, [rdi+30h]
0x18001b5f3  sub     rax, rcx
0x18001b5f6  cmp     rcx, [rdi+30h]
0x18001b5fa  sbb     r8, r8
0x18001b5fd  and     r8, rax; Size
0x18001b600  test    rcx, rcx
0x18001b603  jnz     short loc_18001B613
0x18001b605  call    cs:__imp__o__errno
0x18001b60b  mov     dword ptr [rax], 16h
0x18001b611  jmp     short loc_18001B639
0x18001b613  cmp     r8, 10h
0x18001b617  jb      short loc_18001B626
0x18001b619  mov     [rcx], r14d
0x18001b61c  mov     [rcx+4], r15d
0x18001b620  mov     [rcx+8], rbp
0x18001b624  jmp     short loc_18001B63E
0x18001b626  xor     edx, edx; Val
0x18001b628  call    memset_0
0x18001b62d  call    cs:__imp__o__errno
0x18001b633  mov     dword ptr [rax], 22h ; '"'
0x18001b639  call    _invalid_parameter_noinfo
0x18001b63e  add     qword ptr [rdi+28h], 10h
0x18001b643  cmp     [rdi+18h], r15b
0x18001b647  jnz     loc_18001B6F0
0x18001b64d  cmp     [rdi+10h], r15
0x18001b651  jnz     short loc_18001B6C0
0x18001b653  call    cs:__imp_GetLastError
0x18001b659  mov     r14d, eax
0x18001b65c  xor     r8d, r8d; pcbe
0x18001b65f  mov     rdx, rdi; pv
0x18001b662  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b669  call    cs:__imp_CreateThreadpoolTimer
0x18001b66f  mov     r15, rax
0x18001b672  mov     rbp, [rdi+10h]
0x18001b676  test    rbp, rbp
0x18001b679  jz      short loc_18001B6B3
0x18001b67b  call    cs:__imp_GetLastError
0x18001b681  mov     ebx, eax
0x18001b683  xor     r9d, r9d; msWindowLength
0x18001b686  xor     r8d, r8d; msPeriod
0x18001b689  xor     edx, edx; pftDueTime
0x18001b68b  mov     rcx, rbp; pti
0x18001b68e  call    cs:__imp_SetThreadpoolTimer
0x18001b694  mov     edx, 1; fCancelPendingCallbacks
0x18001b699  mov     rcx, rbp; pti
0x18001b69c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b6a2  mov     rcx, rbp; pti
0x18001b6a5  call    cs:__imp_CloseThreadpoolTimer
0x18001b6ab  mov     ecx, ebx; dwErrCode
0x18001b6ad  call    cs:__imp_SetLastError
0x18001b6b3  mov     [rdi+10h], r15
0x18001b6b7  mov     ecx, r14d; dwErrCode
0x18001b6ba  call    cs:__imp_SetLastError
0x18001b6c0  mov     rcx, [rdi+10h]; pti
0x18001b6c4  test    rcx, rcx
0x18001b6c7  jz      short loc_18001B6F0
0x18001b6c9  mov     rax, 0FFFFFFFF4D2FA200h
0x18001b6d3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18001b6d8  mov     r9d, 124F8h; msWindowLength
0x18001b6de  xor     r8d, r8d; msPeriod
0x18001b6e1  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001b6e6  call    cs:__imp_SetThreadpoolTimer
0x18001b6ec  mov     byte ptr [rdi+18h], 1
0x18001b6f0  test    rsi, rsi
0x18001b6f3  jz      short loc_18001B6FF
0x18001b6f5  mov     rcx, rsi; SRWLock
0x18001b6f8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b6fe  nop
0x18001b6ff  add     rsp, 28h
0x18001b703  pop     r15
0x18001b705  pop     r14
0x18001b707  pop     rdi
0x18001b708  pop     rsi
0x18001b709  pop     rbp
0x18001b70a  pop     rbx
0x18001b70b  retn
```
