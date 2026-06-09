# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a50c`
- end: `0x18000a6a7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ddd0`

## callees

- `0x1800032f2`
- `0x180003384`
- `0x18000a50c`
- `0x18000e8d4`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a5a3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a5cd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a5a3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a5cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a55c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a55c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a693`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a61c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a64e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a65b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a64e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a65b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a60a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a60a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a62f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a681`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a62f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a681`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a63d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a63d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a646`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a646`

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
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v16; // rbp
  DWORD v17; // ebx
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v19) = a2;
  HIDWORD(v19) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v19;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
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
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v16 )
      {
        v17 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v17);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v18 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v18 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18000a50c  push    rbx
0x18000a50e  push    rbp
0x18000a50f  push    rsi
0x18000a510  push    rdi
0x18000a511  push    r14
0x18000a513  push    r15
0x18000a515  sub     rsp, 38h
0x18000a519  mov     ebp, r9d
0x18000a51c  movzx   ebx, r8w
0x18000a520  mov     r14d, edx
0x18000a523  mov     rdi, rcx
0x18000a526  cmp     byte ptr [rcx], 0
0x18000a529  jz      loc_18000A69A
0x18000a52f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a536  jnz     loc_18000A69A
0x18000a53c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a543  test    rax, rax
0x18000a546  jz      short loc_18000A555
0x18000a548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a54d  test    al, al
0x18000a54f  jnz     loc_18000A69A
0x18000a555  lea     rsi, [rdi+28h]
0x18000a559  mov     rcx, rsi; SRWLock
0x18000a55c  call    cs:__imp_AcquireSRWLockExclusive
0x18000a562  xor     eax, eax
0x18000a564  mov     word ptr [rsp+68h+var_48+6], ax
0x18000a569  mov     dword ptr [rsp+68h+var_48], r14d
0x18000a56e  mov     word ptr [rsp+68h+var_48+4], bx
0x18000a573  lea     rbx, [rdi+0E8h]
0x18000a57a  lea     edx, [rax+0Ch]; unsigned __int64
0x18000a57d  mov     rcx, rbx; this
0x18000a580  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a585  test    al, al
0x18000a587  jz      short loc_18000A5E3
0x18000a589  mov     rcx, [rbx+8]; void *
0x18000a58d  mov     rax, [rbx+10h]
0x18000a591  sub     rax, rcx
0x18000a594  cmp     rcx, [rbx+10h]
0x18000a598  sbb     r8, r8
0x18000a59b  and     r8, rax; Size
0x18000a59e  test    rcx, rcx
0x18000a5a1  jnz     short loc_18000A5B1
0x18000a5a3  call    cs:__imp__o__errno
0x18000a5a9  mov     dword ptr [rax], 16h
0x18000a5af  jmp     short loc_18000A5D9
0x18000a5b1  cmp     r8, 0Ch
0x18000a5b5  jb      short loc_18000A5C6
0x18000a5b7  movsd   xmm0, [rsp+68h+var_48]
0x18000a5bd  movsd   qword ptr [rcx], xmm0
0x18000a5c1  mov     [rcx+8], ebp
0x18000a5c4  jmp     short loc_18000A5DE
0x18000a5c6  xor     edx, edx; Val
0x18000a5c8  call    memset_0
0x18000a5cd  call    cs:__imp__o__errno
0x18000a5d3  mov     dword ptr [rax], 22h ; '"'
0x18000a5d9  call    _invalid_parameter_noinfo
0x18000a5de  add     qword ptr [rbx+8], 0Ch
0x18000a5e3  cmp     byte ptr [rdi+40h], 0
0x18000a5e7  jnz     loc_18000A68B
0x18000a5ed  cmp     qword ptr [rdi+38h], 0
0x18000a5f2  jnz     short loc_18000A661
0x18000a5f4  call    cs:__imp_GetLastError
0x18000a5fa  mov     r14d, eax
0x18000a5fd  xor     r8d, r8d; pcbe
0x18000a600  mov     rdx, rdi; pv
0x18000a603  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a60a  call    cs:__imp_CreateThreadpoolTimer
0x18000a610  mov     r15, rax
0x18000a613  mov     rbp, [rdi+38h]
0x18000a617  test    rbp, rbp
0x18000a61a  jz      short loc_18000A654
0x18000a61c  call    cs:__imp_GetLastError
0x18000a622  mov     ebx, eax
0x18000a624  xor     r9d, r9d; msWindowLength
0x18000a627  xor     r8d, r8d; msPeriod
0x18000a62a  xor     edx, edx; pftDueTime
0x18000a62c  mov     rcx, rbp; pti
0x18000a62f  call    cs:__imp_SetThreadpoolTimer
0x18000a635  mov     edx, 1; fCancelPendingCallbacks
0x18000a63a  mov     rcx, rbp; pti
0x18000a63d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a643  mov     rcx, rbp; pti
0x18000a646  call    cs:__imp_CloseThreadpoolTimer
0x18000a64c  mov     ecx, ebx; dwErrCode
0x18000a64e  call    cs:__imp_SetLastError
0x18000a654  mov     [rdi+38h], r15
0x18000a658  mov     ecx, r14d; dwErrCode
0x18000a65b  call    cs:__imp_SetLastError
0x18000a661  mov     rcx, [rdi+38h]; pti
0x18000a665  test    rcx, rcx
0x18000a668  jz      short loc_18000A68B
0x18000a66a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a673  mov     r9d, 4E2h; msWindowLength
0x18000a679  xor     r8d, r8d; msPeriod
0x18000a67c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000a681  call    cs:__imp_SetThreadpoolTimer
0x18000a687  mov     byte ptr [rdi+40h], 1
0x18000a68b  test    rsi, rsi
0x18000a68e  jz      short loc_18000A69A
0x18000a690  mov     rcx, rsi; SRWLock
0x18000a693  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a699  nop
0x18000a69a  add     rsp, 38h
0x18000a69e  pop     r15
0x18000a6a0  pop     r14
0x18000a6a2  pop     rdi
0x18000a6a3  pop     rsi
0x18000a6a4  pop     rbp
0x18000a6a5  pop     rbx
0x18000a6a6  retn
```
