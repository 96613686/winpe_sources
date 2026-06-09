# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000c420`
- end: `0x18000c5bb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000dc00`

## callees

- `0x18000313a`
- `0x180003198`
- `0x18000c420`
- `0x18000dfc4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c470`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c470`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c5a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c5a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c56f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c530`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c55a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c55a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c551`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c551`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c51e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c51e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c543`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c595`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c543`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c595`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18000c420  push    rbx
0x18000c422  push    rbp
0x18000c423  push    rsi
0x18000c424  push    rdi
0x18000c425  push    r14
0x18000c427  push    r15
0x18000c429  sub     rsp, 38h
0x18000c42d  mov     ebp, r9d
0x18000c430  movzx   ebx, r8w
0x18000c434  mov     r14d, edx
0x18000c437  mov     rdi, rcx
0x18000c43a  cmp     byte ptr [rcx], 0
0x18000c43d  jz      loc_18000C5AE
0x18000c443  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c44a  jnz     loc_18000C5AE
0x18000c450  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c457  test    rax, rax
0x18000c45a  jz      short loc_18000C469
0x18000c45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c461  test    al, al
0x18000c463  jnz     loc_18000C5AE
0x18000c469  lea     rsi, [rdi+28h]
0x18000c46d  mov     rcx, rsi; SRWLock
0x18000c470  call    cs:__imp_AcquireSRWLockExclusive
0x18000c476  xor     eax, eax
0x18000c478  mov     word ptr [rsp+68h+var_48+6], ax
0x18000c47d  mov     dword ptr [rsp+68h+var_48], r14d
0x18000c482  mov     word ptr [rsp+68h+var_48+4], bx
0x18000c487  lea     rbx, [rdi+0E8h]
0x18000c48e  lea     edx, [rax+0Ch]; unsigned __int64
0x18000c491  mov     rcx, rbx; this
0x18000c494  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c499  test    al, al
0x18000c49b  jz      short loc_18000C4F7
0x18000c49d  mov     rcx, [rbx+8]; void *
0x18000c4a1  mov     rax, [rbx+10h]
0x18000c4a5  sub     rax, rcx
0x18000c4a8  cmp     rcx, [rbx+10h]
0x18000c4ac  sbb     r8, r8
0x18000c4af  and     r8, rax; Size
0x18000c4b2  test    rcx, rcx
0x18000c4b5  jnz     short loc_18000C4C5
0x18000c4b7  call    cs:__imp__o__errno
0x18000c4bd  mov     dword ptr [rax], 16h
0x18000c4c3  jmp     short loc_18000C4ED
0x18000c4c5  cmp     r8, 0Ch
0x18000c4c9  jb      short loc_18000C4DA
0x18000c4cb  movsd   xmm0, [rsp+68h+var_48]
0x18000c4d1  movsd   qword ptr [rcx], xmm0
0x18000c4d5  mov     [rcx+8], ebp
0x18000c4d8  jmp     short loc_18000C4F2
0x18000c4da  xor     edx, edx; Val
0x18000c4dc  call    memset_0
0x18000c4e1  call    cs:__imp__o__errno
0x18000c4e7  mov     dword ptr [rax], 22h ; '"'
0x18000c4ed  call    _invalid_parameter_noinfo
0x18000c4f2  add     qword ptr [rbx+8], 0Ch
0x18000c4f7  cmp     byte ptr [rdi+40h], 0
0x18000c4fb  jnz     loc_18000C59F
0x18000c501  cmp     qword ptr [rdi+38h], 0
0x18000c506  jnz     short loc_18000C575
0x18000c508  call    cs:__imp_GetLastError
0x18000c50e  mov     r14d, eax
0x18000c511  xor     r8d, r8d; pcbe
0x18000c514  mov     rdx, rdi; pv
0x18000c517  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c51e  call    cs:__imp_CreateThreadpoolTimer
0x18000c524  mov     r15, rax
0x18000c527  mov     rbp, [rdi+38h]
0x18000c52b  test    rbp, rbp
0x18000c52e  jz      short loc_18000C568
0x18000c530  call    cs:__imp_GetLastError
0x18000c536  mov     ebx, eax
0x18000c538  xor     r9d, r9d; msWindowLength
0x18000c53b  xor     r8d, r8d; msPeriod
0x18000c53e  xor     edx, edx; pftDueTime
0x18000c540  mov     rcx, rbp; pti
0x18000c543  call    cs:__imp_SetThreadpoolTimer
0x18000c549  mov     edx, 1; fCancelPendingCallbacks
0x18000c54e  mov     rcx, rbp; pti
0x18000c551  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c557  mov     rcx, rbp; pti
0x18000c55a  call    cs:__imp_CloseThreadpoolTimer
0x18000c560  mov     ecx, ebx; dwErrCode
0x18000c562  call    cs:__imp_SetLastError
0x18000c568  mov     [rdi+38h], r15
0x18000c56c  mov     ecx, r14d; dwErrCode
0x18000c56f  call    cs:__imp_SetLastError
0x18000c575  mov     rcx, [rdi+38h]; pti
0x18000c579  test    rcx, rcx
0x18000c57c  jz      short loc_18000C59F
0x18000c57e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c587  mov     r9d, 4E2h; msWindowLength
0x18000c58d  xor     r8d, r8d; msPeriod
0x18000c590  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000c595  call    cs:__imp_SetThreadpoolTimer
0x18000c59b  mov     byte ptr [rdi+40h], 1
0x18000c59f  test    rsi, rsi
0x18000c5a2  jz      short loc_18000C5AE
0x18000c5a4  mov     rcx, rsi; SRWLock
0x18000c5a7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c5ad  nop
0x18000c5ae  add     rsp, 38h
0x18000c5b2  pop     r15
0x18000c5b4  pop     r14
0x18000c5b6  pop     rdi
0x18000c5b7  pop     rsi
0x18000c5b8  pop     rbp
0x18000c5b9  pop     rbx
0x18000c5ba  retn
```
