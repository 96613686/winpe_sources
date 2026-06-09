# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180007428`
- end: `0x1800074fc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000acb4`

## callees

- `0x180007428`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007475`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007463`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007463`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007488`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007488`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007496`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007496`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000749f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000749f`

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
0x180007428  mov     [rsp+arg_8], rbx
0x18000742d  mov     [rsp+arg_10], rbp
0x180007432  push    rsi
0x180007433  push    rdi
0x180007434  push    r14
0x180007436  sub     rsp, 20h
0x18000743a  cmp     byte ptr [rcx+41h], 0
0x18000743e  mov     rdi, rcx
0x180007441  jnz     loc_1800074E9
0x180007447  cmp     qword ptr [rcx+30h], 0
0x18000744c  jnz     short loc_1800074B9
0x18000744e  call    cs:__imp_GetLastError
0x180007454  xor     r8d, r8d; pcbe
0x180007457  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000745e  mov     rdx, rdi; pv
0x180007461  mov     ebp, eax
0x180007463  call    cs:__imp_CreateThreadpoolTimer
0x180007469  mov     rsi, [rdi+30h]
0x18000746d  mov     r14, rax
0x180007470  test    rsi, rsi
0x180007473  jz      short loc_1800074AD
0x180007475  call    cs:__imp_GetLastError
0x18000747b  xor     r9d, r9d; msWindowLength
0x18000747e  xor     r8d, r8d; msPeriod
0x180007481  xor     edx, edx; pftDueTime
0x180007483  mov     rcx, rsi; pti
0x180007486  mov     ebx, eax
0x180007488  call    cs:__imp_SetThreadpoolTimer
0x18000748e  mov     edx, 1; fCancelPendingCallbacks
0x180007493  mov     rcx, rsi; pti
0x180007496  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000749c  mov     rcx, rsi; pti
0x18000749f  call    cs:__imp_CloseThreadpoolTimer
0x1800074a5  mov     ecx, ebx; dwErrCode
0x1800074a7  call    cs:__imp_SetLastError
0x1800074ad  mov     ecx, ebp; dwErrCode
0x1800074af  mov     [rdi+30h], r14
0x1800074b3  call    cs:__imp_SetLastError
0x1800074b9  mov     rcx, [rdi+30h]; pti
0x1800074bd  test    rcx, rcx
0x1800074c0  jz      short loc_1800074E9
0x1800074c2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800074cc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800074d1  mov     r9d, 124F8h; msWindowLength
0x1800074d7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800074dc  xor     r8d, r8d; msPeriod
0x1800074df  call    cs:__imp_SetThreadpoolTimer
0x1800074e5  mov     byte ptr [rdi+41h], 1
0x1800074e9  mov     rbx, [rsp+38h+arg_8]
0x1800074ee  mov     rbp, [rsp+38h+arg_10]
0x1800074f3  add     rsp, 20h
0x1800074f7  pop     r14
0x1800074f9  pop     rdi
0x1800074fa  pop     rsi
0x1800074fb  retn
```
