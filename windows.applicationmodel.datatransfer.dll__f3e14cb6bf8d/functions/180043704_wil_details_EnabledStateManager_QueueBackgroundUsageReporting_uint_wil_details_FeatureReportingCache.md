# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180043704`
- end: `0x1800438bc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800482bc`

## callees

- `0x1800033f2`
- `0x18000346c`
- `0x180043704`
- `0x180057284`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800437b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800437dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800437b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800437dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800438a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800438a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043751`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043751`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004385d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004386a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004385d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004386a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004382b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004382b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180043855`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180043855`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004384c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004384c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180043819`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180043819`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004383e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043896`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004383e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043896`

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
0x180043704  push    rbx
0x180043706  push    rbp
0x180043707  push    rsi
0x180043708  push    rdi
0x180043709  push    r14
0x18004370b  push    r15
0x18004370d  sub     rsp, 28h
0x180043711  mov     rbp, r8
0x180043714  mov     r14d, edx
0x180043717  mov     rdi, rcx
0x18004371a  mov     eax, [rcx]
0x18004371c  test    eax, eax
0x18004371e  jz      loc_1800438AF
0x180043724  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004372b  jnz     loc_1800438AF
0x180043731  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180043738  test    rax, rax
0x18004373b  jz      short loc_18004374A
0x18004373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043742  test    al, al
0x180043744  jnz     loc_1800438AF
0x18004374a  lea     rsi, [rdi+8]
0x18004374e  mov     rcx, rsi; SRWLock
0x180043751  call    cs:__imp_AcquireSRWLockExclusive
0x180043757  mov     eax, [rdi]
0x180043759  test    eax, eax
0x18004375b  jz      loc_1800438A0
0x180043761  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180043768  jnz     loc_1800438A0
0x18004376e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180043775  test    rax, rax
0x180043778  jz      short loc_180043787
0x18004377a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004377f  test    al, al
0x180043781  jnz     loc_1800438A0
0x180043787  xor     r15d, r15d
0x18004378a  lea     edx, [r15+10h]; unsigned __int64
0x18004378e  lea     rcx, [rdi+20h]; this
0x180043792  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180043797  test    al, al
0x180043799  jz      short loc_1800437F3
0x18004379b  mov     rcx, [rdi+28h]; void *
0x18004379f  mov     rax, [rdi+30h]
0x1800437a3  sub     rax, rcx
0x1800437a6  cmp     rcx, [rdi+30h]
0x1800437aa  sbb     r8, r8
0x1800437ad  and     r8, rax; Size
0x1800437b0  test    rcx, rcx
0x1800437b3  jnz     short loc_1800437C3
0x1800437b5  call    cs:__imp__o__errno
0x1800437bb  mov     dword ptr [rax], 16h
0x1800437c1  jmp     short loc_1800437E9
0x1800437c3  cmp     r8, 10h
0x1800437c7  jb      short loc_1800437D6
0x1800437c9  mov     [rcx], r14d
0x1800437cc  mov     [rcx+4], r15d
0x1800437d0  mov     [rcx+8], rbp
0x1800437d4  jmp     short loc_1800437EE
0x1800437d6  xor     edx, edx; Val
0x1800437d8  call    memset_0
0x1800437dd  call    cs:__imp__o__errno
0x1800437e3  mov     dword ptr [rax], 22h ; '"'
0x1800437e9  call    _invalid_parameter_noinfo
0x1800437ee  add     qword ptr [rdi+28h], 10h
0x1800437f3  cmp     [rdi+18h], r15b
0x1800437f7  jnz     loc_1800438A0
0x1800437fd  cmp     [rdi+10h], r15
0x180043801  jnz     short loc_180043870
0x180043803  call    cs:__imp_GetLastError
0x180043809  mov     r14d, eax
0x18004380c  xor     r8d, r8d; pcbe
0x18004380f  mov     rdx, rdi; pv
0x180043812  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180043819  call    cs:__imp_CreateThreadpoolTimer
0x18004381f  mov     r15, rax
0x180043822  mov     rbp, [rdi+10h]
0x180043826  test    rbp, rbp
0x180043829  jz      short loc_180043863
0x18004382b  call    cs:__imp_GetLastError
0x180043831  mov     ebx, eax
0x180043833  xor     r9d, r9d; msWindowLength
0x180043836  xor     r8d, r8d; msPeriod
0x180043839  xor     edx, edx; pftDueTime
0x18004383b  mov     rcx, rbp; pti
0x18004383e  call    cs:__imp_SetThreadpoolTimer
0x180043844  mov     edx, 1; fCancelPendingCallbacks
0x180043849  mov     rcx, rbp; pti
0x18004384c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180043852  mov     rcx, rbp; pti
0x180043855  call    cs:__imp_CloseThreadpoolTimer
0x18004385b  mov     ecx, ebx; dwErrCode
0x18004385d  call    cs:__imp_SetLastError
0x180043863  mov     [rdi+10h], r15
0x180043867  mov     ecx, r14d; dwErrCode
0x18004386a  call    cs:__imp_SetLastError
0x180043870  mov     rcx, [rdi+10h]; pti
0x180043874  test    rcx, rcx
0x180043877  jz      short loc_1800438A0
0x180043879  mov     rax, 0FFFFFFFF4D2FA200h
0x180043883  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180043888  mov     r9d, 124F8h; msWindowLength
0x18004388e  xor     r8d, r8d; msPeriod
0x180043891  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180043896  call    cs:__imp_SetThreadpoolTimer
0x18004389c  mov     byte ptr [rdi+18h], 1
0x1800438a0  test    rsi, rsi
0x1800438a3  jz      short loc_1800438AF
0x1800438a5  mov     rcx, rsi; SRWLock
0x1800438a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800438ae  nop
0x1800438af  add     rsp, 28h
0x1800438b3  pop     r15
0x1800438b5  pop     r14
0x1800438b7  pop     rdi
0x1800438b8  pop     rsi
0x1800438b9  pop     rbp
0x1800438ba  pop     rbx
0x1800438bb  retn
```
