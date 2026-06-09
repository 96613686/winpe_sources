# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x180007244`
- end: `0x18000732e`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c38`

## callees

- `0x180004120`
- `0x180007244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800072b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007304`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800072b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007304`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000728e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000728e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800072c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800072c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800072ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800072ca`

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
0x180007244  mov     [rsp+arg_8], rbx
0x180007249  mov     [rsp+arg_10], rbp
0x18000724e  push    rsi
0x18000724f  push    rdi
0x180007250  push    r14
0x180007252  sub     rsp, 30h
0x180007256  mov     rax, cs:__security_cookie
0x18000725d  xor     rax, rsp
0x180007260  mov     [rsp+48h+var_20], rax
0x180007265  cmp     byte ptr [rcx+40h], 0
0x180007269  mov     rdi, rcx
0x18000726c  jnz     loc_18000730E
0x180007272  cmp     qword ptr [rcx+38h], 0
0x180007277  jnz     short loc_1800072E4
0x180007279  call    cs:__imp_GetLastError
0x18000727f  xor     r8d, r8d; pcbe
0x180007282  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007289  mov     rdx, rdi; pv
0x18000728c  mov     ebp, eax
0x18000728e  call    cs:__imp_CreateThreadpoolTimer
0x180007294  mov     rsi, [rdi+38h]
0x180007298  mov     r14, rax
0x18000729b  test    rsi, rsi
0x18000729e  jz      short loc_1800072D8
0x1800072a0  call    cs:__imp_GetLastError
0x1800072a6  xor     r9d, r9d; msWindowLength
0x1800072a9  xor     r8d, r8d; msPeriod
0x1800072ac  xor     edx, edx; pftDueTime
0x1800072ae  mov     rcx, rsi; pti
0x1800072b1  mov     ebx, eax
0x1800072b3  call    cs:__imp_SetThreadpoolTimer
0x1800072b9  mov     edx, 1; fCancelPendingCallbacks
0x1800072be  mov     rcx, rsi; pti
0x1800072c1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800072c7  mov     rcx, rsi; pti
0x1800072ca  call    cs:__imp_CloseThreadpoolTimer
0x1800072d0  mov     ecx, ebx; dwErrCode
0x1800072d2  call    cs:__imp_SetLastError
0x1800072d8  mov     ecx, ebp; dwErrCode
0x1800072da  mov     [rdi+38h], r14
0x1800072de  call    cs:__imp_SetLastError
0x1800072e4  mov     rcx, [rdi+38h]; pti
0x1800072e8  test    rcx, rcx
0x1800072eb  jz      short loc_18000730E
0x1800072ed  mov     r9d, 4E2h; msWindowLength
0x1800072f3  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800072fc  xor     r8d, r8d; msPeriod
0x1800072ff  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180007304  call    cs:__imp_SetThreadpoolTimer
0x18000730a  mov     byte ptr [rdi+40h], 1
0x18000730e  mov     rcx, [rsp+48h+var_20]
0x180007313  xor     rcx, rsp; StackCookie
0x180007316  call    __security_check_cookie
0x18000731b  mov     rbx, [rsp+48h+arg_8]
0x180007320  mov     rbp, [rsp+48h+arg_10]
0x180007325  add     rsp, 30h
0x180007329  pop     r14
0x18000732b  pop     rdi
0x18000732c  pop     rsi
0x18000732d  retn
```
