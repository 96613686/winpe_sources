# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180006804`
- end: `0x1800068d8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800091f4`

## callees

- `0x180006804`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000688f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000688f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000682a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000682a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006851`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000687b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000687b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006872`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006872`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006864`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006864`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068bb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000683f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000683f`

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
0x180006804  mov     [rsp+arg_8], rbx
0x180006809  mov     [rsp+arg_10], rbp
0x18000680e  push    rsi
0x18000680f  push    rdi
0x180006810  push    r14
0x180006812  sub     rsp, 20h
0x180006816  cmp     byte ptr [rcx+41h], 0
0x18000681a  mov     rdi, rcx
0x18000681d  jnz     loc_1800068C5
0x180006823  cmp     qword ptr [rcx+30h], 0
0x180006828  jnz     short loc_180006895
0x18000682a  call    cs:__imp_GetLastError
0x180006830  xor     r8d, r8d; pcbe
0x180006833  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000683a  mov     rdx, rdi; pv
0x18000683d  mov     ebp, eax
0x18000683f  call    cs:__imp_CreateThreadpoolTimer
0x180006845  mov     rsi, [rdi+30h]
0x180006849  mov     r14, rax
0x18000684c  test    rsi, rsi
0x18000684f  jz      short loc_180006889
0x180006851  call    cs:__imp_GetLastError
0x180006857  xor     r9d, r9d; msWindowLength
0x18000685a  xor     r8d, r8d; msPeriod
0x18000685d  xor     edx, edx; pftDueTime
0x18000685f  mov     rcx, rsi; pti
0x180006862  mov     ebx, eax
0x180006864  call    cs:__imp_SetThreadpoolTimer
0x18000686a  mov     edx, 1; fCancelPendingCallbacks
0x18000686f  mov     rcx, rsi; pti
0x180006872  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006878  mov     rcx, rsi; pti
0x18000687b  call    cs:__imp_CloseThreadpoolTimer
0x180006881  mov     ecx, ebx; dwErrCode
0x180006883  call    cs:__imp_SetLastError
0x180006889  mov     ecx, ebp; dwErrCode
0x18000688b  mov     [rdi+30h], r14
0x18000688f  call    cs:__imp_SetLastError
0x180006895  mov     rcx, [rdi+30h]; pti
0x180006899  test    rcx, rcx
0x18000689c  jz      short loc_1800068C5
0x18000689e  mov     rax, 0FFFFFFFF4D2FA200h
0x1800068a8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800068ad  mov     r9d, 124F8h; msWindowLength
0x1800068b3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800068b8  xor     r8d, r8d; msPeriod
0x1800068bb  call    cs:__imp_SetThreadpoolTimer
0x1800068c1  mov     byte ptr [rdi+41h], 1
0x1800068c5  mov     rbx, [rsp+38h+arg_8]
0x1800068ca  mov     rbp, [rsp+38h+arg_10]
0x1800068cf  add     rsp, 20h
0x1800068d3  pop     r14
0x1800068d5  pop     rdi
0x1800068d6  pop     rsi
0x1800068d7  retn
```
