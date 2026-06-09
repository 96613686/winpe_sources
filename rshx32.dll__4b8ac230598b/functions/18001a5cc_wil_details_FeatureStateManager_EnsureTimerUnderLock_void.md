# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001a5cc`
- end: `0x18001a6a0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b53c`

## callees

- `0x18001a5cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a64b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a64b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a619`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a643`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a643`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a63a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a63a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a62c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a683`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a62c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a683`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a607`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a607`

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
0x18001a5cc  mov     [rsp+arg_8], rbx
0x18001a5d1  mov     [rsp+arg_10], rbp
0x18001a5d6  push    rsi
0x18001a5d7  push    rdi
0x18001a5d8  push    r14
0x18001a5da  sub     rsp, 20h
0x18001a5de  cmp     byte ptr [rcx+41h], 0
0x18001a5e2  mov     rdi, rcx
0x18001a5e5  jnz     loc_18001A68D
0x18001a5eb  cmp     qword ptr [rcx+30h], 0
0x18001a5f0  jnz     short loc_18001A65D
0x18001a5f2  call    cs:__imp_GetLastError
0x18001a5f8  xor     r8d, r8d; pcbe
0x18001a5fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a602  mov     rdx, rdi; pv
0x18001a605  mov     ebp, eax
0x18001a607  call    cs:__imp_CreateThreadpoolTimer
0x18001a60d  mov     rsi, [rdi+30h]
0x18001a611  mov     r14, rax
0x18001a614  test    rsi, rsi
0x18001a617  jz      short loc_18001A651
0x18001a619  call    cs:__imp_GetLastError
0x18001a61f  xor     r9d, r9d; msWindowLength
0x18001a622  xor     r8d, r8d; msPeriod
0x18001a625  xor     edx, edx; pftDueTime
0x18001a627  mov     rcx, rsi; pti
0x18001a62a  mov     ebx, eax
0x18001a62c  call    cs:__imp_SetThreadpoolTimer
0x18001a632  mov     edx, 1; fCancelPendingCallbacks
0x18001a637  mov     rcx, rsi; pti
0x18001a63a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001a640  mov     rcx, rsi; pti
0x18001a643  call    cs:__imp_CloseThreadpoolTimer
0x18001a649  mov     ecx, ebx; dwErrCode
0x18001a64b  call    cs:__imp_SetLastError
0x18001a651  mov     ecx, ebp; dwErrCode
0x18001a653  mov     [rdi+30h], r14
0x18001a657  call    cs:__imp_SetLastError
0x18001a65d  mov     rcx, [rdi+30h]; pti
0x18001a661  test    rcx, rcx
0x18001a664  jz      short loc_18001A68D
0x18001a666  mov     rax, 0FFFFFFFF4D2FA200h
0x18001a670  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18001a675  mov     r9d, 124F8h; msWindowLength
0x18001a67b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001a680  xor     r8d, r8d; msPeriod
0x18001a683  call    cs:__imp_SetThreadpoolTimer
0x18001a689  mov     byte ptr [rdi+41h], 1
0x18001a68d  mov     rbx, [rsp+38h+arg_8]
0x18001a692  mov     rbp, [rsp+38h+arg_10]
0x18001a697  add     rsp, 20h
0x18001a69b  pop     r14
0x18001a69d  pop     rdi
0x18001a69e  pop     rsi
0x18001a69f  retn
```
