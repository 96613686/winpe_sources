# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800072f8`
- end: `0x180007493`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009cd0`

## callees

- `0x180002ffa`
- `0x180003088`
- `0x1800072f8`
- `0x18000a35c`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000738f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800073b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000738f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800073b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000747f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000747f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007348`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000743a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007447`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000743a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007447`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007432`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007432`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800073f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800073f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000741b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000746d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000741b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000746d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007429`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007429`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v15; // rbp
  DWORD v16; // ebx
  struct _TP_TIMER *v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v18) = a2;
  HIDWORD(v18) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v18;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8) = 22;
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
      v15 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v15 )
      {
        v16 = GetLastError();
        SetThreadpoolTimer(v15, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v15, 1);
        CloseThreadpoolTimer(v15);
        SetLastError(v16);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v17 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v17 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v17, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1800072f8  push    rbx
0x1800072fa  push    rbp
0x1800072fb  push    rsi
0x1800072fc  push    rdi
0x1800072fd  push    r14
0x1800072ff  push    r15
0x180007301  sub     rsp, 38h
0x180007305  mov     ebp, r9d
0x180007308  movzx   ebx, r8w
0x18000730c  mov     r14d, edx
0x18000730f  mov     rdi, rcx
0x180007312  cmp     byte ptr [rcx], 0
0x180007315  jz      loc_180007486
0x18000731b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007322  jnz     loc_180007486
0x180007328  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000732f  test    rax, rax
0x180007332  jz      short loc_180007341
0x180007334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007339  test    al, al
0x18000733b  jnz     loc_180007486
0x180007341  lea     rsi, [rdi+28h]
0x180007345  mov     rcx, rsi; SRWLock
0x180007348  call    cs:__imp_AcquireSRWLockExclusive
0x18000734e  xor     eax, eax
0x180007350  mov     word ptr [rsp+68h+var_48+6], ax
0x180007355  mov     dword ptr [rsp+68h+var_48], r14d
0x18000735a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000735f  lea     rbx, [rdi+0E8h]
0x180007366  lea     edx, [rax+0Ch]; unsigned __int64
0x180007369  mov     rcx, rbx; this
0x18000736c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007371  test    al, al
0x180007373  jz      short loc_1800073CF
0x180007375  mov     rcx, [rbx+8]; void *
0x180007379  mov     rax, [rbx+10h]
0x18000737d  sub     rax, rcx
0x180007380  cmp     rcx, [rbx+10h]
0x180007384  sbb     r8, r8
0x180007387  and     r8, rax; Size
0x18000738a  test    rcx, rcx
0x18000738d  jnz     short loc_18000739D
0x18000738f  call    cs:__imp__o__errno
0x180007395  mov     dword ptr [rax], 16h
0x18000739b  jmp     short loc_1800073C5
0x18000739d  cmp     r8, 0Ch
0x1800073a1  jb      short loc_1800073B2
0x1800073a3  movsd   xmm0, [rsp+68h+var_48]
0x1800073a9  movsd   qword ptr [rcx], xmm0
0x1800073ad  mov     [rcx+8], ebp
0x1800073b0  jmp     short loc_1800073CA
0x1800073b2  xor     edx, edx; Val
0x1800073b4  call    memset_0
0x1800073b9  call    cs:__imp__o__errno
0x1800073bf  mov     dword ptr [rax], 22h ; '"'
0x1800073c5  call    _invalid_parameter_noinfo
0x1800073ca  add     qword ptr [rbx+8], 0Ch
0x1800073cf  cmp     byte ptr [rdi+40h], 0
0x1800073d3  jnz     loc_180007477
0x1800073d9  cmp     qword ptr [rdi+38h], 0
0x1800073de  jnz     short loc_18000744D
0x1800073e0  call    cs:__imp_GetLastError
0x1800073e6  mov     r14d, eax
0x1800073e9  xor     r8d, r8d; pcbe
0x1800073ec  mov     rdx, rdi; pv
0x1800073ef  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800073f6  call    cs:__imp_CreateThreadpoolTimer
0x1800073fc  mov     r15, rax
0x1800073ff  mov     rbp, [rdi+38h]
0x180007403  test    rbp, rbp
0x180007406  jz      short loc_180007440
0x180007408  call    cs:__imp_GetLastError
0x18000740e  mov     ebx, eax
0x180007410  xor     r9d, r9d; msWindowLength
0x180007413  xor     r8d, r8d; msPeriod
0x180007416  xor     edx, edx; pftDueTime
0x180007418  mov     rcx, rbp; pti
0x18000741b  call    cs:__imp_SetThreadpoolTimer
0x180007421  mov     edx, 1; fCancelPendingCallbacks
0x180007426  mov     rcx, rbp; pti
0x180007429  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000742f  mov     rcx, rbp; pti
0x180007432  call    cs:__imp_CloseThreadpoolTimer
0x180007438  mov     ecx, ebx; dwErrCode
0x18000743a  call    cs:__imp_SetLastError
0x180007440  mov     [rdi+38h], r15
0x180007444  mov     ecx, r14d; dwErrCode
0x180007447  call    cs:__imp_SetLastError
0x18000744d  mov     rcx, [rdi+38h]; pti
0x180007451  test    rcx, rcx
0x180007454  jz      short loc_180007477
0x180007456  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000745f  mov     r9d, 4E2h; msWindowLength
0x180007465  xor     r8d, r8d; msPeriod
0x180007468  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000746d  call    cs:__imp_SetThreadpoolTimer
0x180007473  mov     byte ptr [rdi+40h], 1
0x180007477  test    rsi, rsi
0x18000747a  jz      short loc_180007486
0x18000747c  mov     rcx, rsi; SRWLock
0x18000747f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007485  nop
0x180007486  add     rsp, 38h
0x18000748a  pop     r15
0x18000748c  pop     r14
0x18000748e  pop     rdi
0x18000748f  pop     rsi
0x180007490  pop     rbp
0x180007491  pop     rbx
0x180007492  retn
```
