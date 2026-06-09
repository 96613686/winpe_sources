# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400077ec`
- end: `0x140007974`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140009b30`

## callees

- `0x1400077ec`
- `0x14000a09c`
- `0x14000d1f0`
- `0x14000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000789a`
- `msvcrt!memcpy_s` at `0x14000789a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400078cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400078cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400078f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007942`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400078f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007942`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400078fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400078fe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007907`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007907`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000790f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000791c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000790f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000791c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007954`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007954`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000784a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000784a`

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
0x1400077ec  push    rbx
0x1400077ee  push    rbp
0x1400077ef  push    rsi
0x1400077f0  push    rdi
0x1400077f1  push    r14
0x1400077f3  push    r15
0x1400077f5  sub     rsp, 48h
0x1400077f9  mov     rax, cs:__security_cookie
0x140007800  xor     rax, rsp
0x140007803  mov     [rsp+78h+var_40], rax
0x140007808  cmp     byte ptr [rcx], 0
0x14000780b  mov     r14d, r9d
0x14000780e  movzx   ebp, r8w
0x140007812  mov     ebx, edx
0x140007814  mov     rdi, rcx
0x140007817  jz      loc_14000795A
0x14000781d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007824  jnz     loc_14000795A
0x14000782a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007831  test    rax, rax
0x140007834  jz      short loc_140007843
0x140007836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000783b  test    al, al
0x14000783d  jnz     loc_14000795A
0x140007843  lea     rsi, [rdi+28h]
0x140007847  mov     rcx, rsi; SRWLock
0x14000784a  call    cs:__imp_AcquireSRWLockExclusive
0x140007850  xor     eax, eax
0x140007852  mov     [rsp+78h+Source], ebx
0x140007856  mov     [rsp+78h+var_4C], bp
0x14000785b  lea     rbx, [rdi+0E8h]
0x140007862  mov     rcx, rbx; this
0x140007865  mov     [rsp+78h+var_4A], ax
0x14000786a  mov     [rsp+78h+var_48], r14d
0x14000786f  lea     ebp, [rax+0Ch]
0x140007872  mov     edx, ebp; unsigned __int64
0x140007874  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007879  test    al, al
0x14000787b  jz      short loc_1400078A4
0x14000787d  mov     rcx, [rbx+8]; Destination
0x140007881  lea     r8, [rsp+78h+Source]; Source
0x140007886  mov     rax, [rbx+10h]
0x14000788a  mov     r9d, ebp; SourceSize
0x14000788d  sub     rax, rcx
0x140007890  cmp     rcx, [rbx+10h]
0x140007894  sbb     rdx, rdx
0x140007897  and     rdx, rax; DestinationSize
0x14000789a  call    cs:__imp_memcpy_s
0x1400078a0  add     [rbx+8], rbp
0x1400078a4  cmp     byte ptr [rdi+40h], 0
0x1400078a8  jnz     loc_14000794C
0x1400078ae  cmp     qword ptr [rdi+38h], 0
0x1400078b3  jnz     short loc_140007922
0x1400078b5  call    cs:__imp_GetLastError
0x1400078bb  xor     r8d, r8d; pcbe
0x1400078be  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400078c5  mov     rdx, rdi; pv
0x1400078c8  mov     r14d, eax
0x1400078cb  call    cs:__imp_CreateThreadpoolTimer
0x1400078d1  mov     rbp, [rdi+38h]
0x1400078d5  mov     r15, rax
0x1400078d8  test    rbp, rbp
0x1400078db  jz      short loc_140007915
0x1400078dd  call    cs:__imp_GetLastError
0x1400078e3  xor     r9d, r9d; msWindowLength
0x1400078e6  xor     r8d, r8d; msPeriod
0x1400078e9  xor     edx, edx; pftDueTime
0x1400078eb  mov     rcx, rbp; pti
0x1400078ee  mov     ebx, eax
0x1400078f0  call    cs:__imp_SetThreadpoolTimer
0x1400078f6  mov     edx, 1; fCancelPendingCallbacks
0x1400078fb  mov     rcx, rbp; pti
0x1400078fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007904  mov     rcx, rbp; pti
0x140007907  call    cs:__imp_CloseThreadpoolTimer
0x14000790d  mov     ecx, ebx; dwErrCode
0x14000790f  call    cs:__imp_SetLastError
0x140007915  mov     ecx, r14d; dwErrCode
0x140007918  mov     [rdi+38h], r15
0x14000791c  call    cs:__imp_SetLastError
0x140007922  mov     rcx, [rdi+38h]; pti
0x140007926  test    rcx, rcx
0x140007929  jz      short loc_14000794C
0x14000792b  mov     r9d, 4E2h; msWindowLength
0x140007931  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000793a  xor     r8d, r8d; msPeriod
0x14000793d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x140007942  call    cs:__imp_SetThreadpoolTimer
0x140007948  mov     byte ptr [rdi+40h], 1
0x14000794c  test    rsi, rsi
0x14000794f  jz      short loc_14000795A
0x140007951  mov     rcx, rsi; SRWLock
0x140007954  call    cs:__imp_ReleaseSRWLockExclusive
0x14000795a  mov     rcx, [rsp+78h+var_40]
0x14000795f  xor     rcx, rsp; StackCookie
0x140007962  call    __security_check_cookie
0x140007967  add     rsp, 48h
0x14000796b  pop     r15
0x14000796d  pop     r14
0x14000796f  pop     rdi
0x140007970  pop     rsi
0x140007971  pop     rbp
0x140007972  pop     rbx
0x140007973  retn
```
