# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140008be0`
- end: `0x140008d68`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000bce0`

## callees

- `0x140008be0`
- `0x14000c16c`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140008c3e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008c3e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008d48`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008d48`
- `KERNEL32!SetThreadpoolTimer` at `0x140008ce4`
- `KERNEL32!SetThreadpoolTimer` at `0x140008d36`
- `KERNEL32!SetThreadpoolTimer` at `0x140008ce4`
- `KERNEL32!SetThreadpoolTimer` at `0x140008d36`
- `KERNEL32!CreateThreadpoolTimer` at `0x140008cbf`
- `KERNEL32!CreateThreadpoolTimer` at `0x140008cbf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008cf2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008cf2`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008cfb`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008cfb`
- `KERNEL32!GetLastError` at `0x140008ca9`
- `KERNEL32!GetLastError` at `0x140008cd1`
- `KERNEL32!GetLastError` at `0x140008ca9`
- `KERNEL32!GetLastError` at `0x140008cd1`
- `KERNEL32!SetLastError` at `0x140008d03`
- `KERNEL32!SetLastError` at `0x140008d10`
- `KERNEL32!SetLastError` at `0x140008d03`
- `KERNEL32!SetLastError` at `0x140008d10`
- `msvcrt!memcpy_s` at `0x140008c8e`
- `msvcrt!memcpy_s` at `0x140008c8e`

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
0x140008be0  push    rbx
0x140008be2  push    rbp
0x140008be3  push    rsi
0x140008be4  push    rdi
0x140008be5  push    r14
0x140008be7  push    r15
0x140008be9  sub     rsp, 48h
0x140008bed  mov     rax, cs:__security_cookie
0x140008bf4  xor     rax, rsp
0x140008bf7  mov     [rsp+78h+var_40], rax
0x140008bfc  cmp     byte ptr [rcx], 0
0x140008bff  mov     r14d, r9d
0x140008c02  movzx   ebp, r8w
0x140008c06  mov     ebx, edx
0x140008c08  mov     rdi, rcx
0x140008c0b  jz      loc_140008D4E
0x140008c11  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008c18  jnz     loc_140008D4E
0x140008c1e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008c25  test    rax, rax
0x140008c28  jz      short loc_140008C37
0x140008c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c2f  test    al, al
0x140008c31  jnz     loc_140008D4E
0x140008c37  lea     rsi, [rdi+28h]
0x140008c3b  mov     rcx, rsi; SRWLock
0x140008c3e  call    cs:__imp_AcquireSRWLockExclusive
0x140008c44  xor     eax, eax
0x140008c46  mov     [rsp+78h+Source], ebx
0x140008c4a  mov     [rsp+78h+var_4C], bp
0x140008c4f  lea     rbx, [rdi+0E8h]
0x140008c56  mov     rcx, rbx; this
0x140008c59  mov     [rsp+78h+var_4A], ax
0x140008c5e  mov     [rsp+78h+var_48], r14d
0x140008c63  lea     ebp, [rax+0Ch]
0x140008c66  mov     edx, ebp; unsigned __int64
0x140008c68  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008c6d  test    al, al
0x140008c6f  jz      short loc_140008C98
0x140008c71  mov     rcx, [rbx+8]; Destination
0x140008c75  lea     r8, [rsp+78h+Source]; Source
0x140008c7a  mov     rax, [rbx+10h]
0x140008c7e  mov     r9d, ebp; SourceSize
0x140008c81  sub     rax, rcx
0x140008c84  cmp     rcx, [rbx+10h]
0x140008c88  sbb     rdx, rdx
0x140008c8b  and     rdx, rax; DestinationSize
0x140008c8e  call    cs:__imp_memcpy_s
0x140008c94  add     [rbx+8], rbp
0x140008c98  cmp     byte ptr [rdi+40h], 0
0x140008c9c  jnz     loc_140008D40
0x140008ca2  cmp     qword ptr [rdi+38h], 0
0x140008ca7  jnz     short loc_140008D16
0x140008ca9  call    cs:__imp_GetLastError
0x140008caf  xor     r8d, r8d; pcbe
0x140008cb2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008cb9  mov     rdx, rdi; pv
0x140008cbc  mov     r14d, eax
0x140008cbf  call    cs:__imp_CreateThreadpoolTimer
0x140008cc5  mov     rbp, [rdi+38h]
0x140008cc9  mov     r15, rax
0x140008ccc  test    rbp, rbp
0x140008ccf  jz      short loc_140008D09
0x140008cd1  call    cs:__imp_GetLastError
0x140008cd7  xor     r9d, r9d; msWindowLength
0x140008cda  xor     r8d, r8d; msPeriod
0x140008cdd  xor     edx, edx; pftDueTime
0x140008cdf  mov     rcx, rbp; pti
0x140008ce2  mov     ebx, eax
0x140008ce4  call    cs:__imp_SetThreadpoolTimer
0x140008cea  mov     edx, 1; fCancelPendingCallbacks
0x140008cef  mov     rcx, rbp; pti
0x140008cf2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008cf8  mov     rcx, rbp; pti
0x140008cfb  call    cs:__imp_CloseThreadpoolTimer
0x140008d01  mov     ecx, ebx; dwErrCode
0x140008d03  call    cs:__imp_SetLastError
0x140008d09  mov     ecx, r14d; dwErrCode
0x140008d0c  mov     [rdi+38h], r15
0x140008d10  call    cs:__imp_SetLastError
0x140008d16  mov     rcx, [rdi+38h]; pti
0x140008d1a  test    rcx, rcx
0x140008d1d  jz      short loc_140008D40
0x140008d1f  mov     r9d, 4E2h; msWindowLength
0x140008d25  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140008d2e  xor     r8d, r8d; msPeriod
0x140008d31  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x140008d36  call    cs:__imp_SetThreadpoolTimer
0x140008d3c  mov     byte ptr [rdi+40h], 1
0x140008d40  test    rsi, rsi
0x140008d43  jz      short loc_140008D4E
0x140008d45  mov     rcx, rsi; SRWLock
0x140008d48  call    cs:__imp_ReleaseSRWLockExclusive
0x140008d4e  mov     rcx, [rsp+78h+var_40]
0x140008d53  xor     rcx, rsp; StackCookie
0x140008d56  call    __security_check_cookie
0x140008d5b  add     rsp, 48h
0x140008d5f  pop     r15
0x140008d61  pop     r14
0x140008d63  pop     rdi
0x140008d64  pop     rsi
0x140008d65  pop     rbp
0x140008d66  pop     rbx
0x140008d67  retn
```
