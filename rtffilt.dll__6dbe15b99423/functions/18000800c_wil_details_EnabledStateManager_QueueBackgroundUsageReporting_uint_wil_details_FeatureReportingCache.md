# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000800c`
- end: `0x1800081c4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a498`

## callees

- `0x180002846`
- `0x1800028b4`
- `0x18000800c`
- `0x18000c82c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800080bd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800080e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800080bd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800080e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008059`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008165`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008172`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008165`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000810b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000810b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008133`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000815d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000815d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008154`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008154`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008146`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000819e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008146`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000819e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008121`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008121`

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
0x18000800c  push    rbx
0x18000800e  push    rbp
0x18000800f  push    rsi
0x180008010  push    rdi
0x180008011  push    r14
0x180008013  push    r15
0x180008015  sub     rsp, 28h
0x180008019  mov     rbp, r8
0x18000801c  mov     r14d, edx
0x18000801f  mov     rdi, rcx
0x180008022  mov     eax, [rcx]
0x180008024  test    eax, eax
0x180008026  jz      loc_1800081B7
0x18000802c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008033  jnz     loc_1800081B7
0x180008039  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008040  test    rax, rax
0x180008043  jz      short loc_180008052
0x180008045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000804a  test    al, al
0x18000804c  jnz     loc_1800081B7
0x180008052  lea     rsi, [rdi+8]
0x180008056  mov     rcx, rsi; SRWLock
0x180008059  call    cs:__imp_AcquireSRWLockExclusive
0x18000805f  mov     eax, [rdi]
0x180008061  test    eax, eax
0x180008063  jz      loc_1800081A8
0x180008069  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008070  jnz     loc_1800081A8
0x180008076  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000807d  test    rax, rax
0x180008080  jz      short loc_18000808F
0x180008082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008087  test    al, al
0x180008089  jnz     loc_1800081A8
0x18000808f  xor     r15d, r15d
0x180008092  lea     edx, [r15+10h]; unsigned __int64
0x180008096  lea     rcx, [rdi+20h]; this
0x18000809a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000809f  test    al, al
0x1800080a1  jz      short loc_1800080FB
0x1800080a3  mov     rcx, [rdi+28h]; void *
0x1800080a7  mov     rax, [rdi+30h]
0x1800080ab  sub     rax, rcx
0x1800080ae  cmp     rcx, [rdi+30h]
0x1800080b2  sbb     r8, r8
0x1800080b5  and     r8, rax; Size
0x1800080b8  test    rcx, rcx
0x1800080bb  jnz     short loc_1800080CB
0x1800080bd  call    cs:__imp__o__errno
0x1800080c3  mov     dword ptr [rax], 16h
0x1800080c9  jmp     short loc_1800080F1
0x1800080cb  cmp     r8, 10h
0x1800080cf  jb      short loc_1800080DE
0x1800080d1  mov     [rcx], r14d
0x1800080d4  mov     [rcx+4], r15d
0x1800080d8  mov     [rcx+8], rbp
0x1800080dc  jmp     short loc_1800080F6
0x1800080de  xor     edx, edx; Val
0x1800080e0  call    memset_0
0x1800080e5  call    cs:__imp__o__errno
0x1800080eb  mov     dword ptr [rax], 22h ; '"'
0x1800080f1  call    _invalid_parameter_noinfo
0x1800080f6  add     qword ptr [rdi+28h], 10h
0x1800080fb  cmp     [rdi+18h], r15b
0x1800080ff  jnz     loc_1800081A8
0x180008105  cmp     [rdi+10h], r15
0x180008109  jnz     short loc_180008178
0x18000810b  call    cs:__imp_GetLastError
0x180008111  mov     r14d, eax
0x180008114  xor     r8d, r8d; pcbe
0x180008117  mov     rdx, rdi; pv
0x18000811a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008121  call    cs:__imp_CreateThreadpoolTimer
0x180008127  mov     r15, rax
0x18000812a  mov     rbp, [rdi+10h]
0x18000812e  test    rbp, rbp
0x180008131  jz      short loc_18000816B
0x180008133  call    cs:__imp_GetLastError
0x180008139  mov     ebx, eax
0x18000813b  xor     r9d, r9d; msWindowLength
0x18000813e  xor     r8d, r8d; msPeriod
0x180008141  xor     edx, edx; pftDueTime
0x180008143  mov     rcx, rbp; pti
0x180008146  call    cs:__imp_SetThreadpoolTimer
0x18000814c  mov     edx, 1; fCancelPendingCallbacks
0x180008151  mov     rcx, rbp; pti
0x180008154  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000815a  mov     rcx, rbp; pti
0x18000815d  call    cs:__imp_CloseThreadpoolTimer
0x180008163  mov     ecx, ebx; dwErrCode
0x180008165  call    cs:__imp_SetLastError
0x18000816b  mov     [rdi+10h], r15
0x18000816f  mov     ecx, r14d; dwErrCode
0x180008172  call    cs:__imp_SetLastError
0x180008178  mov     rcx, [rdi+10h]; pti
0x18000817c  test    rcx, rcx
0x18000817f  jz      short loc_1800081A8
0x180008181  mov     rax, 0FFFFFFFF4D2FA200h
0x18000818b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180008190  mov     r9d, 124F8h; msWindowLength
0x180008196  xor     r8d, r8d; msPeriod
0x180008199  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000819e  call    cs:__imp_SetThreadpoolTimer
0x1800081a4  mov     byte ptr [rdi+18h], 1
0x1800081a8  test    rsi, rsi
0x1800081ab  jz      short loc_1800081B7
0x1800081ad  mov     rcx, rsi; SRWLock
0x1800081b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800081b6  nop
0x1800081b7  add     rsp, 28h
0x1800081bb  pop     r15
0x1800081bd  pop     r14
0x1800081bf  pop     rdi
0x1800081c0  pop     rsi
0x1800081c1  pop     rbp
0x1800081c2  pop     rbx
0x1800081c3  retn
```
