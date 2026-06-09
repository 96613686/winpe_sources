# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005dbc`
- end: `0x180005e90`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800078e4`

## callees

- `0x180005dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005e33`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005e33`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005df7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005df7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e73`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005e2a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005e2a`

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
0x180005dbc  mov     [rsp+arg_8], rbx
0x180005dc1  mov     [rsp+arg_10], rbp
0x180005dc6  push    rsi
0x180005dc7  push    rdi
0x180005dc8  push    r14
0x180005dca  sub     rsp, 20h
0x180005dce  cmp     byte ptr [rcx+41h], 0
0x180005dd2  mov     rdi, rcx
0x180005dd5  jnz     loc_180005E7D
0x180005ddb  cmp     qword ptr [rcx+30h], 0
0x180005de0  jnz     short loc_180005E4D
0x180005de2  call    cs:__imp_GetLastError
0x180005de8  xor     r8d, r8d; pcbe
0x180005deb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005df2  mov     rdx, rdi; pv
0x180005df5  mov     ebp, eax
0x180005df7  call    cs:__imp_CreateThreadpoolTimer
0x180005dfd  mov     rsi, [rdi+30h]
0x180005e01  mov     r14, rax
0x180005e04  test    rsi, rsi
0x180005e07  jz      short loc_180005E41
0x180005e09  call    cs:__imp_GetLastError
0x180005e0f  xor     r9d, r9d; msWindowLength
0x180005e12  xor     r8d, r8d; msPeriod
0x180005e15  xor     edx, edx; pftDueTime
0x180005e17  mov     rcx, rsi; pti
0x180005e1a  mov     ebx, eax
0x180005e1c  call    cs:__imp_SetThreadpoolTimer
0x180005e22  mov     edx, 1; fCancelPendingCallbacks
0x180005e27  mov     rcx, rsi; pti
0x180005e2a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005e30  mov     rcx, rsi; pti
0x180005e33  call    cs:__imp_CloseThreadpoolTimer
0x180005e39  mov     ecx, ebx; dwErrCode
0x180005e3b  call    cs:__imp_SetLastError
0x180005e41  mov     ecx, ebp; dwErrCode
0x180005e43  mov     [rdi+30h], r14
0x180005e47  call    cs:__imp_SetLastError
0x180005e4d  mov     rcx, [rdi+30h]; pti
0x180005e51  test    rcx, rcx
0x180005e54  jz      short loc_180005E7D
0x180005e56  mov     rax, 0FFFFFFFF4D2FA200h
0x180005e60  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005e65  mov     r9d, 124F8h; msWindowLength
0x180005e6b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005e70  xor     r8d, r8d; msPeriod
0x180005e73  call    cs:__imp_SetThreadpoolTimer
0x180005e79  mov     byte ptr [rdi+41h], 1
0x180005e7d  mov     rbx, [rsp+38h+arg_8]
0x180005e82  mov     rbp, [rsp+38h+arg_10]
0x180005e87  add     rsp, 20h
0x180005e8b  pop     r14
0x180005e8d  pop     rdi
0x180005e8e  pop     rsi
0x180005e8f  retn
```
