# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000e750`
- end: `0x18000e8d9`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011fe0`

## callees

- `0x18000e750`
- `0x1800129fc`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e7fe`
- `msvcrt!memcpy_s` at `0x18000e7fe`
- `KERNEL32!GetLastError` at `0x18000e819`
- `KERNEL32!GetLastError` at `0x18000e841`
- `KERNEL32!GetLastError` at `0x18000e819`
- `KERNEL32!GetLastError` at `0x18000e841`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e7ae`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e7ae`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e8b8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e8b8`
- `KERNEL32!SetLastError` at `0x18000e873`
- `KERNEL32!SetLastError` at `0x18000e880`
- `KERNEL32!SetLastError` at `0x18000e873`
- `KERNEL32!SetLastError` at `0x18000e880`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e854`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e8a6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e854`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e8a6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e862`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e862`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000e86b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000e86b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000e82f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000e82f`

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
0x18000e750  push    rbx
0x18000e752  push    rbp
0x18000e753  push    rsi
0x18000e754  push    rdi
0x18000e755  push    r14
0x18000e757  push    r15
0x18000e759  sub     rsp, 48h
0x18000e75d  mov     rax, cs:__security_cookie
0x18000e764  xor     rax, rsp
0x18000e767  mov     [rsp+78h+var_40], rax
0x18000e76c  mov     r14d, r9d
0x18000e76f  movzx   ebp, r8w
0x18000e773  mov     ebx, edx
0x18000e775  mov     rdi, rcx
0x18000e778  cmp     byte ptr [rcx], 0
0x18000e77b  jz      loc_18000E8BF
0x18000e781  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e788  jnz     loc_18000E8BF
0x18000e78e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e795  test    rax, rax
0x18000e798  jz      short loc_18000E7A7
0x18000e79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e79f  test    al, al
0x18000e7a1  jnz     loc_18000E8BF
0x18000e7a7  lea     rsi, [rdi+28h]
0x18000e7ab  mov     rcx, rsi; SRWLock
0x18000e7ae  call    cs:__imp_AcquireSRWLockExclusive
0x18000e7b4  xor     eax, eax
0x18000e7b6  mov     [rsp+78h+var_4A], ax
0x18000e7bb  mov     [rsp+78h+Source], ebx
0x18000e7bf  mov     [rsp+78h+var_4C], bp
0x18000e7c4  mov     [rsp+78h+var_48], r14d
0x18000e7c9  lea     rbx, [rdi+0E8h]
0x18000e7d0  lea     ebp, [rax+0Ch]
0x18000e7d3  mov     edx, ebp; unsigned __int64
0x18000e7d5  mov     rcx, rbx; this
0x18000e7d8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000e7dd  test    al, al
0x18000e7df  jz      short loc_18000E808
0x18000e7e1  mov     rcx, [rbx+8]; Destination
0x18000e7e5  mov     rax, [rbx+10h]
0x18000e7e9  sub     rax, rcx
0x18000e7ec  cmp     rcx, [rbx+10h]
0x18000e7f0  sbb     rdx, rdx
0x18000e7f3  and     rdx, rax; DestinationSize
0x18000e7f6  mov     r9d, ebp; SourceSize
0x18000e7f9  lea     r8, [rsp+78h+Source]; Source
0x18000e7fe  call    cs:__imp_memcpy_s
0x18000e804  add     [rbx+8], rbp
0x18000e808  cmp     byte ptr [rdi+40h], 0
0x18000e80c  jnz     loc_18000E8B0
0x18000e812  cmp     qword ptr [rdi+38h], 0
0x18000e817  jnz     short loc_18000E886
0x18000e819  call    cs:__imp_GetLastError
0x18000e81f  mov     r14d, eax
0x18000e822  xor     r8d, r8d; pcbe
0x18000e825  mov     rdx, rdi; pv
0x18000e828  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e82f  call    cs:__imp_CreateThreadpoolTimer
0x18000e835  mov     r15, rax
0x18000e838  mov     rbp, [rdi+38h]
0x18000e83c  test    rbp, rbp
0x18000e83f  jz      short loc_18000E879
0x18000e841  call    cs:__imp_GetLastError
0x18000e847  mov     ebx, eax
0x18000e849  xor     r9d, r9d; msWindowLength
0x18000e84c  xor     r8d, r8d; msPeriod
0x18000e84f  xor     edx, edx; pftDueTime
0x18000e851  mov     rcx, rbp; pti
0x18000e854  call    cs:__imp_SetThreadpoolTimer
0x18000e85a  mov     edx, 1; fCancelPendingCallbacks
0x18000e85f  mov     rcx, rbp; pti
0x18000e862  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e868  mov     rcx, rbp; pti
0x18000e86b  call    cs:__imp_CloseThreadpoolTimer
0x18000e871  mov     ecx, ebx; dwErrCode
0x18000e873  call    cs:__imp_SetLastError
0x18000e879  mov     [rdi+38h], r15
0x18000e87d  mov     ecx, r14d; dwErrCode
0x18000e880  call    cs:__imp_SetLastError
0x18000e886  mov     rcx, [rdi+38h]; pti
0x18000e88a  test    rcx, rcx
0x18000e88d  jz      short loc_18000E8B0
0x18000e88f  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000e898  mov     r9d, 4E2h; msWindowLength
0x18000e89e  xor     r8d, r8d; msPeriod
0x18000e8a1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000e8a6  call    cs:__imp_SetThreadpoolTimer
0x18000e8ac  mov     byte ptr [rdi+40h], 1
0x18000e8b0  test    rsi, rsi
0x18000e8b3  jz      short loc_18000E8BF
0x18000e8b5  mov     rcx, rsi; SRWLock
0x18000e8b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e8be  nop
0x18000e8bf  mov     rcx, [rsp+78h+var_40]
0x18000e8c4  xor     rcx, rsp; StackCookie
0x18000e8c7  call    __security_check_cookie
0x18000e8cc  add     rsp, 48h
0x18000e8d0  pop     r15
0x18000e8d2  pop     r14
0x18000e8d4  pop     rdi
0x18000e8d5  pop     rsi
0x18000e8d6  pop     rbp
0x18000e8d7  pop     rbx
0x18000e8d8  retn
```
