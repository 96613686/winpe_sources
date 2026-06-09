# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000a960`
- end: `0x18000aa34`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cb08`

## callees

- `0x18000a960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a9ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a9ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a99b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a99b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aa17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aa17`

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
0x18000a960  mov     [rsp+arg_8], rbx
0x18000a965  mov     [rsp+arg_10], rbp
0x18000a96a  push    rsi
0x18000a96b  push    rdi
0x18000a96c  push    r14
0x18000a96e  sub     rsp, 20h
0x18000a972  cmp     byte ptr [rcx+41h], 0
0x18000a976  mov     rdi, rcx
0x18000a979  jnz     loc_18000AA21
0x18000a97f  cmp     qword ptr [rcx+30h], 0
0x18000a984  jnz     short loc_18000A9F1
0x18000a986  call    cs:__imp_GetLastError
0x18000a98c  xor     r8d, r8d; pcbe
0x18000a98f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a996  mov     rdx, rdi; pv
0x18000a999  mov     ebp, eax
0x18000a99b  call    cs:__imp_CreateThreadpoolTimer
0x18000a9a1  mov     rsi, [rdi+30h]
0x18000a9a5  mov     r14, rax
0x18000a9a8  test    rsi, rsi
0x18000a9ab  jz      short loc_18000A9E5
0x18000a9ad  call    cs:__imp_GetLastError
0x18000a9b3  xor     r9d, r9d; msWindowLength
0x18000a9b6  xor     r8d, r8d; msPeriod
0x18000a9b9  xor     edx, edx; pftDueTime
0x18000a9bb  mov     rcx, rsi; pti
0x18000a9be  mov     ebx, eax
0x18000a9c0  call    cs:__imp_SetThreadpoolTimer
0x18000a9c6  mov     edx, 1; fCancelPendingCallbacks
0x18000a9cb  mov     rcx, rsi; pti
0x18000a9ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a9d4  mov     rcx, rsi; pti
0x18000a9d7  call    cs:__imp_CloseThreadpoolTimer
0x18000a9dd  mov     ecx, ebx; dwErrCode
0x18000a9df  call    cs:__imp_SetLastError
0x18000a9e5  mov     ecx, ebp; dwErrCode
0x18000a9e7  mov     [rdi+30h], r14
0x18000a9eb  call    cs:__imp_SetLastError
0x18000a9f1  mov     rcx, [rdi+30h]; pti
0x18000a9f5  test    rcx, rcx
0x18000a9f8  jz      short loc_18000AA21
0x18000a9fa  mov     rax, 0FFFFFFFF4D2FA200h
0x18000aa04  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000aa09  mov     r9d, 124F8h; msWindowLength
0x18000aa0f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000aa14  xor     r8d, r8d; msPeriod
0x18000aa17  call    cs:__imp_SetThreadpoolTimer
0x18000aa1d  mov     byte ptr [rdi+41h], 1
0x18000aa21  mov     rbx, [rsp+38h+arg_8]
0x18000aa26  mov     rbp, [rsp+38h+arg_10]
0x18000aa2b  add     rsp, 20h
0x18000aa2f  pop     r14
0x18000aa31  pop     rdi
0x18000aa32  pop     rsi
0x18000aa33  retn
```
