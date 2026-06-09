# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400121e8`
- end: `0x14001232c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `324`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400144d0`

## callees

- `0x14000dcc8`
- `0x1400121e8`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400122a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400122a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400122d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400122e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400122d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400122e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012318`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012318`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012238`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012238`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001228f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001228f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400122cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400122cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400122c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400122c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400122b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140012306`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400122b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140012306`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  int Src; // [rsp+20h] [rbp-48h] BYREF
  __int16 v14; // [rsp+24h] [rbp-44h]
  __int16 v15; // [rsp+26h] [rbp-42h]
  int v16; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v15 = 0;
    Src = a2;
    v14 = a3;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Src, 0xCu);
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x1400121e8  push    rbx
0x1400121ea  push    rbp
0x1400121eb  push    rsi
0x1400121ec  push    rdi
0x1400121ed  push    r14
0x1400121ef  push    r15
0x1400121f1  sub     rsp, 38h
0x1400121f5  mov     ebx, r9d
0x1400121f8  movzx   ebp, r8w
0x1400121fc  mov     r14d, edx
0x1400121ff  mov     rdi, rcx
0x140012202  cmp     byte ptr [rcx], 0
0x140012205  jz      loc_14001231F
0x14001220b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140012212  jnz     loc_14001231F
0x140012218  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001221f  test    rax, rax
0x140012222  jz      short loc_140012231
0x140012224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012229  test    al, al
0x14001222b  jnz     loc_14001231F
0x140012231  lea     rsi, [rdi+28h]
0x140012235  mov     rcx, rsi; SRWLock
0x140012238  call    cs:__imp_AcquireSRWLockExclusive
0x14001223e  xor     eax, eax
0x140012240  mov     [rsp+68h+var_42], ax
0x140012245  mov     [rsp+68h+Src], r14d
0x14001224a  mov     [rsp+68h+var_44], bp
0x14001224f  mov     [rsp+68h+var_40], ebx
0x140012253  lea     rcx, [rdi+0E8h]; this
0x14001225a  lea     r8d, [rax+0Ch]; Size
0x14001225e  lea     rdx, [rsp+68h+Src]; Src
0x140012263  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140012268  cmp     byte ptr [rdi+40h], 0
0x14001226c  jnz     loc_140012310
0x140012272  cmp     qword ptr [rdi+38h], 0
0x140012277  jnz     short loc_1400122E6
0x140012279  call    cs:__imp_GetLastError
0x14001227f  mov     r14d, eax
0x140012282  xor     r8d, r8d; pcbe
0x140012285  mov     rdx, rdi; pv
0x140012288  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14001228f  call    cs:__imp_CreateThreadpoolTimer
0x140012295  mov     r15, rax
0x140012298  mov     rbp, [rdi+38h]
0x14001229c  test    rbp, rbp
0x14001229f  jz      short loc_1400122D9
0x1400122a1  call    cs:__imp_GetLastError
0x1400122a7  mov     ebx, eax
0x1400122a9  xor     r9d, r9d; msWindowLength
0x1400122ac  xor     r8d, r8d; msPeriod
0x1400122af  xor     edx, edx; pftDueTime
0x1400122b1  mov     rcx, rbp; pti
0x1400122b4  call    cs:__imp_SetThreadpoolTimer
0x1400122ba  mov     edx, 1; fCancelPendingCallbacks
0x1400122bf  mov     rcx, rbp; pti
0x1400122c2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400122c8  mov     rcx, rbp; pti
0x1400122cb  call    cs:__imp_CloseThreadpoolTimer
0x1400122d1  mov     ecx, ebx; dwErrCode
0x1400122d3  call    cs:__imp_SetLastError
0x1400122d9  mov     [rdi+38h], r15
0x1400122dd  mov     ecx, r14d; dwErrCode
0x1400122e0  call    cs:__imp_SetLastError
0x1400122e6  mov     rcx, [rdi+38h]; pti
0x1400122ea  test    rcx, rcx
0x1400122ed  jz      short loc_140012310
0x1400122ef  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1400122f8  mov     r9d, 4E2h; msWindowLength
0x1400122fe  xor     r8d, r8d; msPeriod
0x140012301  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140012306  call    cs:__imp_SetThreadpoolTimer
0x14001230c  mov     byte ptr [rdi+40h], 1
0x140012310  test    rsi, rsi
0x140012313  jz      short loc_14001231F
0x140012315  mov     rcx, rsi; SRWLock
0x140012318  call    cs:__imp_ReleaseSRWLockExclusive
0x14001231e  nop
0x14001231f  add     rsp, 38h
0x140012323  pop     r15
0x140012325  pop     r14
0x140012327  pop     rdi
0x140012328  pop     rsi
0x140012329  pop     rbp
0x14001232a  pop     rbx
0x14001232b  retn
```
