# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x140009cf0`
- end: `0x140009dda`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b808`

## callees

- `0x140005360`
- `0x140009cf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009d8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009d5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009db0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009d5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009db0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009d76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009d76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009d3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009d3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009d6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009d6d`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 64) )
  {
    if ( !pv[7] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[7];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[7] = v5;
      SetLastError(LastError);
    }
    v7 = pv[7];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x4E2u);
      *((_BYTE *)pv + 64) = 1;
    }
  }
}

```

## disassembly

```asm
0x140009cf0  mov     [rsp+arg_8], rbx
0x140009cf5  mov     [rsp+arg_10], rbp
0x140009cfa  push    rsi
0x140009cfb  push    rdi
0x140009cfc  push    r14
0x140009cfe  sub     rsp, 30h
0x140009d02  mov     rax, cs:__security_cookie
0x140009d09  xor     rax, rsp
0x140009d0c  mov     [rsp+48h+var_20], rax
0x140009d11  cmp     byte ptr [rcx+40h], 0
0x140009d15  mov     rdi, rcx
0x140009d18  jnz     loc_140009DBA
0x140009d1e  cmp     qword ptr [rcx+38h], 0
0x140009d23  jnz     short loc_140009D90
0x140009d25  call    cs:__imp_GetLastError
0x140009d2b  xor     r8d, r8d; pcbe
0x140009d2e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009d35  mov     rdx, rdi; pv
0x140009d38  mov     ebp, eax
0x140009d3a  call    cs:__imp_CreateThreadpoolTimer
0x140009d40  mov     rsi, [rdi+38h]
0x140009d44  mov     r14, rax
0x140009d47  test    rsi, rsi
0x140009d4a  jz      short loc_140009D84
0x140009d4c  call    cs:__imp_GetLastError
0x140009d52  xor     r9d, r9d; msWindowLength
0x140009d55  xor     r8d, r8d; msPeriod
0x140009d58  xor     edx, edx; pftDueTime
0x140009d5a  mov     rcx, rsi; pti
0x140009d5d  mov     ebx, eax
0x140009d5f  call    cs:__imp_SetThreadpoolTimer
0x140009d65  mov     edx, 1; fCancelPendingCallbacks
0x140009d6a  mov     rcx, rsi; pti
0x140009d6d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009d73  mov     rcx, rsi; pti
0x140009d76  call    cs:__imp_CloseThreadpoolTimer
0x140009d7c  mov     ecx, ebx; dwErrCode
0x140009d7e  call    cs:__imp_SetLastError
0x140009d84  mov     ecx, ebp; dwErrCode
0x140009d86  mov     [rdi+38h], r14
0x140009d8a  call    cs:__imp_SetLastError
0x140009d90  mov     rcx, [rdi+38h]; pti
0x140009d94  test    rcx, rcx
0x140009d97  jz      short loc_140009DBA
0x140009d99  mov     r9d, 4E2h; msWindowLength
0x140009d9f  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140009da8  xor     r8d, r8d; msPeriod
0x140009dab  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140009db0  call    cs:__imp_SetThreadpoolTimer
0x140009db6  mov     byte ptr [rdi+40h], 1
0x140009dba  mov     rcx, [rsp+48h+var_20]
0x140009dbf  xor     rcx, rsp; StackCookie
0x140009dc2  call    __security_check_cookie
0x140009dc7  mov     rbx, [rsp+48h+arg_8]
0x140009dcc  mov     rbp, [rsp+48h+arg_10]
0x140009dd1  add     rsp, 30h
0x140009dd5  pop     r14
0x140009dd7  pop     rdi
0x140009dd8  pop     rsi
0x140009dd9  retn
```
