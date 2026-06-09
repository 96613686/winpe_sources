# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001291c`
- end: `0x180012aa4`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800144b0`

## callees

- `0x18001291c`
- `0x180014a04`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800129ca`
- `msvcrt!memcpy_s` at `0x1800129ca`
- `KERNEL32!GetLastError` at `0x1800129e5`
- `KERNEL32!GetLastError` at `0x180012a0d`
- `KERNEL32!GetLastError` at `0x1800129e5`
- `KERNEL32!GetLastError` at `0x180012a0d`
- `KERNEL32!SetLastError` at `0x180012a3f`
- `KERNEL32!SetLastError` at `0x180012a4c`
- `KERNEL32!SetLastError` at `0x180012a3f`
- `KERNEL32!SetLastError` at `0x180012a4c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180012a2e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180012a2e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012a84`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012a84`
- `KERNEL32!CloseThreadpoolTimer` at `0x180012a37`
- `KERNEL32!CloseThreadpoolTimer` at `0x180012a37`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001297a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001297a`
- `KERNEL32!SetThreadpoolTimer` at `0x180012a20`
- `KERNEL32!SetThreadpoolTimer` at `0x180012a72`
- `KERNEL32!SetThreadpoolTimer` at `0x180012a20`
- `KERNEL32!SetThreadpoolTimer` at `0x180012a72`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800129fb`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800129fb`

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
0x18001291c  push    rbx
0x18001291e  push    rbp
0x18001291f  push    rsi
0x180012920  push    rdi
0x180012921  push    r14
0x180012923  push    r15
0x180012925  sub     rsp, 48h
0x180012929  mov     rax, cs:__security_cookie
0x180012930  xor     rax, rsp
0x180012933  mov     [rsp+78h+var_40], rax
0x180012938  cmp     byte ptr [rcx], 0
0x18001293b  mov     r14d, r9d
0x18001293e  movzx   ebp, r8w
0x180012942  mov     ebx, edx
0x180012944  mov     rdi, rcx
0x180012947  jz      loc_180012A8A
0x18001294d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180012954  jnz     loc_180012A8A
0x18001295a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012961  test    rax, rax
0x180012964  jz      short loc_180012973
0x180012966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001296b  test    al, al
0x18001296d  jnz     loc_180012A8A
0x180012973  lea     rsi, [rdi+28h]
0x180012977  mov     rcx, rsi; SRWLock
0x18001297a  call    cs:__imp_AcquireSRWLockExclusive
0x180012980  xor     eax, eax
0x180012982  mov     [rsp+78h+Source], ebx
0x180012986  mov     [rsp+78h+var_4C], bp
0x18001298b  lea     rbx, [rdi+0E8h]
0x180012992  mov     rcx, rbx; this
0x180012995  mov     [rsp+78h+var_4A], ax
0x18001299a  mov     [rsp+78h+var_48], r14d
0x18001299f  lea     ebp, [rax+0Ch]
0x1800129a2  mov     edx, ebp; unsigned __int64
0x1800129a4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800129a9  test    al, al
0x1800129ab  jz      short loc_1800129D4
0x1800129ad  mov     rcx, [rbx+8]; Destination
0x1800129b1  lea     r8, [rsp+78h+Source]; Source
0x1800129b6  mov     rax, [rbx+10h]
0x1800129ba  mov     r9d, ebp; SourceSize
0x1800129bd  sub     rax, rcx
0x1800129c0  cmp     rcx, [rbx+10h]
0x1800129c4  sbb     rdx, rdx
0x1800129c7  and     rdx, rax; DestinationSize
0x1800129ca  call    cs:__imp_memcpy_s
0x1800129d0  add     [rbx+8], rbp
0x1800129d4  cmp     byte ptr [rdi+40h], 0
0x1800129d8  jnz     loc_180012A7C
0x1800129de  cmp     qword ptr [rdi+38h], 0
0x1800129e3  jnz     short loc_180012A52
0x1800129e5  call    cs:__imp_GetLastError
0x1800129eb  xor     r8d, r8d; pcbe
0x1800129ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800129f5  mov     rdx, rdi; pv
0x1800129f8  mov     r14d, eax
0x1800129fb  call    cs:__imp_CreateThreadpoolTimer
0x180012a01  mov     rbp, [rdi+38h]
0x180012a05  mov     r15, rax
0x180012a08  test    rbp, rbp
0x180012a0b  jz      short loc_180012A45
0x180012a0d  call    cs:__imp_GetLastError
0x180012a13  xor     r9d, r9d; msWindowLength
0x180012a16  xor     r8d, r8d; msPeriod
0x180012a19  xor     edx, edx; pftDueTime
0x180012a1b  mov     rcx, rbp; pti
0x180012a1e  mov     ebx, eax
0x180012a20  call    cs:__imp_SetThreadpoolTimer
0x180012a26  mov     edx, 1; fCancelPendingCallbacks
0x180012a2b  mov     rcx, rbp; pti
0x180012a2e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012a34  mov     rcx, rbp; pti
0x180012a37  call    cs:__imp_CloseThreadpoolTimer
0x180012a3d  mov     ecx, ebx; dwErrCode
0x180012a3f  call    cs:__imp_SetLastError
0x180012a45  mov     ecx, r14d; dwErrCode
0x180012a48  mov     [rdi+38h], r15
0x180012a4c  call    cs:__imp_SetLastError
0x180012a52  mov     rcx, [rdi+38h]; pti
0x180012a56  test    rcx, rcx
0x180012a59  jz      short loc_180012A7C
0x180012a5b  mov     r9d, 4E2h; msWindowLength
0x180012a61  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180012a6a  xor     r8d, r8d; msPeriod
0x180012a6d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180012a72  call    cs:__imp_SetThreadpoolTimer
0x180012a78  mov     byte ptr [rdi+40h], 1
0x180012a7c  test    rsi, rsi
0x180012a7f  jz      short loc_180012A8A
0x180012a81  mov     rcx, rsi; SRWLock
0x180012a84  call    cs:__imp_ReleaseSRWLockExclusive
0x180012a8a  mov     rcx, [rsp+78h+var_40]
0x180012a8f  xor     rcx, rsp; StackCookie
0x180012a92  call    __security_check_cookie
0x180012a97  add     rsp, 48h
0x180012a9b  pop     r15
0x180012a9d  pop     r14
0x180012a9f  pop     rdi
0x180012aa0  pop     rsi
0x180012aa1  pop     rbp
0x180012aa2  pop     rbx
0x180012aa3  retn
```
