# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000a6b0`
- end: `0x18000a868`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c3c4`

## callees

- `0x1800032f2`
- `0x180003384`
- `0x18000a6b0`
- `0x18000e8d4`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a761`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a789`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a761`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a789`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a6fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a6fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a809`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a809`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a816`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a7c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a7c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a7ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a842`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a7ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a842`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a7f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a7f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a801`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a801`

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
0x18000a6b0  push    rbx
0x18000a6b2  push    rbp
0x18000a6b3  push    rsi
0x18000a6b4  push    rdi
0x18000a6b5  push    r14
0x18000a6b7  push    r15
0x18000a6b9  sub     rsp, 28h
0x18000a6bd  mov     rbp, r8
0x18000a6c0  mov     r14d, edx
0x18000a6c3  mov     rdi, rcx
0x18000a6c6  mov     eax, [rcx]
0x18000a6c8  test    eax, eax
0x18000a6ca  jz      loc_18000A85B
0x18000a6d0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a6d7  jnz     loc_18000A85B
0x18000a6dd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a6e4  test    rax, rax
0x18000a6e7  jz      short loc_18000A6F6
0x18000a6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ee  test    al, al
0x18000a6f0  jnz     loc_18000A85B
0x18000a6f6  lea     rsi, [rdi+8]
0x18000a6fa  mov     rcx, rsi; SRWLock
0x18000a6fd  call    cs:__imp_AcquireSRWLockExclusive
0x18000a703  mov     eax, [rdi]
0x18000a705  test    eax, eax
0x18000a707  jz      loc_18000A84C
0x18000a70d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a714  jnz     loc_18000A84C
0x18000a71a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a721  test    rax, rax
0x18000a724  jz      short loc_18000A733
0x18000a726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a72b  test    al, al
0x18000a72d  jnz     loc_18000A84C
0x18000a733  xor     r15d, r15d
0x18000a736  lea     edx, [r15+10h]; unsigned __int64
0x18000a73a  lea     rcx, [rdi+20h]; this
0x18000a73e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a743  test    al, al
0x18000a745  jz      short loc_18000A79F
0x18000a747  mov     rcx, [rdi+28h]; void *
0x18000a74b  mov     rax, [rdi+30h]
0x18000a74f  sub     rax, rcx
0x18000a752  cmp     rcx, [rdi+30h]
0x18000a756  sbb     r8, r8
0x18000a759  and     r8, rax; Size
0x18000a75c  test    rcx, rcx
0x18000a75f  jnz     short loc_18000A76F
0x18000a761  call    cs:__imp__o__errno
0x18000a767  mov     dword ptr [rax], 16h
0x18000a76d  jmp     short loc_18000A795
0x18000a76f  cmp     r8, 10h
0x18000a773  jb      short loc_18000A782
0x18000a775  mov     [rcx], r14d
0x18000a778  mov     [rcx+4], r15d
0x18000a77c  mov     [rcx+8], rbp
0x18000a780  jmp     short loc_18000A79A
0x18000a782  xor     edx, edx; Val
0x18000a784  call    memset_0
0x18000a789  call    cs:__imp__o__errno
0x18000a78f  mov     dword ptr [rax], 22h ; '"'
0x18000a795  call    _invalid_parameter_noinfo
0x18000a79a  add     qword ptr [rdi+28h], 10h
0x18000a79f  cmp     [rdi+18h], r15b
0x18000a7a3  jnz     loc_18000A84C
0x18000a7a9  cmp     [rdi+10h], r15
0x18000a7ad  jnz     short loc_18000A81C
0x18000a7af  call    cs:__imp_GetLastError
0x18000a7b5  mov     r14d, eax
0x18000a7b8  xor     r8d, r8d; pcbe
0x18000a7bb  mov     rdx, rdi; pv
0x18000a7be  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a7c5  call    cs:__imp_CreateThreadpoolTimer
0x18000a7cb  mov     r15, rax
0x18000a7ce  mov     rbp, [rdi+10h]
0x18000a7d2  test    rbp, rbp
0x18000a7d5  jz      short loc_18000A80F
0x18000a7d7  call    cs:__imp_GetLastError
0x18000a7dd  mov     ebx, eax
0x18000a7df  xor     r9d, r9d; msWindowLength
0x18000a7e2  xor     r8d, r8d; msPeriod
0x18000a7e5  xor     edx, edx; pftDueTime
0x18000a7e7  mov     rcx, rbp; pti
0x18000a7ea  call    cs:__imp_SetThreadpoolTimer
0x18000a7f0  mov     edx, 1; fCancelPendingCallbacks
0x18000a7f5  mov     rcx, rbp; pti
0x18000a7f8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a7fe  mov     rcx, rbp; pti
0x18000a801  call    cs:__imp_CloseThreadpoolTimer
0x18000a807  mov     ecx, ebx; dwErrCode
0x18000a809  call    cs:__imp_SetLastError
0x18000a80f  mov     [rdi+10h], r15
0x18000a813  mov     ecx, r14d; dwErrCode
0x18000a816  call    cs:__imp_SetLastError
0x18000a81c  mov     rcx, [rdi+10h]; pti
0x18000a820  test    rcx, rcx
0x18000a823  jz      short loc_18000A84C
0x18000a825  mov     rax, 0FFFFFFFF4D2FA200h
0x18000a82f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000a834  mov     r9d, 124F8h; msWindowLength
0x18000a83a  xor     r8d, r8d; msPeriod
0x18000a83d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000a842  call    cs:__imp_SetThreadpoolTimer
0x18000a848  mov     byte ptr [rdi+18h], 1
0x18000a84c  test    rsi, rsi
0x18000a84f  jz      short loc_18000A85B
0x18000a851  mov     rcx, rsi; SRWLock
0x18000a854  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a85a  nop
0x18000a85b  add     rsp, 28h
0x18000a85f  pop     r15
0x18000a861  pop     r14
0x18000a863  pop     rdi
0x18000a864  pop     rsi
0x18000a865  pop     rbp
0x18000a866  pop     rbx
0x18000a867  retn
```
