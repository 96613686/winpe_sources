# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000d18c`
- end: `0x18000d327`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ea00`

## callees

- `0x180003d0a`
- `0x180003da4`
- `0x18000d18c`
- `0x18000ee54`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d223`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d24d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d223`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d24d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d29c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d29c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d1dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d1dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d313`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d313`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d2c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d2c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d2af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d301`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d2af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d301`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d2bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d2bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d28a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d28a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18000d18c  push    rbx
0x18000d18e  push    rbp
0x18000d18f  push    rsi
0x18000d190  push    rdi
0x18000d191  push    r14
0x18000d193  push    r15
0x18000d195  sub     rsp, 38h
0x18000d199  mov     ebp, r9d
0x18000d19c  movzx   ebx, r8w
0x18000d1a0  mov     r14d, edx
0x18000d1a3  mov     rdi, rcx
0x18000d1a6  cmp     byte ptr [rcx], 0
0x18000d1a9  jz      loc_18000D31A
0x18000d1af  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d1b6  jnz     loc_18000D31A
0x18000d1bc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d1c3  test    rax, rax
0x18000d1c6  jz      short loc_18000D1D5
0x18000d1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1cd  test    al, al
0x18000d1cf  jnz     loc_18000D31A
0x18000d1d5  lea     rsi, [rdi+28h]
0x18000d1d9  mov     rcx, rsi; SRWLock
0x18000d1dc  call    cs:__imp_AcquireSRWLockExclusive
0x18000d1e2  xor     eax, eax
0x18000d1e4  mov     word ptr [rsp+68h+var_48+6], ax
0x18000d1e9  mov     dword ptr [rsp+68h+var_48], r14d
0x18000d1ee  mov     word ptr [rsp+68h+var_48+4], bx
0x18000d1f3  lea     rbx, [rdi+0E8h]
0x18000d1fa  lea     edx, [rax+0Ch]; unsigned __int64
0x18000d1fd  mov     rcx, rbx; this
0x18000d200  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d205  test    al, al
0x18000d207  jz      short loc_18000D263
0x18000d209  mov     rcx, [rbx+8]; void *
0x18000d20d  mov     rax, [rbx+10h]
0x18000d211  sub     rax, rcx
0x18000d214  cmp     rcx, [rbx+10h]
0x18000d218  sbb     r8, r8
0x18000d21b  and     r8, rax; Size
0x18000d21e  test    rcx, rcx
0x18000d221  jnz     short loc_18000D231
0x18000d223  call    cs:__imp__o__errno
0x18000d229  mov     dword ptr [rax], 16h
0x18000d22f  jmp     short loc_18000D259
0x18000d231  cmp     r8, 0Ch
0x18000d235  jb      short loc_18000D246
0x18000d237  movsd   xmm0, [rsp+68h+var_48]
0x18000d23d  movsd   qword ptr [rcx], xmm0
0x18000d241  mov     [rcx+8], ebp
0x18000d244  jmp     short loc_18000D25E
0x18000d246  xor     edx, edx; Val
0x18000d248  call    memset_0
0x18000d24d  call    cs:__imp__o__errno
0x18000d253  mov     dword ptr [rax], 22h ; '"'
0x18000d259  call    _invalid_parameter_noinfo
0x18000d25e  add     qword ptr [rbx+8], 0Ch
0x18000d263  cmp     byte ptr [rdi+40h], 0
0x18000d267  jnz     loc_18000D30B
0x18000d26d  cmp     qword ptr [rdi+38h], 0
0x18000d272  jnz     short loc_18000D2E1
0x18000d274  call    cs:__imp_GetLastError
0x18000d27a  mov     r14d, eax
0x18000d27d  xor     r8d, r8d; pcbe
0x18000d280  mov     rdx, rdi; pv
0x18000d283  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d28a  call    cs:__imp_CreateThreadpoolTimer
0x18000d290  mov     r15, rax
0x18000d293  mov     rbp, [rdi+38h]
0x18000d297  test    rbp, rbp
0x18000d29a  jz      short loc_18000D2D4
0x18000d29c  call    cs:__imp_GetLastError
0x18000d2a2  mov     ebx, eax
0x18000d2a4  xor     r9d, r9d; msWindowLength
0x18000d2a7  xor     r8d, r8d; msPeriod
0x18000d2aa  xor     edx, edx; pftDueTime
0x18000d2ac  mov     rcx, rbp; pti
0x18000d2af  call    cs:__imp_SetThreadpoolTimer
0x18000d2b5  mov     edx, 1; fCancelPendingCallbacks
0x18000d2ba  mov     rcx, rbp; pti
0x18000d2bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d2c3  mov     rcx, rbp; pti
0x18000d2c6  call    cs:__imp_CloseThreadpoolTimer
0x18000d2cc  mov     ecx, ebx; dwErrCode
0x18000d2ce  call    cs:__imp_SetLastError
0x18000d2d4  mov     [rdi+38h], r15
0x18000d2d8  mov     ecx, r14d; dwErrCode
0x18000d2db  call    cs:__imp_SetLastError
0x18000d2e1  mov     rcx, [rdi+38h]; pti
0x18000d2e5  test    rcx, rcx
0x18000d2e8  jz      short loc_18000D30B
0x18000d2ea  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000d2f3  mov     r9d, 4E2h; msWindowLength
0x18000d2f9  xor     r8d, r8d; msPeriod
0x18000d2fc  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000d301  call    cs:__imp_SetThreadpoolTimer
0x18000d307  mov     byte ptr [rdi+40h], 1
0x18000d30b  test    rsi, rsi
0x18000d30e  jz      short loc_18000D31A
0x18000d310  mov     rcx, rsi; SRWLock
0x18000d313  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d319  nop
0x18000d31a  add     rsp, 38h
0x18000d31e  pop     r15
0x18000d320  pop     r14
0x18000d322  pop     rdi
0x18000d323  pop     rsi
0x18000d324  pop     rbp
0x18000d325  pop     rbx
0x18000d326  retn
```
