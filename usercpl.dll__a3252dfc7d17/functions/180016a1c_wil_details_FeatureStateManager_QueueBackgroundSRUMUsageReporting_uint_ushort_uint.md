# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180016a1c`
- end: `0x180016ba4`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800188a0`

## callees

- `0x180016a1c`
- `0x180019324`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180016aca`
- `msvcrt!memcpy_s` at `0x180016aca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016b3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016b4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016b3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016b4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016b2e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016b2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016afb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016afb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016b20`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016b72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016b20`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016b72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016b37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016b37`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
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
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
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
0x180016a1c  push    rbx
0x180016a1e  push    rbp
0x180016a1f  push    rsi
0x180016a20  push    rdi
0x180016a21  push    r14
0x180016a23  push    r15
0x180016a25  sub     rsp, 48h
0x180016a29  mov     rax, cs:__security_cookie
0x180016a30  xor     rax, rsp
0x180016a33  mov     [rsp+78h+var_40], rax
0x180016a38  cmp     byte ptr [rcx], 0
0x180016a3b  mov     r14d, r9d
0x180016a3e  movzx   ebp, r8w
0x180016a42  mov     ebx, edx
0x180016a44  mov     rdi, rcx
0x180016a47  jz      loc_180016B8A
0x180016a4d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016a54  jnz     loc_180016B8A
0x180016a5a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016a61  test    rax, rax
0x180016a64  jz      short loc_180016A73
0x180016a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6b  test    al, al
0x180016a6d  jnz     loc_180016B8A
0x180016a73  lea     rsi, [rdi+28h]
0x180016a77  mov     rcx, rsi; SRWLock
0x180016a7a  call    cs:__imp_AcquireSRWLockExclusive
0x180016a80  xor     eax, eax
0x180016a82  mov     [rsp+78h+Source], ebx
0x180016a86  mov     [rsp+78h+var_4C], bp
0x180016a8b  lea     rbx, [rdi+0E8h]
0x180016a92  mov     rcx, rbx; this
0x180016a95  mov     [rsp+78h+var_4A], ax
0x180016a9a  mov     [rsp+78h+var_48], r14d
0x180016a9f  lea     ebp, [rax+0Ch]
0x180016aa2  mov     edx, ebp; unsigned __int64
0x180016aa4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180016aa9  test    al, al
0x180016aab  jz      short loc_180016AD4
0x180016aad  mov     rcx, [rbx+8]; Destination
0x180016ab1  lea     r8, [rsp+78h+Source]; Source
0x180016ab6  mov     rax, [rbx+10h]
0x180016aba  mov     r9d, ebp; SourceSize
0x180016abd  sub     rax, rcx
0x180016ac0  cmp     rcx, [rbx+10h]
0x180016ac4  sbb     rdx, rdx
0x180016ac7  and     rdx, rax; DestinationSize
0x180016aca  call    cs:__imp_memcpy_s
0x180016ad0  add     [rbx+8], rbp
0x180016ad4  cmp     byte ptr [rdi+40h], 0
0x180016ad8  jnz     loc_180016B7C
0x180016ade  cmp     qword ptr [rdi+38h], 0
0x180016ae3  jnz     short loc_180016B52
0x180016ae5  call    cs:__imp_GetLastError
0x180016aeb  xor     r8d, r8d; pcbe
0x180016aee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016af5  mov     rdx, rdi; pv
0x180016af8  mov     r14d, eax
0x180016afb  call    cs:__imp_CreateThreadpoolTimer
0x180016b01  mov     rbp, [rdi+38h]
0x180016b05  mov     r15, rax
0x180016b08  test    rbp, rbp
0x180016b0b  jz      short loc_180016B45
0x180016b0d  call    cs:__imp_GetLastError
0x180016b13  xor     r9d, r9d; msWindowLength
0x180016b16  xor     r8d, r8d; msPeriod
0x180016b19  xor     edx, edx; pftDueTime
0x180016b1b  mov     rcx, rbp; pti
0x180016b1e  mov     ebx, eax
0x180016b20  call    cs:__imp_SetThreadpoolTimer
0x180016b26  mov     edx, 1; fCancelPendingCallbacks
0x180016b2b  mov     rcx, rbp; pti
0x180016b2e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016b34  mov     rcx, rbp; pti
0x180016b37  call    cs:__imp_CloseThreadpoolTimer
0x180016b3d  mov     ecx, ebx; dwErrCode
0x180016b3f  call    cs:__imp_SetLastError
0x180016b45  mov     ecx, r14d; dwErrCode
0x180016b48  mov     [rdi+38h], r15
0x180016b4c  call    cs:__imp_SetLastError
0x180016b52  mov     rcx, [rdi+38h]; pti
0x180016b56  test    rcx, rcx
0x180016b59  jz      short loc_180016B7C
0x180016b5b  mov     r9d, 4E2h; msWindowLength
0x180016b61  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180016b6a  xor     r8d, r8d; msPeriod
0x180016b6d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180016b72  call    cs:__imp_SetThreadpoolTimer
0x180016b78  mov     byte ptr [rdi+40h], 1
0x180016b7c  test    rsi, rsi
0x180016b7f  jz      short loc_180016B8A
0x180016b81  mov     rcx, rsi; SRWLock
0x180016b84  call    cs:__imp_ReleaseSRWLockExclusive
0x180016b8a  mov     rcx, [rsp+78h+var_40]
0x180016b8f  xor     rcx, rsp; StackCookie
0x180016b92  call    __security_check_cookie
0x180016b97  add     rsp, 48h
0x180016b9b  pop     r15
0x180016b9d  pop     r14
0x180016b9f  pop     rdi
0x180016ba0  pop     rsi
0x180016ba1  pop     rbp
0x180016ba2  pop     rbx
0x180016ba3  retn
```
