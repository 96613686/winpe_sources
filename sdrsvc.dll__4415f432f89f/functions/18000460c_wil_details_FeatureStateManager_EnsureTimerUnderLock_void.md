# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000460c`
- end: `0x1800046e0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063a4`

## callees

- `0x18000460c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000468b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004697`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000468b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004697`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004683`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004683`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004647`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004647`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000466c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800046c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000466c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800046c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000467a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000467a`

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
0x18000460c  mov     [rsp+arg_8], rbx
0x180004611  mov     [rsp+arg_10], rbp
0x180004616  push    rsi
0x180004617  push    rdi
0x180004618  push    r14
0x18000461a  sub     rsp, 20h
0x18000461e  cmp     byte ptr [rcx+41h], 0
0x180004622  mov     rdi, rcx
0x180004625  jnz     loc_1800046CD
0x18000462b  cmp     qword ptr [rcx+30h], 0
0x180004630  jnz     short loc_18000469D
0x180004632  call    cs:__imp_GetLastError
0x180004638  xor     r8d, r8d; pcbe
0x18000463b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004642  mov     rdx, rdi; pv
0x180004645  mov     ebp, eax
0x180004647  call    cs:__imp_CreateThreadpoolTimer
0x18000464d  mov     rsi, [rdi+30h]
0x180004651  mov     r14, rax
0x180004654  test    rsi, rsi
0x180004657  jz      short loc_180004691
0x180004659  call    cs:__imp_GetLastError
0x18000465f  xor     r9d, r9d; msWindowLength
0x180004662  xor     r8d, r8d; msPeriod
0x180004665  xor     edx, edx; pftDueTime
0x180004667  mov     rcx, rsi; pti
0x18000466a  mov     ebx, eax
0x18000466c  call    cs:__imp_SetThreadpoolTimer
0x180004672  mov     edx, 1; fCancelPendingCallbacks
0x180004677  mov     rcx, rsi; pti
0x18000467a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004680  mov     rcx, rsi; pti
0x180004683  call    cs:__imp_CloseThreadpoolTimer
0x180004689  mov     ecx, ebx; dwErrCode
0x18000468b  call    cs:__imp_SetLastError
0x180004691  mov     ecx, ebp; dwErrCode
0x180004693  mov     [rdi+30h], r14
0x180004697  call    cs:__imp_SetLastError
0x18000469d  mov     rcx, [rdi+30h]; pti
0x1800046a1  test    rcx, rcx
0x1800046a4  jz      short loc_1800046CD
0x1800046a6  mov     rax, 0FFFFFFFF4D2FA200h
0x1800046b0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800046b5  mov     r9d, 124F8h; msWindowLength
0x1800046bb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800046c0  xor     r8d, r8d; msPeriod
0x1800046c3  call    cs:__imp_SetThreadpoolTimer
0x1800046c9  mov     byte ptr [rdi+41h], 1
0x1800046cd  mov     rbx, [rsp+38h+arg_8]
0x1800046d2  mov     rbp, [rsp+38h+arg_10]
0x1800046d7  add     rsp, 20h
0x1800046db  pop     r14
0x1800046dd  pop     rdi
0x1800046de  pop     rsi
0x1800046df  retn
```
