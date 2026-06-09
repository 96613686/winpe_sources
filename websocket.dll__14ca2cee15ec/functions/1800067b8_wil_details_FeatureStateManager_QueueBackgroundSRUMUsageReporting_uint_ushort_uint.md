# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800067b8`
- end: `0x18000693f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `391`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800087d0`

## callees

- `0x180001670`
- `0x180001f8c`
- `0x1800067b8`
- `0x180008d9c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006816`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006816`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000691f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000691f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000690d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000690d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006896`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006896`

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
0x1800067b8  push    rbx
0x1800067ba  push    rbp
0x1800067bb  push    rsi
0x1800067bc  push    rdi
0x1800067bd  push    r14
0x1800067bf  push    r15
0x1800067c1  sub     rsp, 48h
0x1800067c5  mov     rax, cs:__security_cookie
0x1800067cc  xor     rax, rsp
0x1800067cf  mov     [rsp+78h+var_40], rax
0x1800067d4  cmp     byte ptr [rcx], 0
0x1800067d7  mov     r14d, r9d
0x1800067da  movzx   ebp, r8w
0x1800067de  mov     ebx, edx
0x1800067e0  mov     rdi, rcx
0x1800067e3  jz      loc_180006925
0x1800067e9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800067f0  jnz     loc_180006925
0x1800067f6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800067fd  test    rax, rax
0x180006800  jz      short loc_18000680F
0x180006802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006807  test    al, al
0x180006809  jnz     loc_180006925
0x18000680f  lea     rsi, [rdi+28h]
0x180006813  mov     rcx, rsi; SRWLock
0x180006816  call    cs:__imp_AcquireSRWLockExclusive
0x18000681c  xor     eax, eax
0x18000681e  mov     [rsp+78h+Source], ebx
0x180006822  mov     [rsp+78h+var_4C], bp
0x180006827  lea     rbx, [rdi+0E8h]
0x18000682e  mov     rcx, rbx; this
0x180006831  mov     [rsp+78h+var_4A], ax
0x180006836  mov     [rsp+78h+var_48], r14d
0x18000683b  lea     ebp, [rax+0Ch]
0x18000683e  mov     edx, ebp; unsigned __int64
0x180006840  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006845  test    al, al
0x180006847  jz      short loc_18000686F
0x180006849  mov     rcx, [rbx+8]; Destination
0x18000684d  lea     r8, [rsp+78h+Source]; Source
0x180006852  mov     rax, [rbx+10h]
0x180006856  mov     r9d, ebp; SourceSize
0x180006859  sub     rax, rcx
0x18000685c  cmp     rcx, [rbx+10h]
0x180006860  sbb     rdx, rdx
0x180006863  and     rdx, rax; DestinationSize
0x180006866  call    memcpy_s
0x18000686b  add     [rbx+8], rbp
0x18000686f  cmp     byte ptr [rdi+40h], 0
0x180006873  jnz     loc_180006917
0x180006879  cmp     qword ptr [rdi+38h], 0
0x18000687e  jnz     short loc_1800068ED
0x180006880  call    cs:__imp_GetLastError
0x180006886  xor     r8d, r8d; pcbe
0x180006889  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006890  mov     rdx, rdi; pv
0x180006893  mov     r14d, eax
0x180006896  call    cs:__imp_CreateThreadpoolTimer
0x18000689c  mov     rbp, [rdi+38h]
0x1800068a0  mov     r15, rax
0x1800068a3  test    rbp, rbp
0x1800068a6  jz      short loc_1800068E0
0x1800068a8  call    cs:__imp_GetLastError
0x1800068ae  xor     r9d, r9d; msWindowLength
0x1800068b1  xor     r8d, r8d; msPeriod
0x1800068b4  xor     edx, edx; pftDueTime
0x1800068b6  mov     rcx, rbp; pti
0x1800068b9  mov     ebx, eax
0x1800068bb  call    cs:__imp_SetThreadpoolTimer
0x1800068c1  mov     edx, 1; fCancelPendingCallbacks
0x1800068c6  mov     rcx, rbp; pti
0x1800068c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068cf  mov     rcx, rbp; pti
0x1800068d2  call    cs:__imp_CloseThreadpoolTimer
0x1800068d8  mov     ecx, ebx; dwErrCode
0x1800068da  call    cs:__imp_SetLastError
0x1800068e0  mov     ecx, r14d; dwErrCode
0x1800068e3  mov     [rdi+38h], r15
0x1800068e7  call    cs:__imp_SetLastError
0x1800068ed  mov     rcx, [rdi+38h]; pti
0x1800068f1  test    rcx, rcx
0x1800068f4  jz      short loc_180006917
0x1800068f6  mov     r9d, 4E2h; msWindowLength
0x1800068fc  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006905  xor     r8d, r8d; msPeriod
0x180006908  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000690d  call    cs:__imp_SetThreadpoolTimer
0x180006913  mov     byte ptr [rdi+40h], 1
0x180006917  test    rsi, rsi
0x18000691a  jz      short loc_180006925
0x18000691c  mov     rcx, rsi; SRWLock
0x18000691f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006925  mov     rcx, [rsp+78h+var_40]
0x18000692a  xor     rcx, rsp; StackCookie
0x18000692d  call    __security_check_cookie
0x180006932  add     rsp, 48h
0x180006936  pop     r15
0x180006938  pop     r14
0x18000693a  pop     rdi
0x18000693b  pop     rsi
0x18000693c  pop     rbp
0x18000693d  pop     rbx
0x18000693e  retn
```
