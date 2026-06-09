# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180025c88`
- end: `0x180025d5c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180044134`

## callees

- `0x180025c88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cd5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025cff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025cff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025cf6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025cf6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025cc3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025cc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025ce8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025d3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025ce8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025d3f`

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
0x180025c88  mov     [rsp+arg_8], rbx
0x180025c8d  mov     [rsp+arg_10], rbp
0x180025c92  push    rsi
0x180025c93  push    rdi
0x180025c94  push    r14
0x180025c96  sub     rsp, 20h
0x180025c9a  cmp     byte ptr [rcx+41h], 0
0x180025c9e  mov     rdi, rcx
0x180025ca1  jnz     loc_180025D49
0x180025ca7  cmp     qword ptr [rcx+30h], 0
0x180025cac  jnz     short loc_180025D19
0x180025cae  call    cs:__imp_GetLastError
0x180025cb4  xor     r8d, r8d; pcbe
0x180025cb7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180025cbe  mov     rdx, rdi; pv
0x180025cc1  mov     ebp, eax
0x180025cc3  call    cs:__imp_CreateThreadpoolTimer
0x180025cc9  mov     rsi, [rdi+30h]
0x180025ccd  mov     r14, rax
0x180025cd0  test    rsi, rsi
0x180025cd3  jz      short loc_180025D0D
0x180025cd5  call    cs:__imp_GetLastError
0x180025cdb  xor     r9d, r9d; msWindowLength
0x180025cde  xor     r8d, r8d; msPeriod
0x180025ce1  xor     edx, edx; pftDueTime
0x180025ce3  mov     rcx, rsi; pti
0x180025ce6  mov     ebx, eax
0x180025ce8  call    cs:__imp_SetThreadpoolTimer
0x180025cee  mov     edx, 1; fCancelPendingCallbacks
0x180025cf3  mov     rcx, rsi; pti
0x180025cf6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025cfc  mov     rcx, rsi; pti
0x180025cff  call    cs:__imp_CloseThreadpoolTimer
0x180025d05  mov     ecx, ebx; dwErrCode
0x180025d07  call    cs:__imp_SetLastError
0x180025d0d  mov     ecx, ebp; dwErrCode
0x180025d0f  mov     [rdi+30h], r14
0x180025d13  call    cs:__imp_SetLastError
0x180025d19  mov     rcx, [rdi+30h]; pti
0x180025d1d  test    rcx, rcx
0x180025d20  jz      short loc_180025D49
0x180025d22  mov     rax, 0FFFFFFFF4D2FA200h
0x180025d2c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180025d31  mov     r9d, 124F8h; msWindowLength
0x180025d37  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180025d3c  xor     r8d, r8d; msPeriod
0x180025d3f  call    cs:__imp_SetThreadpoolTimer
0x180025d45  mov     byte ptr [rdi+41h], 1
0x180025d49  mov     rbx, [rsp+38h+arg_8]
0x180025d4e  mov     rbp, [rsp+38h+arg_10]
0x180025d53  add     rsp, 20h
0x180025d57  pop     r14
0x180025d59  pop     rdi
0x180025d5a  pop     rsi
0x180025d5b  retn
```
