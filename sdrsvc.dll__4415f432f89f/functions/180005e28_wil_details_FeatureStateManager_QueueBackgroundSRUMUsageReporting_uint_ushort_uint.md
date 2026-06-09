# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005e28`
- end: `0x180005fb0`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007eb0`

## callees

- `0x180005e28`
- `0x18000847c`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005ed6`
- `msvcrt!memcpy_s` at `0x180005ed6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f43`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005f07`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f7e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f3a`

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
0x180005e28  push    rbx
0x180005e2a  push    rbp
0x180005e2b  push    rsi
0x180005e2c  push    rdi
0x180005e2d  push    r14
0x180005e2f  push    r15
0x180005e31  sub     rsp, 48h
0x180005e35  mov     rax, cs:__security_cookie
0x180005e3c  xor     rax, rsp
0x180005e3f  mov     [rsp+78h+var_40], rax
0x180005e44  cmp     byte ptr [rcx], 0
0x180005e47  mov     r14d, r9d
0x180005e4a  movzx   ebp, r8w
0x180005e4e  mov     ebx, edx
0x180005e50  mov     rdi, rcx
0x180005e53  jz      loc_180005F96
0x180005e59  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005e60  jnz     loc_180005F96
0x180005e66  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005e6d  test    rax, rax
0x180005e70  jz      short loc_180005E7F
0x180005e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e77  test    al, al
0x180005e79  jnz     loc_180005F96
0x180005e7f  lea     rsi, [rdi+28h]
0x180005e83  mov     rcx, rsi; SRWLock
0x180005e86  call    cs:__imp_AcquireSRWLockExclusive
0x180005e8c  xor     eax, eax
0x180005e8e  mov     [rsp+78h+Source], ebx
0x180005e92  mov     [rsp+78h+var_4C], bp
0x180005e97  lea     rbx, [rdi+0E8h]
0x180005e9e  mov     rcx, rbx; this
0x180005ea1  mov     [rsp+78h+var_4A], ax
0x180005ea6  mov     [rsp+78h+var_48], r14d
0x180005eab  lea     ebp, [rax+0Ch]
0x180005eae  mov     edx, ebp; unsigned __int64
0x180005eb0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005eb5  test    al, al
0x180005eb7  jz      short loc_180005EE0
0x180005eb9  mov     rcx, [rbx+8]; Destination
0x180005ebd  lea     r8, [rsp+78h+Source]; Source
0x180005ec2  mov     rax, [rbx+10h]
0x180005ec6  mov     r9d, ebp; SourceSize
0x180005ec9  sub     rax, rcx
0x180005ecc  cmp     rcx, [rbx+10h]
0x180005ed0  sbb     rdx, rdx
0x180005ed3  and     rdx, rax; DestinationSize
0x180005ed6  call    cs:__imp_memcpy_s
0x180005edc  add     [rbx+8], rbp
0x180005ee0  cmp     byte ptr [rdi+40h], 0
0x180005ee4  jnz     loc_180005F88
0x180005eea  cmp     qword ptr [rdi+38h], 0
0x180005eef  jnz     short loc_180005F5E
0x180005ef1  call    cs:__imp_GetLastError
0x180005ef7  xor     r8d, r8d; pcbe
0x180005efa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005f01  mov     rdx, rdi; pv
0x180005f04  mov     r14d, eax
0x180005f07  call    cs:__imp_CreateThreadpoolTimer
0x180005f0d  mov     rbp, [rdi+38h]
0x180005f11  mov     r15, rax
0x180005f14  test    rbp, rbp
0x180005f17  jz      short loc_180005F51
0x180005f19  call    cs:__imp_GetLastError
0x180005f1f  xor     r9d, r9d; msWindowLength
0x180005f22  xor     r8d, r8d; msPeriod
0x180005f25  xor     edx, edx; pftDueTime
0x180005f27  mov     rcx, rbp; pti
0x180005f2a  mov     ebx, eax
0x180005f2c  call    cs:__imp_SetThreadpoolTimer
0x180005f32  mov     edx, 1; fCancelPendingCallbacks
0x180005f37  mov     rcx, rbp; pti
0x180005f3a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005f40  mov     rcx, rbp; pti
0x180005f43  call    cs:__imp_CloseThreadpoolTimer
0x180005f49  mov     ecx, ebx; dwErrCode
0x180005f4b  call    cs:__imp_SetLastError
0x180005f51  mov     ecx, r14d; dwErrCode
0x180005f54  mov     [rdi+38h], r15
0x180005f58  call    cs:__imp_SetLastError
0x180005f5e  mov     rcx, [rdi+38h]; pti
0x180005f62  test    rcx, rcx
0x180005f65  jz      short loc_180005F88
0x180005f67  mov     r9d, 4E2h; msWindowLength
0x180005f6d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005f76  xor     r8d, r8d; msPeriod
0x180005f79  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180005f7e  call    cs:__imp_SetThreadpoolTimer
0x180005f84  mov     byte ptr [rdi+40h], 1
0x180005f88  test    rsi, rsi
0x180005f8b  jz      short loc_180005F96
0x180005f8d  mov     rcx, rsi; SRWLock
0x180005f90  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f96  mov     rcx, [rsp+78h+var_40]
0x180005f9b  xor     rcx, rsp; StackCookie
0x180005f9e  call    __security_check_cookie
0x180005fa3  add     rsp, 48h
0x180005fa7  pop     r15
0x180005fa9  pop     r14
0x180005fab  pop     rdi
0x180005fac  pop     rsi
0x180005fad  pop     rbp
0x180005fae  pop     rbx
0x180005faf  retn
```
