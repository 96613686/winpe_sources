# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180018770`
- end: `0x180018903`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018c00`

## callees

- `0x180018770`
- `0x180019328`
- `0x18001e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180018830`
- `msvcrt!memcpy_s` at `0x180018830`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800188f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800188f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800187bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800187bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001884b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001884b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018873`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001889d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001889d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018894`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018894`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018886`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800188de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018886`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800188de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018861`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018861`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v13 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          v9 = ThreadpoolTimer;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = v9;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x180018770  push    rbx
0x180018772  push    rbp
0x180018773  push    rsi
0x180018774  push    rdi
0x180018775  push    r14
0x180018777  push    r15
0x180018779  sub     rsp, 38h
0x18001877d  mov     eax, [rcx]
0x18001877f  mov     rbx, r8
0x180018782  mov     ebp, edx
0x180018784  mov     rdi, rcx
0x180018787  test    eax, eax
0x180018789  jz      loc_1800188F6
0x18001878f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180018796  jnz     loc_1800188F6
0x18001879c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800187a3  test    rax, rax
0x1800187a6  jz      short loc_1800187B5
0x1800187a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ad  test    al, al
0x1800187af  jnz     loc_1800188F6
0x1800187b5  lea     rsi, [rdi+8]
0x1800187b9  mov     rcx, rsi; SRWLock
0x1800187bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800187c2  mov     eax, [rdi]
0x1800187c4  test    eax, eax
0x1800187c6  jz      loc_1800188E8
0x1800187cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800187d3  jnz     loc_1800188E8
0x1800187d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800187e0  test    rax, rax
0x1800187e3  jz      short loc_1800187F2
0x1800187e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ea  test    al, al
0x1800187ec  jnz     loc_1800188E8
0x1800187f2  xor     eax, eax
0x1800187f4  mov     [rsp+68h+Source], ebp
0x1800187f8  lea     rcx, [rdi+20h]; this
0x1800187fc  mov     [rsp+68h+var_44], eax
0x180018800  mov     [rsp+68h+var_40], rbx
0x180018805  lea     ebp, [rax+10h]
0x180018808  mov     edx, ebp; unsigned __int64
0x18001880a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001880f  test    al, al
0x180018811  jz      short loc_18001883A
0x180018813  mov     rcx, [rdi+28h]; Destination
0x180018817  lea     r8, [rsp+68h+Source]; Source
0x18001881c  mov     rax, [rdi+30h]
0x180018820  mov     r9d, ebp; SourceSize
0x180018823  sub     rax, rcx
0x180018826  cmp     rcx, [rdi+30h]
0x18001882a  sbb     rdx, rdx
0x18001882d  and     rdx, rax; DestinationSize
0x180018830  call    cs:__imp_memcpy_s
0x180018836  add     [rdi+28h], rbp
0x18001883a  cmp     byte ptr [rdi+18h], 0
0x18001883e  jnz     loc_1800188E8
0x180018844  cmp     qword ptr [rdi+10h], 0
0x180018849  jnz     short loc_1800188B8
0x18001884b  call    cs:__imp_GetLastError
0x180018851  xor     r8d, r8d; pcbe
0x180018854  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001885b  mov     rdx, rdi; pv
0x18001885e  mov     r14d, eax
0x180018861  call    cs:__imp_CreateThreadpoolTimer
0x180018867  mov     rbp, [rdi+10h]
0x18001886b  mov     r15, rax
0x18001886e  test    rbp, rbp
0x180018871  jz      short loc_1800188AB
0x180018873  call    cs:__imp_GetLastError
0x180018879  xor     r9d, r9d; msWindowLength
0x18001887c  xor     r8d, r8d; msPeriod
0x18001887f  xor     edx, edx; pftDueTime
0x180018881  mov     rcx, rbp; pti
0x180018884  mov     ebx, eax
0x180018886  call    cs:__imp_SetThreadpoolTimer
0x18001888c  mov     edx, 1; fCancelPendingCallbacks
0x180018891  mov     rcx, rbp; pti
0x180018894  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001889a  mov     rcx, rbp; pti
0x18001889d  call    cs:__imp_CloseThreadpoolTimer
0x1800188a3  mov     ecx, ebx; dwErrCode
0x1800188a5  call    cs:__imp_SetLastError
0x1800188ab  mov     ecx, r14d; dwErrCode
0x1800188ae  mov     [rdi+10h], r15
0x1800188b2  call    cs:__imp_SetLastError
0x1800188b8  mov     rcx, [rdi+10h]; pti
0x1800188bc  test    rcx, rcx
0x1800188bf  jz      short loc_1800188E8
0x1800188c1  mov     rax, 0FFFFFFFF4D2FA200h
0x1800188cb  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800188d0  mov     r9d, 124F8h; msWindowLength
0x1800188d6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x1800188db  xor     r8d, r8d; msPeriod
0x1800188de  call    cs:__imp_SetThreadpoolTimer
0x1800188e4  mov     byte ptr [rdi+18h], 1
0x1800188e8  test    rsi, rsi
0x1800188eb  jz      short loc_1800188F6
0x1800188ed  mov     rcx, rsi; SRWLock
0x1800188f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800188f6  add     rsp, 38h
0x1800188fa  pop     r15
0x1800188fc  pop     r14
0x1800188fe  pop     rdi
0x1800188ff  pop     rsi
0x180018900  pop     rbp
0x180018901  pop     rbx
0x180018902  retn
```
