# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005e94`
- end: `0x180005f68`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a164`

## callees

- `0x180005e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ee1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ef4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f4b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ef4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f4b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005ecf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005ecf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f0b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f02`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f02`

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
0x180005e94  mov     [rsp+arg_8], rbx
0x180005e99  mov     [rsp+arg_10], rbp
0x180005e9e  push    rsi
0x180005e9f  push    rdi
0x180005ea0  push    r14
0x180005ea2  sub     rsp, 20h
0x180005ea6  cmp     byte ptr [rcx+41h], 0
0x180005eaa  mov     rdi, rcx
0x180005ead  jnz     loc_180005F55
0x180005eb3  cmp     qword ptr [rcx+30h], 0
0x180005eb8  jnz     short loc_180005F25
0x180005eba  call    cs:__imp_GetLastError
0x180005ec0  xor     r8d, r8d; pcbe
0x180005ec3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005eca  mov     rdx, rdi; pv
0x180005ecd  mov     ebp, eax
0x180005ecf  call    cs:__imp_CreateThreadpoolTimer
0x180005ed5  mov     rsi, [rdi+30h]
0x180005ed9  mov     r14, rax
0x180005edc  test    rsi, rsi
0x180005edf  jz      short loc_180005F19
0x180005ee1  call    cs:__imp_GetLastError
0x180005ee7  xor     r9d, r9d; msWindowLength
0x180005eea  xor     r8d, r8d; msPeriod
0x180005eed  xor     edx, edx; pftDueTime
0x180005eef  mov     rcx, rsi; pti
0x180005ef2  mov     ebx, eax
0x180005ef4  call    cs:__imp_SetThreadpoolTimer
0x180005efa  mov     edx, 1; fCancelPendingCallbacks
0x180005eff  mov     rcx, rsi; pti
0x180005f02  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005f08  mov     rcx, rsi; pti
0x180005f0b  call    cs:__imp_CloseThreadpoolTimer
0x180005f11  mov     ecx, ebx; dwErrCode
0x180005f13  call    cs:__imp_SetLastError
0x180005f19  mov     ecx, ebp; dwErrCode
0x180005f1b  mov     [rdi+30h], r14
0x180005f1f  call    cs:__imp_SetLastError
0x180005f25  mov     rcx, [rdi+30h]; pti
0x180005f29  test    rcx, rcx
0x180005f2c  jz      short loc_180005F55
0x180005f2e  mov     rax, 0FFFFFFFF4D2FA200h
0x180005f38  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005f3d  mov     r9d, 124F8h; msWindowLength
0x180005f43  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005f48  xor     r8d, r8d; msPeriod
0x180005f4b  call    cs:__imp_SetThreadpoolTimer
0x180005f51  mov     byte ptr [rdi+41h], 1
0x180005f55  mov     rbx, [rsp+38h+arg_8]
0x180005f5a  mov     rbp, [rsp+38h+arg_10]
0x180005f5f  add     rsp, 20h
0x180005f63  pop     r14
0x180005f65  pop     rdi
0x180005f66  pop     rsi
0x180005f67  retn
```
