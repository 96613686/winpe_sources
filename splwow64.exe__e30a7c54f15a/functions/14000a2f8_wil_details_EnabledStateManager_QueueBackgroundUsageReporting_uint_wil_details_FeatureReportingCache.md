# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000a2f8`
- end: `0x14000a4af`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `439`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000b708`

## callees

- `0x1400027fe`
- `0x1400028b8`
- `0x14000a2f8`
- `0x14000c354`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000a451`
- `KERNEL32!SetLastError` at `0x14000a45e`
- `KERNEL32!SetLastError` at `0x14000a451`
- `KERNEL32!SetLastError` at `0x14000a45e`
- `KERNEL32!GetLastError` at `0x14000a3f7`
- `KERNEL32!GetLastError` at `0x14000a41f`
- `KERNEL32!GetLastError` at `0x14000a3f7`
- `KERNEL32!GetLastError` at `0x14000a41f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a345`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a345`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a49c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a49c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a432`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a48a`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a432`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a48a`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a449`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a449`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a440`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a440`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000a40d`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000a40d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a3a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a3d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a3a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a3d1`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v12; // r15
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
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
          v12 = ThreadpoolTimer;
          if ( Ptr )
          {
            v13 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v13);
          }
          pv[2].Ptr = v12;
          SetLastError(LastError);
        }
        v14 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v14 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v14, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
0x14000a2f8  push    rbx
0x14000a2fa  push    rbp
0x14000a2fb  push    rsi
0x14000a2fc  push    rdi
0x14000a2fd  push    r14
0x14000a2ff  push    r15
0x14000a301  sub     rsp, 28h
0x14000a305  mov     eax, [rcx]
0x14000a307  mov     rbp, r8
0x14000a30a  mov     r14d, edx
0x14000a30d  mov     rdi, rcx
0x14000a310  test    eax, eax
0x14000a312  jz      loc_14000A4A2
0x14000a318  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a31f  jnz     loc_14000A4A2
0x14000a325  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a32c  test    rax, rax
0x14000a32f  jz      short loc_14000A33E
0x14000a331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a336  test    al, al
0x14000a338  jnz     loc_14000A4A2
0x14000a33e  lea     rsi, [rdi+8]
0x14000a342  mov     rcx, rsi; SRWLock
0x14000a345  call    cs:__imp_AcquireSRWLockExclusive
0x14000a34b  mov     eax, [rdi]
0x14000a34d  test    eax, eax
0x14000a34f  jz      loc_14000A494
0x14000a355  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a35c  jnz     loc_14000A494
0x14000a362  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a369  test    rax, rax
0x14000a36c  jz      short loc_14000A37B
0x14000a36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a373  test    al, al
0x14000a375  jnz     loc_14000A494
0x14000a37b  xor     r15d, r15d
0x14000a37e  lea     rcx, [rdi+20h]; this
0x14000a382  lea     edx, [r15+10h]; unsigned __int64
0x14000a386  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000a38b  test    al, al
0x14000a38d  jz      short loc_14000A3E7
0x14000a38f  mov     rcx, [rdi+28h]; void *
0x14000a393  mov     rax, [rdi+30h]
0x14000a397  sub     rax, rcx
0x14000a39a  cmp     rcx, [rdi+30h]
0x14000a39e  sbb     r8, r8
0x14000a3a1  and     r8, rax; Size
0x14000a3a4  test    rcx, rcx
0x14000a3a7  jnz     short loc_14000A3B7
0x14000a3a9  call    cs:__imp__o__errno
0x14000a3af  mov     dword ptr [rax], 16h
0x14000a3b5  jmp     short loc_14000A3DD
0x14000a3b7  cmp     r8, 10h
0x14000a3bb  jb      short loc_14000A3CA
0x14000a3bd  mov     [rcx], r14d
0x14000a3c0  mov     [rcx+4], r15d
0x14000a3c4  mov     [rcx+8], rbp
0x14000a3c8  jmp     short loc_14000A3E2
0x14000a3ca  xor     edx, edx; Val
0x14000a3cc  call    memset_0
0x14000a3d1  call    cs:__imp__o__errno
0x14000a3d7  mov     dword ptr [rax], 22h ; '"'
0x14000a3dd  call    _invalid_parameter_noinfo
0x14000a3e2  add     qword ptr [rdi+28h], 10h
0x14000a3e7  cmp     [rdi+18h], r15b
0x14000a3eb  jnz     loc_14000A494
0x14000a3f1  cmp     [rdi+10h], r15
0x14000a3f5  jnz     short loc_14000A464
0x14000a3f7  call    cs:__imp_GetLastError
0x14000a3fd  xor     r8d, r8d; pcbe
0x14000a400  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000a407  mov     rdx, rdi; pv
0x14000a40a  mov     r14d, eax
0x14000a40d  call    cs:__imp_CreateThreadpoolTimer
0x14000a413  mov     rbp, [rdi+10h]
0x14000a417  mov     r15, rax
0x14000a41a  test    rbp, rbp
0x14000a41d  jz      short loc_14000A457
0x14000a41f  call    cs:__imp_GetLastError
0x14000a425  xor     r9d, r9d; msWindowLength
0x14000a428  xor     r8d, r8d; msPeriod
0x14000a42b  xor     edx, edx; pftDueTime
0x14000a42d  mov     rcx, rbp; pti
0x14000a430  mov     ebx, eax
0x14000a432  call    cs:__imp_SetThreadpoolTimer
0x14000a438  mov     edx, 1; fCancelPendingCallbacks
0x14000a43d  mov     rcx, rbp; pti
0x14000a440  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a446  mov     rcx, rbp; pti
0x14000a449  call    cs:__imp_CloseThreadpoolTimer
0x14000a44f  mov     ecx, ebx; dwErrCode
0x14000a451  call    cs:__imp_SetLastError
0x14000a457  mov     ecx, r14d; dwErrCode
0x14000a45a  mov     [rdi+10h], r15
0x14000a45e  call    cs:__imp_SetLastError
0x14000a464  mov     rcx, [rdi+10h]; pti
0x14000a468  test    rcx, rcx
0x14000a46b  jz      short loc_14000A494
0x14000a46d  mov     rax, 0FFFFFFFF4D2FA200h
0x14000a477  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x14000a47c  mov     r9d, 124F8h; msWindowLength
0x14000a482  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x14000a487  xor     r8d, r8d; msPeriod
0x14000a48a  call    cs:__imp_SetThreadpoolTimer
0x14000a490  mov     byte ptr [rdi+18h], 1
0x14000a494  test    rsi, rsi
0x14000a497  jz      short loc_14000A4A2
0x14000a499  mov     rcx, rsi; SRWLock
0x14000a49c  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a4a2  add     rsp, 28h
0x14000a4a6  pop     r15
0x14000a4a8  pop     r14
0x14000a4aa  pop     rdi
0x14000a4ab  pop     rsi
0x14000a4ac  pop     rbp
0x14000a4ad  pop     rbx
0x14000a4ae  retn
```
