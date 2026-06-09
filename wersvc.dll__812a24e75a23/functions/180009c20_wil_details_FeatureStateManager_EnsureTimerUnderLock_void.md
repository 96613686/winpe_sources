# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009c20`
- end: `0x180009cf4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b6a0`

## callees

- `0x180009c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009c8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009c8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009c97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009c97`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009c5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009c5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009c80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009cd7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009c80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009cd7`

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
0x180009c20  mov     [rsp+arg_8], rbx
0x180009c25  mov     [rsp+arg_10], rbp
0x180009c2a  push    rsi
0x180009c2b  push    rdi
0x180009c2c  push    r14
0x180009c2e  sub     rsp, 20h
0x180009c32  cmp     byte ptr [rcx+41h], 0
0x180009c36  mov     rdi, rcx
0x180009c39  jnz     loc_180009CE1
0x180009c3f  cmp     qword ptr [rcx+30h], 0
0x180009c44  jnz     short loc_180009CB1
0x180009c46  call    cs:__imp_GetLastError
0x180009c4c  xor     r8d, r8d; pcbe
0x180009c4f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009c56  mov     rdx, rdi; pv
0x180009c59  mov     ebp, eax
0x180009c5b  call    cs:__imp_CreateThreadpoolTimer
0x180009c61  mov     rsi, [rdi+30h]
0x180009c65  mov     r14, rax
0x180009c68  test    rsi, rsi
0x180009c6b  jz      short loc_180009CA5
0x180009c6d  call    cs:__imp_GetLastError
0x180009c73  xor     r9d, r9d; msWindowLength
0x180009c76  xor     r8d, r8d; msPeriod
0x180009c79  xor     edx, edx; pftDueTime
0x180009c7b  mov     rcx, rsi; pti
0x180009c7e  mov     ebx, eax
0x180009c80  call    cs:__imp_SetThreadpoolTimer
0x180009c86  mov     edx, 1; fCancelPendingCallbacks
0x180009c8b  mov     rcx, rsi; pti
0x180009c8e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009c94  mov     rcx, rsi; pti
0x180009c97  call    cs:__imp_CloseThreadpoolTimer
0x180009c9d  mov     ecx, ebx; dwErrCode
0x180009c9f  call    cs:__imp_SetLastError
0x180009ca5  mov     ecx, ebp; dwErrCode
0x180009ca7  mov     [rdi+30h], r14
0x180009cab  call    cs:__imp_SetLastError
0x180009cb1  mov     rcx, [rdi+30h]; pti
0x180009cb5  test    rcx, rcx
0x180009cb8  jz      short loc_180009CE1
0x180009cba  mov     rax, 0FFFFFFFF4D2FA200h
0x180009cc4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180009cc9  mov     r9d, 124F8h; msWindowLength
0x180009ccf  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180009cd4  xor     r8d, r8d; msPeriod
0x180009cd7  call    cs:__imp_SetThreadpoolTimer
0x180009cdd  mov     byte ptr [rdi+41h], 1
0x180009ce1  mov     rbx, [rsp+38h+arg_8]
0x180009ce6  mov     rbp, [rsp+38h+arg_10]
0x180009ceb  add     rsp, 20h
0x180009cef  pop     r14
0x180009cf1  pop     rdi
0x180009cf2  pop     rsi
0x180009cf3  retn
```
