# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001b1b0`
- end: `0x18001b338`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001c980`

## callees

- `0x180019328`
- `0x18001b1b0`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001b25e`
- `msvcrt!memcpy_s` at `0x18001b25e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b318`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b318`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b20e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b20e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b2cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b2cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b2c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b2c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b2b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b306`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b2b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b306`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b28f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b28f`

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
0x18001b1b0  push    rbx
0x18001b1b2  push    rbp
0x18001b1b3  push    rsi
0x18001b1b4  push    rdi
0x18001b1b5  push    r14
0x18001b1b7  push    r15
0x18001b1b9  sub     rsp, 48h
0x18001b1bd  mov     rax, cs:__security_cookie
0x18001b1c4  xor     rax, rsp
0x18001b1c7  mov     [rsp+78h+var_40], rax
0x18001b1cc  cmp     byte ptr [rcx], 0
0x18001b1cf  mov     r14d, r9d
0x18001b1d2  movzx   ebp, r8w
0x18001b1d6  mov     ebx, edx
0x18001b1d8  mov     rdi, rcx
0x18001b1db  jz      loc_18001B31E
0x18001b1e1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001b1e8  jnz     loc_18001B31E
0x18001b1ee  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001b1f5  test    rax, rax
0x18001b1f8  jz      short loc_18001B207
0x18001b1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ff  test    al, al
0x18001b201  jnz     loc_18001B31E
0x18001b207  lea     rsi, [rdi+28h]
0x18001b20b  mov     rcx, rsi; SRWLock
0x18001b20e  call    cs:__imp_AcquireSRWLockExclusive
0x18001b214  xor     eax, eax
0x18001b216  mov     [rsp+78h+Source], ebx
0x18001b21a  mov     [rsp+78h+var_4C], bp
0x18001b21f  lea     rbx, [rdi+0E8h]
0x18001b226  mov     rcx, rbx; this
0x18001b229  mov     [rsp+78h+var_4A], ax
0x18001b22e  mov     [rsp+78h+var_48], r14d
0x18001b233  lea     ebp, [rax+0Ch]
0x18001b236  mov     edx, ebp; unsigned __int64
0x18001b238  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001b23d  test    al, al
0x18001b23f  jz      short loc_18001B268
0x18001b241  mov     rcx, [rbx+8]; Destination
0x18001b245  lea     r8, [rsp+78h+Source]; Source
0x18001b24a  mov     rax, [rbx+10h]
0x18001b24e  mov     r9d, ebp; SourceSize
0x18001b251  sub     rax, rcx
0x18001b254  cmp     rcx, [rbx+10h]
0x18001b258  sbb     rdx, rdx
0x18001b25b  and     rdx, rax; DestinationSize
0x18001b25e  call    cs:__imp_memcpy_s
0x18001b264  add     [rbx+8], rbp
0x18001b268  cmp     byte ptr [rdi+40h], 0
0x18001b26c  jnz     loc_18001B310
0x18001b272  cmp     qword ptr [rdi+38h], 0
0x18001b277  jnz     short loc_18001B2E6
0x18001b279  call    cs:__imp_GetLastError
0x18001b27f  xor     r8d, r8d; pcbe
0x18001b282  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b289  mov     rdx, rdi; pv
0x18001b28c  mov     r14d, eax
0x18001b28f  call    cs:__imp_CreateThreadpoolTimer
0x18001b295  mov     rbp, [rdi+38h]
0x18001b299  mov     r15, rax
0x18001b29c  test    rbp, rbp
0x18001b29f  jz      short loc_18001B2D9
0x18001b2a1  call    cs:__imp_GetLastError
0x18001b2a7  xor     r9d, r9d; msWindowLength
0x18001b2aa  xor     r8d, r8d; msPeriod
0x18001b2ad  xor     edx, edx; pftDueTime
0x18001b2af  mov     rcx, rbp; pti
0x18001b2b2  mov     ebx, eax
0x18001b2b4  call    cs:__imp_SetThreadpoolTimer
0x18001b2ba  mov     edx, 1; fCancelPendingCallbacks
0x18001b2bf  mov     rcx, rbp; pti
0x18001b2c2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b2c8  mov     rcx, rbp; pti
0x18001b2cb  call    cs:__imp_CloseThreadpoolTimer
0x18001b2d1  mov     ecx, ebx; dwErrCode
0x18001b2d3  call    cs:__imp_SetLastError
0x18001b2d9  mov     ecx, r14d; dwErrCode
0x18001b2dc  mov     [rdi+38h], r15
0x18001b2e0  call    cs:__imp_SetLastError
0x18001b2e6  mov     rcx, [rdi+38h]; pti
0x18001b2ea  test    rcx, rcx
0x18001b2ed  jz      short loc_18001B310
0x18001b2ef  mov     r9d, 4E2h; msWindowLength
0x18001b2f5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001b2fe  xor     r8d, r8d; msPeriod
0x18001b301  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18001b306  call    cs:__imp_SetThreadpoolTimer
0x18001b30c  mov     byte ptr [rdi+40h], 1
0x18001b310  test    rsi, rsi
0x18001b313  jz      short loc_18001B31E
0x18001b315  mov     rcx, rsi; SRWLock
0x18001b318  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b31e  mov     rcx, [rsp+78h+var_40]
0x18001b323  xor     rcx, rsp; StackCookie
0x18001b326  call    __security_check_cookie
0x18001b32b  add     rsp, 48h
0x18001b32f  pop     r15
0x18001b331  pop     r14
0x18001b333  pop     rdi
0x18001b334  pop     rsi
0x18001b335  pop     rbp
0x18001b336  pop     rbx
0x18001b337  retn
```
