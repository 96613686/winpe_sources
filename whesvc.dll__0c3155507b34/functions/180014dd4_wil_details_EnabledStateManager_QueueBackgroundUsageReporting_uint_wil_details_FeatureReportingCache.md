# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014dd4`
- end: `0x180014f8c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180015740`

## callees

- `0x180003d0a`
- `0x180003da4`
- `0x18000ee54`
- `0x180014dd4`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014e85`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014ead`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014e85`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014efb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014f25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014f25`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014f0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014f66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014f0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014f66`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014f1c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014f1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014ee9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014ee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  __int64 v11; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
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
            v15 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v15);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v16 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v16 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v16, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180014dd4  push    rbx
0x180014dd6  push    rbp
0x180014dd7  push    rsi
0x180014dd8  push    rdi
0x180014dd9  push    r14
0x180014ddb  push    r15
0x180014ddd  sub     rsp, 28h
0x180014de1  mov     rbp, r8
0x180014de4  mov     r14d, edx
0x180014de7  mov     rdi, rcx
0x180014dea  mov     eax, [rcx]
0x180014dec  test    eax, eax
0x180014dee  jz      loc_180014F7F
0x180014df4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014dfb  jnz     loc_180014F7F
0x180014e01  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014e08  test    rax, rax
0x180014e0b  jz      short loc_180014E1A
0x180014e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e12  test    al, al
0x180014e14  jnz     loc_180014F7F
0x180014e1a  lea     rsi, [rdi+8]
0x180014e1e  mov     rcx, rsi; SRWLock
0x180014e21  call    cs:__imp_AcquireSRWLockExclusive
0x180014e27  mov     eax, [rdi]
0x180014e29  test    eax, eax
0x180014e2b  jz      loc_180014F70
0x180014e31  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014e38  jnz     loc_180014F70
0x180014e3e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014e45  test    rax, rax
0x180014e48  jz      short loc_180014E57
0x180014e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e4f  test    al, al
0x180014e51  jnz     loc_180014F70
0x180014e57  xor     r15d, r15d
0x180014e5a  lea     edx, [r15+10h]; unsigned __int64
0x180014e5e  lea     rcx, [rdi+20h]; this
0x180014e62  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180014e67  test    al, al
0x180014e69  jz      short loc_180014EC3
0x180014e6b  mov     rcx, [rdi+28h]; void *
0x180014e6f  mov     rax, [rdi+30h]
0x180014e73  sub     rax, rcx
0x180014e76  cmp     rcx, [rdi+30h]
0x180014e7a  sbb     r8, r8
0x180014e7d  and     r8, rax; Size
0x180014e80  test    rcx, rcx
0x180014e83  jnz     short loc_180014E93
0x180014e85  call    cs:__imp__o__errno
0x180014e8b  mov     dword ptr [rax], 16h
0x180014e91  jmp     short loc_180014EB9
0x180014e93  cmp     r8, 10h
0x180014e97  jb      short loc_180014EA6
0x180014e99  mov     [rcx], r14d
0x180014e9c  mov     [rcx+4], r15d
0x180014ea0  mov     [rcx+8], rbp
0x180014ea4  jmp     short loc_180014EBE
0x180014ea6  xor     edx, edx; Val
0x180014ea8  call    memset_0
0x180014ead  call    cs:__imp__o__errno
0x180014eb3  mov     dword ptr [rax], 22h ; '"'
0x180014eb9  call    _invalid_parameter_noinfo
0x180014ebe  add     qword ptr [rdi+28h], 10h
0x180014ec3  cmp     [rdi+18h], r15b
0x180014ec7  jnz     loc_180014F70
0x180014ecd  cmp     [rdi+10h], r15
0x180014ed1  jnz     short loc_180014F40
0x180014ed3  call    cs:__imp_GetLastError
0x180014ed9  mov     r14d, eax
0x180014edc  xor     r8d, r8d; pcbe
0x180014edf  mov     rdx, rdi; pv
0x180014ee2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014ee9  call    cs:__imp_CreateThreadpoolTimer
0x180014eef  mov     r15, rax
0x180014ef2  mov     rbp, [rdi+10h]
0x180014ef6  test    rbp, rbp
0x180014ef9  jz      short loc_180014F33
0x180014efb  call    cs:__imp_GetLastError
0x180014f01  mov     ebx, eax
0x180014f03  xor     r9d, r9d; msWindowLength
0x180014f06  xor     r8d, r8d; msPeriod
0x180014f09  xor     edx, edx; pftDueTime
0x180014f0b  mov     rcx, rbp; pti
0x180014f0e  call    cs:__imp_SetThreadpoolTimer
0x180014f14  mov     edx, 1; fCancelPendingCallbacks
0x180014f19  mov     rcx, rbp; pti
0x180014f1c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014f22  mov     rcx, rbp; pti
0x180014f25  call    cs:__imp_CloseThreadpoolTimer
0x180014f2b  mov     ecx, ebx; dwErrCode
0x180014f2d  call    cs:__imp_SetLastError
0x180014f33  mov     [rdi+10h], r15
0x180014f37  mov     ecx, r14d; dwErrCode
0x180014f3a  call    cs:__imp_SetLastError
0x180014f40  mov     rcx, [rdi+10h]; pti
0x180014f44  test    rcx, rcx
0x180014f47  jz      short loc_180014F70
0x180014f49  mov     rax, 0FFFFFFFF4D2FA200h
0x180014f53  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180014f58  mov     r9d, 124F8h; msWindowLength
0x180014f5e  xor     r8d, r8d; msPeriod
0x180014f61  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180014f66  call    cs:__imp_SetThreadpoolTimer
0x180014f6c  mov     byte ptr [rdi+18h], 1
0x180014f70  test    rsi, rsi
0x180014f73  jz      short loc_180014F7F
0x180014f75  mov     rcx, rsi; SRWLock
0x180014f78  call    cs:__imp_ReleaseSRWLockExclusive
0x180014f7e  nop
0x180014f7f  add     rsp, 28h
0x180014f83  pop     r15
0x180014f85  pop     r14
0x180014f87  pop     rdi
0x180014f88  pop     rsi
0x180014f89  pop     rbp
0x180014f8a  pop     rbx
0x180014f8b  retn
```
