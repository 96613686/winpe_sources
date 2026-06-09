# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000c760`
- end: `0x18000c8e8`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000eb10`

## callees

- `0x18000c760`
- `0x180011038`
- `0x1800121b0`
- `0x180013010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c80e`
- `msvcrt!memcpy_s` at `0x18000c80e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c7be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c7be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c851`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c890`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c872`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c872`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c83f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c83f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c87b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c87b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c864`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c8b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c864`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c8b6`

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
0x18000c760  push    rbx
0x18000c762  push    rbp
0x18000c763  push    rsi
0x18000c764  push    rdi
0x18000c765  push    r14
0x18000c767  push    r15
0x18000c769  sub     rsp, 48h
0x18000c76d  mov     rax, cs:__security_cookie
0x18000c774  xor     rax, rsp
0x18000c777  mov     [rsp+78h+var_40], rax
0x18000c77c  cmp     byte ptr [rcx], 0
0x18000c77f  mov     r14d, r9d
0x18000c782  movzx   ebp, r8w
0x18000c786  mov     ebx, edx
0x18000c788  mov     rdi, rcx
0x18000c78b  jz      loc_18000C8CE
0x18000c791  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c798  jnz     loc_18000C8CE
0x18000c79e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c7a5  test    rax, rax
0x18000c7a8  jz      short loc_18000C7B7
0x18000c7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7af  test    al, al
0x18000c7b1  jnz     loc_18000C8CE
0x18000c7b7  lea     rsi, [rdi+28h]
0x18000c7bb  mov     rcx, rsi; SRWLock
0x18000c7be  call    cs:__imp_AcquireSRWLockExclusive
0x18000c7c4  xor     eax, eax
0x18000c7c6  mov     [rsp+78h+Source], ebx
0x18000c7ca  mov     [rsp+78h+var_4C], bp
0x18000c7cf  lea     rbx, [rdi+0E8h]
0x18000c7d6  mov     rcx, rbx; this
0x18000c7d9  mov     [rsp+78h+var_4A], ax
0x18000c7de  mov     [rsp+78h+var_48], r14d
0x18000c7e3  lea     ebp, [rax+0Ch]
0x18000c7e6  mov     edx, ebp; unsigned __int64
0x18000c7e8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c7ed  test    al, al
0x18000c7ef  jz      short loc_18000C818
0x18000c7f1  mov     rcx, [rbx+8]; Destination
0x18000c7f5  lea     r8, [rsp+78h+Source]; Source
0x18000c7fa  mov     rax, [rbx+10h]
0x18000c7fe  mov     r9d, ebp; SourceSize
0x18000c801  sub     rax, rcx
0x18000c804  cmp     rcx, [rbx+10h]
0x18000c808  sbb     rdx, rdx
0x18000c80b  and     rdx, rax; DestinationSize
0x18000c80e  call    cs:__imp_memcpy_s
0x18000c814  add     [rbx+8], rbp
0x18000c818  cmp     byte ptr [rdi+40h], 0
0x18000c81c  jnz     loc_18000C8C0
0x18000c822  cmp     qword ptr [rdi+38h], 0
0x18000c827  jnz     short loc_18000C896
0x18000c829  call    cs:__imp_GetLastError
0x18000c82f  xor     r8d, r8d; pcbe
0x18000c832  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c839  mov     rdx, rdi; pv
0x18000c83c  mov     r14d, eax
0x18000c83f  call    cs:__imp_CreateThreadpoolTimer
0x18000c845  mov     rbp, [rdi+38h]
0x18000c849  mov     r15, rax
0x18000c84c  test    rbp, rbp
0x18000c84f  jz      short loc_18000C889
0x18000c851  call    cs:__imp_GetLastError
0x18000c857  xor     r9d, r9d; msWindowLength
0x18000c85a  xor     r8d, r8d; msPeriod
0x18000c85d  xor     edx, edx; pftDueTime
0x18000c85f  mov     rcx, rbp; pti
0x18000c862  mov     ebx, eax
0x18000c864  call    cs:__imp_SetThreadpoolTimer
0x18000c86a  mov     edx, 1; fCancelPendingCallbacks
0x18000c86f  mov     rcx, rbp; pti
0x18000c872  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c878  mov     rcx, rbp; pti
0x18000c87b  call    cs:__imp_CloseThreadpoolTimer
0x18000c881  mov     ecx, ebx; dwErrCode
0x18000c883  call    cs:__imp_SetLastError
0x18000c889  mov     ecx, r14d; dwErrCode
0x18000c88c  mov     [rdi+38h], r15
0x18000c890  call    cs:__imp_SetLastError
0x18000c896  mov     rcx, [rdi+38h]; pti
0x18000c89a  test    rcx, rcx
0x18000c89d  jz      short loc_18000C8C0
0x18000c89f  mov     r9d, 4E2h; msWindowLength
0x18000c8a5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c8ae  xor     r8d, r8d; msPeriod
0x18000c8b1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000c8b6  call    cs:__imp_SetThreadpoolTimer
0x18000c8bc  mov     byte ptr [rdi+40h], 1
0x18000c8c0  test    rsi, rsi
0x18000c8c3  jz      short loc_18000C8CE
0x18000c8c5  mov     rcx, rsi; SRWLock
0x18000c8c8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c8ce  mov     rcx, [rsp+78h+var_40]
0x18000c8d3  xor     rcx, rsp; StackCookie
0x18000c8d6  call    __security_check_cookie
0x18000c8db  add     rsp, 48h
0x18000c8df  pop     r15
0x18000c8e1  pop     r14
0x18000c8e3  pop     rdi
0x18000c8e4  pop     rsi
0x18000c8e5  pop     rbp
0x18000c8e6  pop     rbx
0x18000c8e7  retn
```
