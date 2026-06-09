# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180043560`
- end: `0x1800436fb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180050b80`

## callees

- `0x1800033f2`
- `0x18000346c`
- `0x180043560`
- `0x180057284`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800435f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043621`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800435f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043621`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800436e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800436e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800435b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800435b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043670`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004369a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004369a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043691`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043691`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004365e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004365e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043683`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800436d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043683`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800436d5`

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
0x180043560  push    rbx
0x180043562  push    rbp
0x180043563  push    rsi
0x180043564  push    rdi
0x180043565  push    r14
0x180043567  push    r15
0x180043569  sub     rsp, 38h
0x18004356d  mov     ebp, r9d
0x180043570  movzx   ebx, r8w
0x180043574  mov     r14d, edx
0x180043577  mov     rdi, rcx
0x18004357a  cmp     byte ptr [rcx], 0
0x18004357d  jz      loc_1800436EE
0x180043583  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004358a  jnz     loc_1800436EE
0x180043590  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180043597  test    rax, rax
0x18004359a  jz      short loc_1800435A9
0x18004359c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435a1  test    al, al
0x1800435a3  jnz     loc_1800436EE
0x1800435a9  lea     rsi, [rdi+28h]
0x1800435ad  mov     rcx, rsi; SRWLock
0x1800435b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800435b6  xor     eax, eax
0x1800435b8  mov     word ptr [rsp+68h+var_48+6], ax
0x1800435bd  mov     dword ptr [rsp+68h+var_48], r14d
0x1800435c2  mov     word ptr [rsp+68h+var_48+4], bx
0x1800435c7  lea     rbx, [rdi+0E8h]
0x1800435ce  lea     edx, [rax+0Ch]; unsigned __int64
0x1800435d1  mov     rcx, rbx; this
0x1800435d4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800435d9  test    al, al
0x1800435db  jz      short loc_180043637
0x1800435dd  mov     rcx, [rbx+8]; void *
0x1800435e1  mov     rax, [rbx+10h]
0x1800435e5  sub     rax, rcx
0x1800435e8  cmp     rcx, [rbx+10h]
0x1800435ec  sbb     r8, r8
0x1800435ef  and     r8, rax; Size
0x1800435f2  test    rcx, rcx
0x1800435f5  jnz     short loc_180043605
0x1800435f7  call    cs:__imp__o__errno
0x1800435fd  mov     dword ptr [rax], 16h
0x180043603  jmp     short loc_18004362D
0x180043605  cmp     r8, 0Ch
0x180043609  jb      short loc_18004361A
0x18004360b  movsd   xmm0, [rsp+68h+var_48]
0x180043611  movsd   qword ptr [rcx], xmm0
0x180043615  mov     [rcx+8], ebp
0x180043618  jmp     short loc_180043632
0x18004361a  xor     edx, edx; Val
0x18004361c  call    memset_0
0x180043621  call    cs:__imp__o__errno
0x180043627  mov     dword ptr [rax], 22h ; '"'
0x18004362d  call    _invalid_parameter_noinfo
0x180043632  add     qword ptr [rbx+8], 0Ch
0x180043637  cmp     byte ptr [rdi+40h], 0
0x18004363b  jnz     loc_1800436DF
0x180043641  cmp     qword ptr [rdi+38h], 0
0x180043646  jnz     short loc_1800436B5
0x180043648  call    cs:__imp_GetLastError
0x18004364e  mov     r14d, eax
0x180043651  xor     r8d, r8d; pcbe
0x180043654  mov     rdx, rdi; pv
0x180043657  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004365e  call    cs:__imp_CreateThreadpoolTimer
0x180043664  mov     r15, rax
0x180043667  mov     rbp, [rdi+38h]
0x18004366b  test    rbp, rbp
0x18004366e  jz      short loc_1800436A8
0x180043670  call    cs:__imp_GetLastError
0x180043676  mov     ebx, eax
0x180043678  xor     r9d, r9d; msWindowLength
0x18004367b  xor     r8d, r8d; msPeriod
0x18004367e  xor     edx, edx; pftDueTime
0x180043680  mov     rcx, rbp; pti
0x180043683  call    cs:__imp_SetThreadpoolTimer
0x180043689  mov     edx, 1; fCancelPendingCallbacks
0x18004368e  mov     rcx, rbp; pti
0x180043691  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180043697  mov     rcx, rbp; pti
0x18004369a  call    cs:__imp_CloseThreadpoolTimer
0x1800436a0  mov     ecx, ebx; dwErrCode
0x1800436a2  call    cs:__imp_SetLastError
0x1800436a8  mov     [rdi+38h], r15
0x1800436ac  mov     ecx, r14d; dwErrCode
0x1800436af  call    cs:__imp_SetLastError
0x1800436b5  mov     rcx, [rdi+38h]; pti
0x1800436b9  test    rcx, rcx
0x1800436bc  jz      short loc_1800436DF
0x1800436be  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800436c7  mov     r9d, 4E2h; msWindowLength
0x1800436cd  xor     r8d, r8d; msPeriod
0x1800436d0  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800436d5  call    cs:__imp_SetThreadpoolTimer
0x1800436db  mov     byte ptr [rdi+40h], 1
0x1800436df  test    rsi, rsi
0x1800436e2  jz      short loc_1800436EE
0x1800436e4  mov     rcx, rsi; SRWLock
0x1800436e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800436ed  nop
0x1800436ee  add     rsp, 38h
0x1800436f2  pop     r15
0x1800436f4  pop     r14
0x1800436f6  pop     rdi
0x1800436f7  pop     rsi
0x1800436f8  pop     rbp
0x1800436f9  pop     rbx
0x1800436fa  retn
```
