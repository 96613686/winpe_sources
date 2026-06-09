# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180030fc8`
- end: `0x180031151`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180033d40`

## callees

- `0x180030fc8`
- `0x18003459c`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180031076`
- `msvcrt!memcpy_s` at `0x180031076`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031130`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031026`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031026`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800310a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800310a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800310e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800310e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800310cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003111e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800310cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003111e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800310da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800310da`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
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
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
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
0x180030fc8  push    rbx
0x180030fca  push    rbp
0x180030fcb  push    rsi
0x180030fcc  push    rdi
0x180030fcd  push    r14
0x180030fcf  push    r15
0x180030fd1  sub     rsp, 48h
0x180030fd5  mov     rax, cs:__security_cookie
0x180030fdc  xor     rax, rsp
0x180030fdf  mov     [rsp+78h+var_40], rax
0x180030fe4  mov     r14d, r9d
0x180030fe7  movzx   ebp, r8w
0x180030feb  mov     ebx, edx
0x180030fed  mov     rdi, rcx
0x180030ff0  cmp     byte ptr [rcx], 0
0x180030ff3  jz      loc_180031137
0x180030ff9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180031000  jnz     loc_180031137
0x180031006  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003100d  test    rax, rax
0x180031010  jz      short loc_18003101F
0x180031012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031017  test    al, al
0x180031019  jnz     loc_180031137
0x18003101f  lea     rsi, [rdi+28h]
0x180031023  mov     rcx, rsi; SRWLock
0x180031026  call    cs:__imp_AcquireSRWLockExclusive
0x18003102c  xor     eax, eax
0x18003102e  mov     [rsp+78h+var_4A], ax
0x180031033  mov     [rsp+78h+Source], ebx
0x180031037  mov     [rsp+78h+var_4C], bp
0x18003103c  mov     [rsp+78h+var_48], r14d
0x180031041  lea     rbx, [rdi+0E8h]
0x180031048  lea     ebp, [rax+0Ch]
0x18003104b  mov     edx, ebp; unsigned __int64
0x18003104d  mov     rcx, rbx; this
0x180031050  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180031055  test    al, al
0x180031057  jz      short loc_180031080
0x180031059  mov     rcx, [rbx+8]; Destination
0x18003105d  mov     rax, [rbx+10h]
0x180031061  sub     rax, rcx
0x180031064  cmp     rcx, [rbx+10h]
0x180031068  sbb     rdx, rdx
0x18003106b  and     rdx, rax; DestinationSize
0x18003106e  mov     r9d, ebp; SourceSize
0x180031071  lea     r8, [rsp+78h+Source]; Source
0x180031076  call    cs:__imp_memcpy_s
0x18003107c  add     [rbx+8], rbp
0x180031080  cmp     byte ptr [rdi+40h], 0
0x180031084  jnz     loc_180031128
0x18003108a  cmp     qword ptr [rdi+38h], 0
0x18003108f  jnz     short loc_1800310FE
0x180031091  call    cs:__imp_GetLastError
0x180031097  mov     r14d, eax
0x18003109a  xor     r8d, r8d; pcbe
0x18003109d  mov     rdx, rdi; pv
0x1800310a0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800310a7  call    cs:__imp_CreateThreadpoolTimer
0x1800310ad  mov     r15, rax
0x1800310b0  mov     rbp, [rdi+38h]
0x1800310b4  test    rbp, rbp
0x1800310b7  jz      short loc_1800310F1
0x1800310b9  call    cs:__imp_GetLastError
0x1800310bf  mov     ebx, eax
0x1800310c1  xor     r9d, r9d; msWindowLength
0x1800310c4  xor     r8d, r8d; msPeriod
0x1800310c7  xor     edx, edx; pftDueTime
0x1800310c9  mov     rcx, rbp; pti
0x1800310cc  call    cs:__imp_SetThreadpoolTimer
0x1800310d2  mov     edx, 1; fCancelPendingCallbacks
0x1800310d7  mov     rcx, rbp; pti
0x1800310da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800310e0  mov     rcx, rbp; pti
0x1800310e3  call    cs:__imp_CloseThreadpoolTimer
0x1800310e9  mov     ecx, ebx; dwErrCode
0x1800310eb  call    cs:__imp_SetLastError
0x1800310f1  mov     [rdi+38h], r15
0x1800310f5  mov     ecx, r14d; dwErrCode
0x1800310f8  call    cs:__imp_SetLastError
0x1800310fe  mov     rcx, [rdi+38h]; pti
0x180031102  test    rcx, rcx
0x180031105  jz      short loc_180031128
0x180031107  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180031110  mov     r9d, 4E2h; msWindowLength
0x180031116  xor     r8d, r8d; msPeriod
0x180031119  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18003111e  call    cs:__imp_SetThreadpoolTimer
0x180031124  mov     byte ptr [rdi+40h], 1
0x180031128  test    rsi, rsi
0x18003112b  jz      short loc_180031137
0x18003112d  mov     rcx, rsi; SRWLock
0x180031130  call    cs:__imp_ReleaseSRWLockExclusive
0x180031136  nop
0x180031137  mov     rcx, [rsp+78h+var_40]
0x18003113c  xor     rcx, rsp; StackCookie
0x18003113f  call    __security_check_cookie
0x180031144  add     rsp, 48h
0x180031148  pop     r15
0x18003114a  pop     r14
0x18003114c  pop     rdi
0x18003114d  pop     rsi
0x18003114e  pop     rbp
0x18003114f  pop     rbx
0x180031150  retn
```
