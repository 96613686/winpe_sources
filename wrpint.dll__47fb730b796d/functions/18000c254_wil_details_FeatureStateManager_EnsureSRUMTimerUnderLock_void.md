# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x18000c254`
- end: `0x18000c33e`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dbb4`

## callees

- `0x18000c254`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c2e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c2ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c2e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c2da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c2da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c29e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c29e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c2d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c2d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c2c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c314`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c2c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c314`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x18000c254  mov     [rsp+arg_8], rbx
0x18000c259  mov     [rsp+arg_10], rbp
0x18000c25e  push    rsi
0x18000c25f  push    rdi
0x18000c260  push    r14
0x18000c262  sub     rsp, 30h
0x18000c266  mov     rax, cs:__security_cookie
0x18000c26d  xor     rax, rsp
0x18000c270  mov     [rsp+48h+var_20], rax
0x18000c275  cmp     byte ptr [rcx+40h], 0
0x18000c279  mov     rdi, rcx
0x18000c27c  jnz     loc_18000C31E
0x18000c282  cmp     qword ptr [rcx+38h], 0
0x18000c287  jnz     short loc_18000C2F4
0x18000c289  call    cs:__imp_GetLastError
0x18000c28f  xor     r8d, r8d; pcbe
0x18000c292  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c299  mov     rdx, rdi; pv
0x18000c29c  mov     ebp, eax
0x18000c29e  call    cs:__imp_CreateThreadpoolTimer
0x18000c2a4  mov     rsi, [rdi+38h]
0x18000c2a8  mov     r14, rax
0x18000c2ab  test    rsi, rsi
0x18000c2ae  jz      short loc_18000C2E8
0x18000c2b0  call    cs:__imp_GetLastError
0x18000c2b6  xor     r9d, r9d; msWindowLength
0x18000c2b9  xor     r8d, r8d; msPeriod
0x18000c2bc  xor     edx, edx; pftDueTime
0x18000c2be  mov     rcx, rsi; pti
0x18000c2c1  mov     ebx, eax
0x18000c2c3  call    cs:__imp_SetThreadpoolTimer
0x18000c2c9  mov     edx, 1; fCancelPendingCallbacks
0x18000c2ce  mov     rcx, rsi; pti
0x18000c2d1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c2d7  mov     rcx, rsi; pti
0x18000c2da  call    cs:__imp_CloseThreadpoolTimer
0x18000c2e0  mov     ecx, ebx; dwErrCode
0x18000c2e2  call    cs:__imp_SetLastError
0x18000c2e8  mov     ecx, ebp; dwErrCode
0x18000c2ea  mov     [rdi+38h], r14
0x18000c2ee  call    cs:__imp_SetLastError
0x18000c2f4  mov     rcx, [rdi+38h]; pti
0x18000c2f8  test    rcx, rcx
0x18000c2fb  jz      short loc_18000C31E
0x18000c2fd  mov     r9d, 4E2h; msWindowLength
0x18000c303  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c30c  xor     r8d, r8d; msPeriod
0x18000c30f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000c314  call    cs:__imp_SetThreadpoolTimer
0x18000c31a  mov     byte ptr [rdi+40h], 1
0x18000c31e  mov     rcx, [rsp+48h+var_20]
0x18000c323  xor     rcx, rsp; StackCookie
0x18000c326  call    __security_check_cookie
0x18000c32b  mov     rbx, [rsp+48h+arg_8]
0x18000c330  mov     rbp, [rsp+48h+arg_10]
0x18000c335  add     rsp, 30h
0x18000c339  pop     r14
0x18000c33b  pop     rdi
0x18000c33c  pop     rsi
0x18000c33d  retn
```
