# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180031158`
- end: `0x1800312ec`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `404`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003267c`

## callees

- `0x180031158`
- `0x18003459c`
- `0x18005a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180031218`
- `msvcrt!memcpy_s` at `0x180031218`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800312d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800312d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800311a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800311a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003128d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003129a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003128d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003129a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003125b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003125b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031249`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031249`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031285`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031285`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003126e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800312c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003126e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800312c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003127c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003127c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+28h] [rbp-40h]
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
      v12 = a3;
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
          if ( Ptr )
          {
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
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
0x180031158  push    rbx
0x18003115a  push    rbp
0x18003115b  push    rsi
0x18003115c  push    rdi
0x18003115d  push    r14
0x18003115f  push    r15
0x180031161  sub     rsp, 38h
0x180031165  mov     rbx, r8
0x180031168  mov     ebp, edx
0x18003116a  mov     rdi, rcx
0x18003116d  mov     eax, [rcx]
0x18003116f  test    eax, eax
0x180031171  jz      loc_1800312DF
0x180031177  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003117e  jnz     loc_1800312DF
0x180031184  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003118b  test    rax, rax
0x18003118e  jz      short loc_18003119D
0x180031190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031195  test    al, al
0x180031197  jnz     loc_1800312DF
0x18003119d  lea     rsi, [rdi+8]
0x1800311a1  mov     rcx, rsi; SRWLock
0x1800311a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800311aa  mov     eax, [rdi]
0x1800311ac  test    eax, eax
0x1800311ae  jz      loc_1800312D0
0x1800311b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800311bb  jnz     loc_1800312D0
0x1800311c1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800311c8  test    rax, rax
0x1800311cb  jz      short loc_1800311DA
0x1800311cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311d2  test    al, al
0x1800311d4  jnz     loc_1800312D0
0x1800311da  mov     [rsp+68h+Source], ebp
0x1800311de  xor     eax, eax
0x1800311e0  mov     [rsp+68h+var_44], eax
0x1800311e4  mov     [rsp+68h+var_40], rbx
0x1800311e9  lea     ebp, [rax+10h]
0x1800311ec  mov     edx, ebp; unsigned __int64
0x1800311ee  lea     rcx, [rdi+20h]; this
0x1800311f2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800311f7  test    al, al
0x1800311f9  jz      short loc_180031222
0x1800311fb  mov     rcx, [rdi+28h]; Destination
0x1800311ff  mov     rax, [rdi+30h]
0x180031203  sub     rax, rcx
0x180031206  cmp     rcx, [rdi+30h]
0x18003120a  sbb     rdx, rdx
0x18003120d  and     rdx, rax; DestinationSize
0x180031210  mov     r9d, ebp; SourceSize
0x180031213  lea     r8, [rsp+68h+Source]; Source
0x180031218  call    cs:__imp_memcpy_s
0x18003121e  add     [rdi+28h], rbp
0x180031222  cmp     byte ptr [rdi+18h], 0
0x180031226  jnz     loc_1800312D0
0x18003122c  cmp     qword ptr [rdi+10h], 0
0x180031231  jnz     short loc_1800312A0
0x180031233  call    cs:__imp_GetLastError
0x180031239  mov     r14d, eax
0x18003123c  xor     r8d, r8d; pcbe
0x18003123f  mov     rdx, rdi; pv
0x180031242  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180031249  call    cs:__imp_CreateThreadpoolTimer
0x18003124f  mov     r15, rax
0x180031252  mov     rbp, [rdi+10h]
0x180031256  test    rbp, rbp
0x180031259  jz      short loc_180031293
0x18003125b  call    cs:__imp_GetLastError
0x180031261  mov     ebx, eax
0x180031263  xor     r9d, r9d; msWindowLength
0x180031266  xor     r8d, r8d; msPeriod
0x180031269  xor     edx, edx; pftDueTime
0x18003126b  mov     rcx, rbp; pti
0x18003126e  call    cs:__imp_SetThreadpoolTimer
0x180031274  mov     edx, 1; fCancelPendingCallbacks
0x180031279  mov     rcx, rbp; pti
0x18003127c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180031282  mov     rcx, rbp; pti
0x180031285  call    cs:__imp_CloseThreadpoolTimer
0x18003128b  mov     ecx, ebx; dwErrCode
0x18003128d  call    cs:__imp_SetLastError
0x180031293  mov     [rdi+10h], r15
0x180031297  mov     ecx, r14d; dwErrCode
0x18003129a  call    cs:__imp_SetLastError
0x1800312a0  mov     rcx, [rdi+10h]; pti
0x1800312a4  test    rcx, rcx
0x1800312a7  jz      short loc_1800312D0
0x1800312a9  mov     rax, 0FFFFFFFF4D2FA200h
0x1800312b3  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x1800312b8  mov     r9d, 124F8h; msWindowLength
0x1800312be  xor     r8d, r8d; msPeriod
0x1800312c1  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800312c6  call    cs:__imp_SetThreadpoolTimer
0x1800312cc  mov     byte ptr [rdi+18h], 1
0x1800312d0  test    rsi, rsi
0x1800312d3  jz      short loc_1800312DF
0x1800312d5  mov     rcx, rsi; SRWLock
0x1800312d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800312de  nop
0x1800312df  add     rsp, 38h
0x1800312e3  pop     r15
0x1800312e5  pop     r14
0x1800312e7  pop     rdi
0x1800312e8  pop     rsi
0x1800312e9  pop     rbp
0x1800312ea  pop     rbx
0x1800312eb  retn
```
