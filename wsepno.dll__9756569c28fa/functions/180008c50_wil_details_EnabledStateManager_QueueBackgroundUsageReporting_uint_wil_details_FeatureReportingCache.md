# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180008c50`
- end: `0x180008e04`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `436`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a1b8`

## callees

- `0x18000218a`
- `0x1800021f4`
- `0x180008c50`
- `0x18000b74c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008cfc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008cfc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008da5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008db2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008da5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008df0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008df0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008d9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008d9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008d94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008d94`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008dde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008dde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008d61`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008d61`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  size_t v7; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
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
            v11 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v11);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v12 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v12 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v12, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v6 = pv[5].Ptr;
    v7 = ((char *)pv[6].Ptr - (char *)v6) & -(__int64)(v6 < pv[6].Ptr);
    if ( v6 )
    {
      if ( v7 >= 0x10 )
      {
        *v6 = 16372493;
        v6[1] = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v5, v7) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180008c50  push    rbx
0x180008c52  push    rbp
0x180008c53  push    rsi
0x180008c54  push    rdi
0x180008c55  push    r14
0x180008c57  push    r15
0x180008c59  sub     rsp, 28h
0x180008c5d  mov     rbp, r8
0x180008c60  mov     rdi, rcx
0x180008c63  mov     eax, [rcx]
0x180008c65  test    eax, eax
0x180008c67  jz      loc_180008DF7
0x180008c6d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008c74  jnz     loc_180008DF7
0x180008c7a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008c81  test    rax, rax
0x180008c84  jz      short loc_180008C93
0x180008c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8b  test    al, al
0x180008c8d  jnz     loc_180008DF7
0x180008c93  lea     rsi, [rdi+8]
0x180008c97  mov     rcx, rsi; SRWLock
0x180008c9a  call    cs:__imp_AcquireSRWLockExclusive
0x180008ca0  mov     eax, [rdi]
0x180008ca2  test    eax, eax
0x180008ca4  jz      loc_180008DE8
0x180008caa  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008cb1  jnz     loc_180008DE8
0x180008cb7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008cbe  test    rax, rax
0x180008cc1  jz      short loc_180008CD0
0x180008cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc8  test    al, al
0x180008cca  jnz     loc_180008DE8
0x180008cd0  mov     edx, 10h; unsigned __int64
0x180008cd5  lea     rcx, [rdi+20h]; this
0x180008cd9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008cde  test    al, al
0x180008ce0  jz      short loc_180008D3A
0x180008ce2  mov     rcx, [rdi+28h]; void *
0x180008ce6  mov     rax, [rdi+30h]
0x180008cea  sub     rax, rcx
0x180008ced  cmp     rcx, [rdi+30h]
0x180008cf1  sbb     r8, r8
0x180008cf4  and     r8, rax; Size
0x180008cf7  test    rcx, rcx
0x180008cfa  jnz     short loc_180008D0A
0x180008cfc  call    cs:__imp__o__errno
0x180008d02  mov     dword ptr [rax], 16h
0x180008d08  jmp     short loc_180008D30
0x180008d0a  cmp     r8, 10h
0x180008d0e  jb      short loc_180008D1D
0x180008d10  mov     qword ptr [rcx], 0F9D30Dh
0x180008d17  mov     [rcx+8], rbp
0x180008d1b  jmp     short loc_180008D35
0x180008d1d  xor     edx, edx; Val
0x180008d1f  call    memset_0
0x180008d24  call    cs:__imp__o__errno
0x180008d2a  mov     dword ptr [rax], 22h ; '"'
0x180008d30  call    _invalid_parameter_noinfo
0x180008d35  add     qword ptr [rdi+28h], 10h
0x180008d3a  cmp     byte ptr [rdi+18h], 0
0x180008d3e  jnz     loc_180008DE8
0x180008d44  cmp     qword ptr [rdi+10h], 0
0x180008d49  jnz     short loc_180008DB8
0x180008d4b  call    cs:__imp_GetLastError
0x180008d51  mov     r14d, eax
0x180008d54  xor     r8d, r8d; pcbe
0x180008d57  mov     rdx, rdi; pv
0x180008d5a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008d61  call    cs:__imp_CreateThreadpoolTimer
0x180008d67  mov     r15, rax
0x180008d6a  mov     rbp, [rdi+10h]
0x180008d6e  test    rbp, rbp
0x180008d71  jz      short loc_180008DAB
0x180008d73  call    cs:__imp_GetLastError
0x180008d79  mov     ebx, eax
0x180008d7b  xor     r9d, r9d; msWindowLength
0x180008d7e  xor     r8d, r8d; msPeriod
0x180008d81  xor     edx, edx; pftDueTime
0x180008d83  mov     rcx, rbp; pti
0x180008d86  call    cs:__imp_SetThreadpoolTimer
0x180008d8c  mov     edx, 1; fCancelPendingCallbacks
0x180008d91  mov     rcx, rbp; pti
0x180008d94  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008d9a  mov     rcx, rbp; pti
0x180008d9d  call    cs:__imp_CloseThreadpoolTimer
0x180008da3  mov     ecx, ebx; dwErrCode
0x180008da5  call    cs:__imp_SetLastError
0x180008dab  mov     [rdi+10h], r15
0x180008daf  mov     ecx, r14d; dwErrCode
0x180008db2  call    cs:__imp_SetLastError
0x180008db8  mov     rcx, [rdi+10h]; pti
0x180008dbc  test    rcx, rcx
0x180008dbf  jz      short loc_180008DE8
0x180008dc1  mov     rax, 0FFFFFFFF4D2FA200h
0x180008dcb  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180008dd0  mov     r9d, 124F8h; msWindowLength
0x180008dd6  xor     r8d, r8d; msPeriod
0x180008dd9  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180008dde  call    cs:__imp_SetThreadpoolTimer
0x180008de4  mov     byte ptr [rdi+18h], 1
0x180008de8  test    rsi, rsi
0x180008deb  jz      short loc_180008DF7
0x180008ded  mov     rcx, rsi; SRWLock
0x180008df0  call    cs:__imp_ReleaseSRWLockExclusive
0x180008df6  nop
0x180008df7  add     rsp, 28h
0x180008dfb  pop     r15
0x180008dfd  pop     r14
0x180008dff  pop     rdi
0x180008e00  pop     rsi
0x180008e01  pop     rbp
0x180008e02  pop     rbx
0x180008e03  retn
```
