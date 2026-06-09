# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140008fe8`
- end: `0x140009155`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `365`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400094a4`

## callees

- `0x140008fe8`
- `0x14000dcc8`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000909c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000909c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009103`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009103`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009141`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009141`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009034`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009034`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400090b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400090b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400090ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400090ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400090e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400090e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400090d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000912f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400090d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000912f`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _DWORD Src[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Src[0] = a2;
      Src[1] = 0;
      v12 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Src, 0x10u);
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
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x140008fe8  push    rbx
0x140008fea  push    rbp
0x140008feb  push    rsi
0x140008fec  push    rdi
0x140008fed  push    r14
0x140008fef  push    r15
0x140008ff1  sub     rsp, 38h
0x140008ff5  mov     rbx, r8
0x140008ff8  mov     ebp, edx
0x140008ffa  mov     rdi, rcx
0x140008ffd  mov     eax, [rcx]
0x140008fff  test    eax, eax
0x140009001  jz      loc_140009148
0x140009007  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000900e  jnz     loc_140009148
0x140009014  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000901b  test    rax, rax
0x14000901e  jz      short loc_14000902D
0x140009020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009025  test    al, al
0x140009027  jnz     loc_140009148
0x14000902d  lea     rsi, [rdi+8]
0x140009031  mov     rcx, rsi; SRWLock
0x140009034  call    cs:__imp_AcquireSRWLockExclusive
0x14000903a  mov     eax, [rdi]
0x14000903c  test    eax, eax
0x14000903e  jz      loc_140009139
0x140009044  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000904b  jnz     loc_140009139
0x140009051  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009058  test    rax, rax
0x14000905b  jz      short loc_14000906A
0x14000905d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009062  test    al, al
0x140009064  jnz     loc_140009139
0x14000906a  mov     [rsp+68h+Src], ebp
0x14000906e  xor     eax, eax
0x140009070  mov     [rsp+68h+var_44], eax
0x140009074  mov     [rsp+68h+var_40], rbx
0x140009079  lea     rcx, [rdi+20h]; this
0x14000907d  lea     r8d, [rax+10h]; Size
0x140009081  lea     rdx, [rsp+68h+Src]; Src
0x140009086  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000908b  cmp     byte ptr [rdi+18h], 0
0x14000908f  jnz     loc_140009139
0x140009095  cmp     qword ptr [rdi+10h], 0
0x14000909a  jnz     short loc_140009109
0x14000909c  call    cs:__imp_GetLastError
0x1400090a2  mov     r14d, eax
0x1400090a5  xor     r8d, r8d; pcbe
0x1400090a8  mov     rdx, rdi; pv
0x1400090ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400090b2  call    cs:__imp_CreateThreadpoolTimer
0x1400090b8  mov     r15, rax
0x1400090bb  mov     rbp, [rdi+10h]
0x1400090bf  test    rbp, rbp
0x1400090c2  jz      short loc_1400090FC
0x1400090c4  call    cs:__imp_GetLastError
0x1400090ca  mov     ebx, eax
0x1400090cc  xor     r9d, r9d; msWindowLength
0x1400090cf  xor     r8d, r8d; msPeriod
0x1400090d2  xor     edx, edx; pftDueTime
0x1400090d4  mov     rcx, rbp; pti
0x1400090d7  call    cs:__imp_SetThreadpoolTimer
0x1400090dd  mov     edx, 1; fCancelPendingCallbacks
0x1400090e2  mov     rcx, rbp; pti
0x1400090e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400090eb  mov     rcx, rbp; pti
0x1400090ee  call    cs:__imp_CloseThreadpoolTimer
0x1400090f4  mov     ecx, ebx; dwErrCode
0x1400090f6  call    cs:__imp_SetLastError
0x1400090fc  mov     [rdi+10h], r15
0x140009100  mov     ecx, r14d; dwErrCode
0x140009103  call    cs:__imp_SetLastError
0x140009109  mov     rcx, [rdi+10h]; pti
0x14000910d  test    rcx, rcx
0x140009110  jz      short loc_140009139
0x140009112  mov     rax, 0FFFFFFFF4D2FA200h
0x14000911c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x140009121  mov     r9d, 124F8h; msWindowLength
0x140009127  xor     r8d, r8d; msPeriod
0x14000912a  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000912f  call    cs:__imp_SetThreadpoolTimer
0x140009135  mov     byte ptr [rdi+18h], 1
0x140009139  test    rsi, rsi
0x14000913c  jz      short loc_140009148
0x14000913e  mov     rcx, rsi; SRWLock
0x140009141  call    cs:__imp_ReleaseSRWLockExclusive
0x140009147  nop
0x140009148  add     rsp, 38h
0x14000914c  pop     r15
0x14000914e  pop     r14
0x140009150  pop     rdi
0x140009151  pop     rsi
0x140009152  pop     rbp
0x140009153  pop     rbx
0x140009154  retn
```
