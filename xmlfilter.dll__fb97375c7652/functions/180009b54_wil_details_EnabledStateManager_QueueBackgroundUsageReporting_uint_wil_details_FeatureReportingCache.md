# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180009b54`
- end: `0x180009d0c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b418`

## callees

- `0x180002ae2`
- `0x180002b38`
- `0x180009b54`
- `0x18000d7e4`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009c05`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009c2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009c05`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009c2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009cf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009cf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ba1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ba1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009c8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ce6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009c8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ce6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009c69`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009c69`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009ca5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009ca5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009c9c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009c9c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
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
            v15 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v15);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v16 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v16 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v16, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180009b54  push    rbx
0x180009b56  push    rbp
0x180009b57  push    rsi
0x180009b58  push    rdi
0x180009b59  push    r14
0x180009b5b  push    r15
0x180009b5d  sub     rsp, 28h
0x180009b61  mov     rbp, r8
0x180009b64  mov     r14d, edx
0x180009b67  mov     rdi, rcx
0x180009b6a  mov     eax, [rcx]
0x180009b6c  test    eax, eax
0x180009b6e  jz      loc_180009CFF
0x180009b74  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009b7b  jnz     loc_180009CFF
0x180009b81  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009b88  test    rax, rax
0x180009b8b  jz      short loc_180009B9A
0x180009b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b92  test    al, al
0x180009b94  jnz     loc_180009CFF
0x180009b9a  lea     rsi, [rdi+8]
0x180009b9e  mov     rcx, rsi; SRWLock
0x180009ba1  call    cs:__imp_AcquireSRWLockExclusive
0x180009ba7  mov     eax, [rdi]
0x180009ba9  test    eax, eax
0x180009bab  jz      loc_180009CF0
0x180009bb1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009bb8  jnz     loc_180009CF0
0x180009bbe  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009bc5  test    rax, rax
0x180009bc8  jz      short loc_180009BD7
0x180009bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bcf  test    al, al
0x180009bd1  jnz     loc_180009CF0
0x180009bd7  xor     r15d, r15d
0x180009bda  lea     edx, [r15+10h]; unsigned __int64
0x180009bde  lea     rcx, [rdi+20h]; this
0x180009be2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009be7  test    al, al
0x180009be9  jz      short loc_180009C43
0x180009beb  mov     rcx, [rdi+28h]; void *
0x180009bef  mov     rax, [rdi+30h]
0x180009bf3  sub     rax, rcx
0x180009bf6  cmp     rcx, [rdi+30h]
0x180009bfa  sbb     r8, r8
0x180009bfd  and     r8, rax; Size
0x180009c00  test    rcx, rcx
0x180009c03  jnz     short loc_180009C13
0x180009c05  call    cs:__imp__o__errno
0x180009c0b  mov     dword ptr [rax], 16h
0x180009c11  jmp     short loc_180009C39
0x180009c13  cmp     r8, 10h
0x180009c17  jb      short loc_180009C26
0x180009c19  mov     [rcx], r14d
0x180009c1c  mov     [rcx+4], r15d
0x180009c20  mov     [rcx+8], rbp
0x180009c24  jmp     short loc_180009C3E
0x180009c26  xor     edx, edx; Val
0x180009c28  call    memset_0
0x180009c2d  call    cs:__imp__o__errno
0x180009c33  mov     dword ptr [rax], 22h ; '"'
0x180009c39  call    _invalid_parameter_noinfo
0x180009c3e  add     qword ptr [rdi+28h], 10h
0x180009c43  cmp     [rdi+18h], r15b
0x180009c47  jnz     loc_180009CF0
0x180009c4d  cmp     [rdi+10h], r15
0x180009c51  jnz     short loc_180009CC0
0x180009c53  call    cs:__imp_GetLastError
0x180009c59  mov     r14d, eax
0x180009c5c  xor     r8d, r8d; pcbe
0x180009c5f  mov     rdx, rdi; pv
0x180009c62  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009c69  call    cs:__imp_CreateThreadpoolTimer
0x180009c6f  mov     r15, rax
0x180009c72  mov     rbp, [rdi+10h]
0x180009c76  test    rbp, rbp
0x180009c79  jz      short loc_180009CB3
0x180009c7b  call    cs:__imp_GetLastError
0x180009c81  mov     ebx, eax
0x180009c83  xor     r9d, r9d; msWindowLength
0x180009c86  xor     r8d, r8d; msPeriod
0x180009c89  xor     edx, edx; pftDueTime
0x180009c8b  mov     rcx, rbp; pti
0x180009c8e  call    cs:__imp_SetThreadpoolTimer
0x180009c94  mov     edx, 1; fCancelPendingCallbacks
0x180009c99  mov     rcx, rbp; pti
0x180009c9c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ca2  mov     rcx, rbp; pti
0x180009ca5  call    cs:__imp_CloseThreadpoolTimer
0x180009cab  mov     ecx, ebx; dwErrCode
0x180009cad  call    cs:__imp_SetLastError
0x180009cb3  mov     [rdi+10h], r15
0x180009cb7  mov     ecx, r14d; dwErrCode
0x180009cba  call    cs:__imp_SetLastError
0x180009cc0  mov     rcx, [rdi+10h]; pti
0x180009cc4  test    rcx, rcx
0x180009cc7  jz      short loc_180009CF0
0x180009cc9  mov     rax, 0FFFFFFFF4D2FA200h
0x180009cd3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180009cd8  mov     r9d, 124F8h; msWindowLength
0x180009cde  xor     r8d, r8d; msPeriod
0x180009ce1  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180009ce6  call    cs:__imp_SetThreadpoolTimer
0x180009cec  mov     byte ptr [rdi+18h], 1
0x180009cf0  test    rsi, rsi
0x180009cf3  jz      short loc_180009CFF
0x180009cf5  mov     rcx, rsi; SRWLock
0x180009cf8  call    cs:__imp_ReleaseSRWLockExclusive
0x180009cfe  nop
0x180009cff  add     rsp, 28h
0x180009d03  pop     r15
0x180009d05  pop     r14
0x180009d07  pop     rdi
0x180009d08  pop     rsi
0x180009d09  pop     rbp
0x180009d0a  pop     rbx
0x180009d0b  retn
```
