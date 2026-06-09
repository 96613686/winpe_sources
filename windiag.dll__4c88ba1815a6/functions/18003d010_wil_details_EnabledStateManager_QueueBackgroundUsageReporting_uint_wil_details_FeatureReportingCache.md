# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003d010`
- end: `0x18003d1c8`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003d308`

## callees

- `0x1800053be`
- `0x1800054e4`
- `0x18003983c`
- `0x18003d010`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d0c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d0e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d0c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d0e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d05d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d05d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d1b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d1b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d169`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d176`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d169`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d137`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d158`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d158`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003d161`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003d161`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d14a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d1a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d14a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d1a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d125`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d125`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
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
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v13 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
0x18003d010  push    rbx
0x18003d012  push    rbp
0x18003d013  push    rsi
0x18003d014  push    rdi
0x18003d015  push    r14
0x18003d017  push    r15
0x18003d019  sub     rsp, 28h
0x18003d01d  mov     rbp, r8
0x18003d020  mov     r14d, edx
0x18003d023  mov     rdi, rcx
0x18003d026  mov     eax, [rcx]
0x18003d028  test    eax, eax
0x18003d02a  jz      loc_18003D1BB
0x18003d030  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003d037  jnz     loc_18003D1BB
0x18003d03d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003d044  test    rax, rax
0x18003d047  jz      short loc_18003D056
0x18003d049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d04e  test    al, al
0x18003d050  jnz     loc_18003D1BB
0x18003d056  lea     rsi, [rdi+8]
0x18003d05a  mov     rcx, rsi; SRWLock
0x18003d05d  call    cs:__imp_AcquireSRWLockExclusive
0x18003d063  mov     eax, [rdi]
0x18003d065  test    eax, eax
0x18003d067  jz      loc_18003D1AC
0x18003d06d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003d074  jnz     loc_18003D1AC
0x18003d07a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003d081  test    rax, rax
0x18003d084  jz      short loc_18003D093
0x18003d086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d08b  test    al, al
0x18003d08d  jnz     loc_18003D1AC
0x18003d093  xor     r15d, r15d
0x18003d096  lea     edx, [r15+10h]; unsigned __int64
0x18003d09a  lea     rcx, [rdi+20h]; this
0x18003d09e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18003d0a3  test    al, al
0x18003d0a5  jz      short loc_18003D0FF
0x18003d0a7  mov     rcx, [rdi+28h]; void *
0x18003d0ab  mov     rax, [rdi+30h]
0x18003d0af  sub     rax, rcx
0x18003d0b2  cmp     rcx, [rdi+30h]
0x18003d0b6  sbb     r8, r8
0x18003d0b9  and     r8, rax; Size
0x18003d0bc  test    rcx, rcx
0x18003d0bf  jnz     short loc_18003D0CF
0x18003d0c1  call    cs:__imp__o__errno
0x18003d0c7  mov     dword ptr [rax], 16h
0x18003d0cd  jmp     short loc_18003D0F5
0x18003d0cf  cmp     r8, 10h
0x18003d0d3  jb      short loc_18003D0E2
0x18003d0d5  mov     [rcx], r14d
0x18003d0d8  mov     [rcx+4], r15d
0x18003d0dc  mov     [rcx+8], rbp
0x18003d0e0  jmp     short loc_18003D0FA
0x18003d0e2  xor     edx, edx; Val
0x18003d0e4  call    memset_0
0x18003d0e9  call    cs:__imp__o__errno
0x18003d0ef  mov     dword ptr [rax], 22h ; '"'
0x18003d0f5  call    _invalid_parameter_noinfo
0x18003d0fa  add     qword ptr [rdi+28h], 10h
0x18003d0ff  cmp     [rdi+18h], r15b
0x18003d103  jnz     loc_18003D1AC
0x18003d109  cmp     [rdi+10h], r15
0x18003d10d  jnz     short loc_18003D17C
0x18003d10f  call    cs:__imp_GetLastError
0x18003d115  mov     r14d, eax
0x18003d118  xor     r8d, r8d; pcbe
0x18003d11b  mov     rdx, rdi; pv
0x18003d11e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003d125  call    cs:__imp_CreateThreadpoolTimer
0x18003d12b  mov     r15, rax
0x18003d12e  mov     rbp, [rdi+10h]
0x18003d132  test    rbp, rbp
0x18003d135  jz      short loc_18003D16F
0x18003d137  call    cs:__imp_GetLastError
0x18003d13d  mov     ebx, eax
0x18003d13f  xor     r9d, r9d; msWindowLength
0x18003d142  xor     r8d, r8d; msPeriod
0x18003d145  xor     edx, edx; pftDueTime
0x18003d147  mov     rcx, rbp; pti
0x18003d14a  call    cs:__imp_SetThreadpoolTimer
0x18003d150  mov     edx, 1; fCancelPendingCallbacks
0x18003d155  mov     rcx, rbp; pti
0x18003d158  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003d15e  mov     rcx, rbp; pti
0x18003d161  call    cs:__imp_CloseThreadpoolTimer
0x18003d167  mov     ecx, ebx; dwErrCode
0x18003d169  call    cs:__imp_SetLastError
0x18003d16f  mov     [rdi+10h], r15
0x18003d173  mov     ecx, r14d; dwErrCode
0x18003d176  call    cs:__imp_SetLastError
0x18003d17c  mov     rcx, [rdi+10h]; pti
0x18003d180  test    rcx, rcx
0x18003d183  jz      short loc_18003D1AC
0x18003d185  mov     rax, 0FFFFFFFF4D2FA200h
0x18003d18f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18003d194  mov     r9d, 124F8h; msWindowLength
0x18003d19a  xor     r8d, r8d; msPeriod
0x18003d19d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18003d1a2  call    cs:__imp_SetThreadpoolTimer
0x18003d1a8  mov     byte ptr [rdi+18h], 1
0x18003d1ac  test    rsi, rsi
0x18003d1af  jz      short loc_18003D1BB
0x18003d1b1  mov     rcx, rsi; SRWLock
0x18003d1b4  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d1ba  nop
0x18003d1bb  add     rsp, 28h
0x18003d1bf  pop     r15
0x18003d1c1  pop     r14
0x18003d1c3  pop     rdi
0x18003d1c4  pop     rsi
0x18003d1c5  pop     rbp
0x18003d1c6  pop     rbx
0x18003d1c7  retn
```
