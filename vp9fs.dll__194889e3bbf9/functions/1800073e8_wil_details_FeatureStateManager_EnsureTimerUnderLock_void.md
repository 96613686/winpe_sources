# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800073e8`
- end: `0x1800074d8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008fc4`

## callees

- `0x180004120`
- `0x1800073e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007482`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000741d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000741d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007444`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007457`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007457`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007432`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007432`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007465`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007465`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000746e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000746e`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
0x1800073e8  mov     [rsp+arg_8], rbx
0x1800073ed  mov     [rsp+arg_10], rbp
0x1800073f2  push    rsi
0x1800073f3  push    rdi
0x1800073f4  push    r14
0x1800073f6  sub     rsp, 30h
0x1800073fa  mov     rax, cs:__security_cookie
0x180007401  xor     rax, rsp
0x180007404  mov     [rsp+48h+var_20], rax
0x180007409  cmp     byte ptr [rcx+41h], 0
0x18000740d  mov     rdi, rcx
0x180007410  jnz     loc_1800074B8
0x180007416  cmp     qword ptr [rcx+30h], 0
0x18000741b  jnz     short loc_180007488
0x18000741d  call    cs:__imp_GetLastError
0x180007423  xor     r8d, r8d; pcbe
0x180007426  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000742d  mov     rdx, rdi; pv
0x180007430  mov     ebp, eax
0x180007432  call    cs:__imp_CreateThreadpoolTimer
0x180007438  mov     rsi, [rdi+30h]
0x18000743c  mov     r14, rax
0x18000743f  test    rsi, rsi
0x180007442  jz      short loc_18000747C
0x180007444  call    cs:__imp_GetLastError
0x18000744a  xor     r9d, r9d; msWindowLength
0x18000744d  xor     r8d, r8d; msPeriod
0x180007450  xor     edx, edx; pftDueTime
0x180007452  mov     rcx, rsi; pti
0x180007455  mov     ebx, eax
0x180007457  call    cs:__imp_SetThreadpoolTimer
0x18000745d  mov     edx, 1; fCancelPendingCallbacks
0x180007462  mov     rcx, rsi; pti
0x180007465  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000746b  mov     rcx, rsi; pti
0x18000746e  call    cs:__imp_CloseThreadpoolTimer
0x180007474  mov     ecx, ebx; dwErrCode
0x180007476  call    cs:__imp_SetLastError
0x18000747c  mov     ecx, ebp; dwErrCode
0x18000747e  mov     [rdi+30h], r14
0x180007482  call    cs:__imp_SetLastError
0x180007488  mov     rcx, [rdi+30h]; pti
0x18000748c  test    rcx, rcx
0x18000748f  jz      short loc_1800074B8
0x180007491  mov     rax, 0FFFFFFFF4D2FA200h
0x18000749b  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800074a0  mov     r9d, 124F8h; msWindowLength
0x1800074a6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800074ab  xor     r8d, r8d; msPeriod
0x1800074ae  call    cs:__imp_SetThreadpoolTimer
0x1800074b4  mov     byte ptr [rdi+41h], 1
0x1800074b8  mov     rcx, [rsp+48h+var_20]
0x1800074bd  xor     rcx, rsp; StackCookie
0x1800074c0  call    __security_check_cookie
0x1800074c5  mov     rbx, [rsp+48h+arg_8]
0x1800074ca  mov     rbp, [rsp+48h+arg_10]
0x1800074cf  add     rsp, 30h
0x1800074d3  pop     r14
0x1800074d5  pop     rdi
0x1800074d6  pop     rsi
0x1800074d7  retn
```
