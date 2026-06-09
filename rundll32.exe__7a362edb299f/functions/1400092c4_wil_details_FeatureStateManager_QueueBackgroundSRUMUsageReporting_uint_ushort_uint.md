# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400092c4`
- end: `0x14000944b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `391`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000a710`

## callees

- `0x1400015a0`
- `0x14000220c`
- `0x1400092c4`
- `0x14000ab0c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000942b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000942b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009322`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000938c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000938c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400093a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400093a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400093d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400093d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400093de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400093de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400093c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009419`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400093c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009419`

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
0x1400092c4  push    rbx
0x1400092c6  push    rbp
0x1400092c7  push    rsi
0x1400092c8  push    rdi
0x1400092c9  push    r14
0x1400092cb  push    r15
0x1400092cd  sub     rsp, 48h
0x1400092d1  mov     rax, cs:__security_cookie
0x1400092d8  xor     rax, rsp
0x1400092db  mov     [rsp+78h+var_40], rax
0x1400092e0  cmp     byte ptr [rcx], 0
0x1400092e3  mov     r14d, r9d
0x1400092e6  movzx   ebp, r8w
0x1400092ea  mov     ebx, edx
0x1400092ec  mov     rdi, rcx
0x1400092ef  jz      loc_140009431
0x1400092f5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400092fc  jnz     loc_140009431
0x140009302  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009309  test    rax, rax
0x14000930c  jz      short loc_14000931B
0x14000930e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009313  test    al, al
0x140009315  jnz     loc_140009431
0x14000931b  lea     rsi, [rdi+28h]
0x14000931f  mov     rcx, rsi; SRWLock
0x140009322  call    cs:__imp_AcquireSRWLockExclusive
0x140009328  xor     eax, eax
0x14000932a  mov     [rsp+78h+Source], ebx
0x14000932e  mov     [rsp+78h+var_4C], bp
0x140009333  lea     rbx, [rdi+0E8h]
0x14000933a  mov     rcx, rbx; this
0x14000933d  mov     [rsp+78h+var_4A], ax
0x140009342  mov     [rsp+78h+var_48], r14d
0x140009347  lea     ebp, [rax+0Ch]
0x14000934a  mov     edx, ebp; unsigned __int64
0x14000934c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009351  test    al, al
0x140009353  jz      short loc_14000937B
0x140009355  mov     rcx, [rbx+8]; Destination
0x140009359  lea     r8, [rsp+78h+Source]; Source
0x14000935e  mov     rax, [rbx+10h]
0x140009362  mov     r9d, ebp; SourceSize
0x140009365  sub     rax, rcx
0x140009368  cmp     rcx, [rbx+10h]
0x14000936c  sbb     rdx, rdx
0x14000936f  and     rdx, rax; DestinationSize
0x140009372  call    memcpy_s
0x140009377  add     [rbx+8], rbp
0x14000937b  cmp     byte ptr [rdi+40h], 0
0x14000937f  jnz     loc_140009423
0x140009385  cmp     qword ptr [rdi+38h], 0
0x14000938a  jnz     short loc_1400093F9
0x14000938c  call    cs:__imp_GetLastError
0x140009392  xor     r8d, r8d; pcbe
0x140009395  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000939c  mov     rdx, rdi; pv
0x14000939f  mov     r14d, eax
0x1400093a2  call    cs:__imp_CreateThreadpoolTimer
0x1400093a8  mov     rbp, [rdi+38h]
0x1400093ac  mov     r15, rax
0x1400093af  test    rbp, rbp
0x1400093b2  jz      short loc_1400093EC
0x1400093b4  call    cs:__imp_GetLastError
0x1400093ba  xor     r9d, r9d; msWindowLength
0x1400093bd  xor     r8d, r8d; msPeriod
0x1400093c0  xor     edx, edx; pftDueTime
0x1400093c2  mov     rcx, rbp; pti
0x1400093c5  mov     ebx, eax
0x1400093c7  call    cs:__imp_SetThreadpoolTimer
0x1400093cd  mov     edx, 1; fCancelPendingCallbacks
0x1400093d2  mov     rcx, rbp; pti
0x1400093d5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400093db  mov     rcx, rbp; pti
0x1400093de  call    cs:__imp_CloseThreadpoolTimer
0x1400093e4  mov     ecx, ebx; dwErrCode
0x1400093e6  call    cs:__imp_SetLastError
0x1400093ec  mov     ecx, r14d; dwErrCode
0x1400093ef  mov     [rdi+38h], r15
0x1400093f3  call    cs:__imp_SetLastError
0x1400093f9  mov     rcx, [rdi+38h]; pti
0x1400093fd  test    rcx, rcx
0x140009400  jz      short loc_140009423
0x140009402  mov     r9d, 4E2h; msWindowLength
0x140009408  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140009411  xor     r8d, r8d; msPeriod
0x140009414  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x140009419  call    cs:__imp_SetThreadpoolTimer
0x14000941f  mov     byte ptr [rdi+40h], 1
0x140009423  test    rsi, rsi
0x140009426  jz      short loc_140009431
0x140009428  mov     rcx, rsi; SRWLock
0x14000942b  call    cs:__imp_ReleaseSRWLockExclusive
0x140009431  mov     rcx, [rsp+78h+var_40]
0x140009436  xor     rcx, rsp; StackCookie
0x140009439  call    __security_check_cookie
0x14000943e  add     rsp, 48h
0x140009442  pop     r15
0x140009444  pop     r14
0x140009446  pop     rdi
0x140009447  pop     rsi
0x140009448  pop     rbp
0x140009449  pop     rbx
0x14000944a  retn
```
