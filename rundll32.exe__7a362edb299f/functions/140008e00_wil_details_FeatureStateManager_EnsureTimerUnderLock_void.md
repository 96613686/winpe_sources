# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140008e00`
- end: `0x140008ed4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000964c`

## callees

- `0x140008e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e8b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008e3b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008e3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008e6e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008e6e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008e77`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008e77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008e60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008eb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008e60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008eb7`

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
0x140008e00  mov     [rsp+arg_8], rbx
0x140008e05  mov     [rsp+arg_10], rbp
0x140008e0a  push    rsi
0x140008e0b  push    rdi
0x140008e0c  push    r14
0x140008e0e  sub     rsp, 20h
0x140008e12  cmp     byte ptr [rcx+41h], 0
0x140008e16  mov     rdi, rcx
0x140008e19  jnz     loc_140008EC1
0x140008e1f  cmp     qword ptr [rcx+30h], 0
0x140008e24  jnz     short loc_140008E91
0x140008e26  call    cs:__imp_GetLastError
0x140008e2c  xor     r8d, r8d; pcbe
0x140008e2f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008e36  mov     rdx, rdi; pv
0x140008e39  mov     ebp, eax
0x140008e3b  call    cs:__imp_CreateThreadpoolTimer
0x140008e41  mov     rsi, [rdi+30h]
0x140008e45  mov     r14, rax
0x140008e48  test    rsi, rsi
0x140008e4b  jz      short loc_140008E85
0x140008e4d  call    cs:__imp_GetLastError
0x140008e53  xor     r9d, r9d; msWindowLength
0x140008e56  xor     r8d, r8d; msPeriod
0x140008e59  xor     edx, edx; pftDueTime
0x140008e5b  mov     rcx, rsi; pti
0x140008e5e  mov     ebx, eax
0x140008e60  call    cs:__imp_SetThreadpoolTimer
0x140008e66  mov     edx, 1; fCancelPendingCallbacks
0x140008e6b  mov     rcx, rsi; pti
0x140008e6e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008e74  mov     rcx, rsi; pti
0x140008e77  call    cs:__imp_CloseThreadpoolTimer
0x140008e7d  mov     ecx, ebx; dwErrCode
0x140008e7f  call    cs:__imp_SetLastError
0x140008e85  mov     ecx, ebp; dwErrCode
0x140008e87  mov     [rdi+30h], r14
0x140008e8b  call    cs:__imp_SetLastError
0x140008e91  mov     rcx, [rdi+30h]; pti
0x140008e95  test    rcx, rcx
0x140008e98  jz      short loc_140008EC1
0x140008e9a  mov     rax, 0FFFFFFFF4D2FA200h
0x140008ea4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140008ea9  mov     r9d, 124F8h; msWindowLength
0x140008eaf  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140008eb4  xor     r8d, r8d; msPeriod
0x140008eb7  call    cs:__imp_SetThreadpoolTimer
0x140008ebd  mov     byte ptr [rdi+41h], 1
0x140008ec1  mov     rbx, [rsp+38h+arg_8]
0x140008ec6  mov     rbp, [rsp+38h+arg_10]
0x140008ecb  add     rsp, 20h
0x140008ecf  pop     r14
0x140008ed1  pop     rdi
0x140008ed2  pop     rsi
0x140008ed3  retn
```
