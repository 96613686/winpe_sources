# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000b114`
- end: `0x18000b2cc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c948`

## callees

- `0x18000355e`
- `0x1800035e8`
- `0x18000b114`
- `0x18001171c`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1c5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1ed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1c5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b23b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b26d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b26d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b27a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b161`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b161`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b25c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b25c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b265`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b265`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b229`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b229`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b24e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b2a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b24e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b2a6`

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
0x18000b114  push    rbx
0x18000b116  push    rbp
0x18000b117  push    rsi
0x18000b118  push    rdi
0x18000b119  push    r14
0x18000b11b  push    r15
0x18000b11d  sub     rsp, 28h
0x18000b121  mov     rbp, r8
0x18000b124  mov     r14d, edx
0x18000b127  mov     rdi, rcx
0x18000b12a  mov     eax, [rcx]
0x18000b12c  test    eax, eax
0x18000b12e  jz      loc_18000B2BF
0x18000b134  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b13b  jnz     loc_18000B2BF
0x18000b141  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b148  test    rax, rax
0x18000b14b  jz      short loc_18000B15A
0x18000b14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b152  test    al, al
0x18000b154  jnz     loc_18000B2BF
0x18000b15a  lea     rsi, [rdi+8]
0x18000b15e  mov     rcx, rsi; SRWLock
0x18000b161  call    cs:__imp_AcquireSRWLockExclusive
0x18000b167  mov     eax, [rdi]
0x18000b169  test    eax, eax
0x18000b16b  jz      loc_18000B2B0
0x18000b171  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b178  jnz     loc_18000B2B0
0x18000b17e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b185  test    rax, rax
0x18000b188  jz      short loc_18000B197
0x18000b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18f  test    al, al
0x18000b191  jnz     loc_18000B2B0
0x18000b197  xor     r15d, r15d
0x18000b19a  lea     edx, [r15+10h]; unsigned __int64
0x18000b19e  lea     rcx, [rdi+20h]; this
0x18000b1a2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b1a7  test    al, al
0x18000b1a9  jz      short loc_18000B203
0x18000b1ab  mov     rcx, [rdi+28h]; void *
0x18000b1af  mov     rax, [rdi+30h]
0x18000b1b3  sub     rax, rcx
0x18000b1b6  cmp     rcx, [rdi+30h]
0x18000b1ba  sbb     r8, r8
0x18000b1bd  and     r8, rax; Size
0x18000b1c0  test    rcx, rcx
0x18000b1c3  jnz     short loc_18000B1D3
0x18000b1c5  call    cs:__imp__o__errno
0x18000b1cb  mov     dword ptr [rax], 16h
0x18000b1d1  jmp     short loc_18000B1F9
0x18000b1d3  cmp     r8, 10h
0x18000b1d7  jb      short loc_18000B1E6
0x18000b1d9  mov     [rcx], r14d
0x18000b1dc  mov     [rcx+4], r15d
0x18000b1e0  mov     [rcx+8], rbp
0x18000b1e4  jmp     short loc_18000B1FE
0x18000b1e6  xor     edx, edx; Val
0x18000b1e8  call    memset_0
0x18000b1ed  call    cs:__imp__o__errno
0x18000b1f3  mov     dword ptr [rax], 22h ; '"'
0x18000b1f9  call    _invalid_parameter_noinfo
0x18000b1fe  add     qword ptr [rdi+28h], 10h
0x18000b203  cmp     [rdi+18h], r15b
0x18000b207  jnz     loc_18000B2B0
0x18000b20d  cmp     [rdi+10h], r15
0x18000b211  jnz     short loc_18000B280
0x18000b213  call    cs:__imp_GetLastError
0x18000b219  mov     r14d, eax
0x18000b21c  xor     r8d, r8d; pcbe
0x18000b21f  mov     rdx, rdi; pv
0x18000b222  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b229  call    cs:__imp_CreateThreadpoolTimer
0x18000b22f  mov     r15, rax
0x18000b232  mov     rbp, [rdi+10h]
0x18000b236  test    rbp, rbp
0x18000b239  jz      short loc_18000B273
0x18000b23b  call    cs:__imp_GetLastError
0x18000b241  mov     ebx, eax
0x18000b243  xor     r9d, r9d; msWindowLength
0x18000b246  xor     r8d, r8d; msPeriod
0x18000b249  xor     edx, edx; pftDueTime
0x18000b24b  mov     rcx, rbp; pti
0x18000b24e  call    cs:__imp_SetThreadpoolTimer
0x18000b254  mov     edx, 1; fCancelPendingCallbacks
0x18000b259  mov     rcx, rbp; pti
0x18000b25c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b262  mov     rcx, rbp; pti
0x18000b265  call    cs:__imp_CloseThreadpoolTimer
0x18000b26b  mov     ecx, ebx; dwErrCode
0x18000b26d  call    cs:__imp_SetLastError
0x18000b273  mov     [rdi+10h], r15
0x18000b277  mov     ecx, r14d; dwErrCode
0x18000b27a  call    cs:__imp_SetLastError
0x18000b280  mov     rcx, [rdi+10h]; pti
0x18000b284  test    rcx, rcx
0x18000b287  jz      short loc_18000B2B0
0x18000b289  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b293  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000b298  mov     r9d, 124F8h; msWindowLength
0x18000b29e  xor     r8d, r8d; msPeriod
0x18000b2a1  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000b2a6  call    cs:__imp_SetThreadpoolTimer
0x18000b2ac  mov     byte ptr [rdi+18h], 1
0x18000b2b0  test    rsi, rsi
0x18000b2b3  jz      short loc_18000B2BF
0x18000b2b5  mov     rcx, rsi; SRWLock
0x18000b2b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2be  nop
0x18000b2bf  add     rsp, 28h
0x18000b2c3  pop     r15
0x18000b2c5  pop     r14
0x18000b2c7  pop     rdi
0x18000b2c8  pop     rsi
0x18000b2c9  pop     rbp
0x18000b2ca  pop     rbx
0x18000b2cb  retn
```
