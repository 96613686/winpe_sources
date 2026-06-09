# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000b808`
- end: `0x18000b8dc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c7d0`

## callees

- `0x18000b808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b893`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b855`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b87f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b87f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b876`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b876`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b843`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b843`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b868`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b8bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b868`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b8bf`

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
0x18000b808  mov     [rsp+arg_8], rbx
0x18000b80d  mov     [rsp+arg_10], rbp
0x18000b812  push    rsi
0x18000b813  push    rdi
0x18000b814  push    r14
0x18000b816  sub     rsp, 20h
0x18000b81a  cmp     byte ptr [rcx+41h], 0
0x18000b81e  mov     rdi, rcx
0x18000b821  jnz     loc_18000B8C9
0x18000b827  cmp     qword ptr [rcx+30h], 0
0x18000b82c  jnz     short loc_18000B899
0x18000b82e  call    cs:__imp_GetLastError
0x18000b834  xor     r8d, r8d; pcbe
0x18000b837  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b83e  mov     rdx, rdi; pv
0x18000b841  mov     ebp, eax
0x18000b843  call    cs:__imp_CreateThreadpoolTimer
0x18000b849  mov     rsi, [rdi+30h]
0x18000b84d  mov     r14, rax
0x18000b850  test    rsi, rsi
0x18000b853  jz      short loc_18000B88D
0x18000b855  call    cs:__imp_GetLastError
0x18000b85b  xor     r9d, r9d; msWindowLength
0x18000b85e  xor     r8d, r8d; msPeriod
0x18000b861  xor     edx, edx; pftDueTime
0x18000b863  mov     rcx, rsi; pti
0x18000b866  mov     ebx, eax
0x18000b868  call    cs:__imp_SetThreadpoolTimer
0x18000b86e  mov     edx, 1; fCancelPendingCallbacks
0x18000b873  mov     rcx, rsi; pti
0x18000b876  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b87c  mov     rcx, rsi; pti
0x18000b87f  call    cs:__imp_CloseThreadpoolTimer
0x18000b885  mov     ecx, ebx; dwErrCode
0x18000b887  call    cs:__imp_SetLastError
0x18000b88d  mov     ecx, ebp; dwErrCode
0x18000b88f  mov     [rdi+30h], r14
0x18000b893  call    cs:__imp_SetLastError
0x18000b899  mov     rcx, [rdi+30h]; pti
0x18000b89d  test    rcx, rcx
0x18000b8a0  jz      short loc_18000B8C9
0x18000b8a2  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b8ac  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000b8b1  mov     r9d, 124F8h; msWindowLength
0x18000b8b7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000b8bc  xor     r8d, r8d; msPeriod
0x18000b8bf  call    cs:__imp_SetThreadpoolTimer
0x18000b8c5  mov     byte ptr [rdi+41h], 1
0x18000b8c9  mov     rbx, [rsp+38h+arg_8]
0x18000b8ce  mov     rbp, [rsp+38h+arg_10]
0x18000b8d3  add     rsp, 20h
0x18000b8d7  pop     r14
0x18000b8d9  pop     rdi
0x18000b8da  pop     rsi
0x18000b8db  retn
```
