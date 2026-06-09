# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800351a8`
- end: `0x18003527c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036f74`

## callees

- `0x1800351a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035216`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035216`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003521f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003521f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035208`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003525f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035208`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003525f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800351e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800351e3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x1800351a8  mov     [rsp+arg_8], rbx
0x1800351ad  mov     [rsp+arg_10], rbp
0x1800351b2  push    rsi
0x1800351b3  push    rdi
0x1800351b4  push    r14
0x1800351b6  sub     rsp, 20h
0x1800351ba  cmp     byte ptr [rcx+41h], 0
0x1800351be  mov     rdi, rcx
0x1800351c1  jnz     loc_180035269
0x1800351c7  cmp     qword ptr [rcx+30h], 0
0x1800351cc  jnz     short loc_180035239
0x1800351ce  call    cs:__imp_GetLastError
0x1800351d4  xor     r8d, r8d; pcbe
0x1800351d7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800351de  mov     rdx, rdi; pv
0x1800351e1  mov     ebp, eax
0x1800351e3  call    cs:__imp_CreateThreadpoolTimer
0x1800351e9  mov     rsi, [rdi+30h]
0x1800351ed  mov     r14, rax
0x1800351f0  test    rsi, rsi
0x1800351f3  jz      short loc_18003522D
0x1800351f5  call    cs:__imp_GetLastError
0x1800351fb  xor     r9d, r9d; msWindowLength
0x1800351fe  xor     r8d, r8d; msPeriod
0x180035201  xor     edx, edx; pftDueTime
0x180035203  mov     rcx, rsi; pti
0x180035206  mov     ebx, eax
0x180035208  call    cs:__imp_SetThreadpoolTimer
0x18003520e  mov     edx, 1; fCancelPendingCallbacks
0x180035213  mov     rcx, rsi; pti
0x180035216  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003521c  mov     rcx, rsi; pti
0x18003521f  call    cs:__imp_CloseThreadpoolTimer
0x180035225  mov     ecx, ebx; dwErrCode
0x180035227  call    cs:__imp_SetLastError
0x18003522d  mov     ecx, ebp; dwErrCode
0x18003522f  mov     [rdi+30h], r14
0x180035233  call    cs:__imp_SetLastError
0x180035239  mov     rcx, [rdi+30h]; pti
0x18003523d  test    rcx, rcx
0x180035240  jz      short loc_180035269
0x180035242  mov     rax, 0FFFFFFFF4D2FA200h
0x18003524c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180035251  mov     r9d, 124F8h; msWindowLength
0x180035257  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18003525c  xor     r8d, r8d; msPeriod
0x18003525f  call    cs:__imp_SetThreadpoolTimer
0x180035265  mov     byte ptr [rdi+41h], 1
0x180035269  mov     rbx, [rsp+38h+arg_8]
0x18003526e  mov     rbp, [rsp+38h+arg_10]
0x180035273  add     rsp, 20h
0x180035277  pop     r14
0x180035279  pop     rdi
0x18003527a  pop     rsi
0x18003527b  retn
```
