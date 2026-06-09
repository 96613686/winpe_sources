# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000c3f8`
- end: `0x18000c4e8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000def4`

## callees

- `0x18000c3f8`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c492`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c454`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c47e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c47e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c442`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c442`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c475`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c475`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c467`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c4be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c467`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c4be`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x18000c3f8  mov     [rsp+arg_8], rbx
0x18000c3fd  mov     [rsp+arg_10], rbp
0x18000c402  push    rsi
0x18000c403  push    rdi
0x18000c404  push    r14
0x18000c406  sub     rsp, 30h
0x18000c40a  mov     rax, cs:__security_cookie
0x18000c411  xor     rax, rsp
0x18000c414  mov     [rsp+48h+var_20], rax
0x18000c419  cmp     byte ptr [rcx+41h], 0
0x18000c41d  mov     rdi, rcx
0x18000c420  jnz     loc_18000C4C8
0x18000c426  cmp     qword ptr [rcx+30h], 0
0x18000c42b  jnz     short loc_18000C498
0x18000c42d  call    cs:__imp_GetLastError
0x18000c433  xor     r8d, r8d; pcbe
0x18000c436  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c43d  mov     rdx, rdi; pv
0x18000c440  mov     ebp, eax
0x18000c442  call    cs:__imp_CreateThreadpoolTimer
0x18000c448  mov     rsi, [rdi+30h]
0x18000c44c  mov     r14, rax
0x18000c44f  test    rsi, rsi
0x18000c452  jz      short loc_18000C48C
0x18000c454  call    cs:__imp_GetLastError
0x18000c45a  xor     r9d, r9d; msWindowLength
0x18000c45d  xor     r8d, r8d; msPeriod
0x18000c460  xor     edx, edx; pftDueTime
0x18000c462  mov     rcx, rsi; pti
0x18000c465  mov     ebx, eax
0x18000c467  call    cs:__imp_SetThreadpoolTimer
0x18000c46d  mov     edx, 1; fCancelPendingCallbacks
0x18000c472  mov     rcx, rsi; pti
0x18000c475  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c47b  mov     rcx, rsi; pti
0x18000c47e  call    cs:__imp_CloseThreadpoolTimer
0x18000c484  mov     ecx, ebx; dwErrCode
0x18000c486  call    cs:__imp_SetLastError
0x18000c48c  mov     ecx, ebp; dwErrCode
0x18000c48e  mov     [rdi+30h], r14
0x18000c492  call    cs:__imp_SetLastError
0x18000c498  mov     rcx, [rdi+30h]; pti
0x18000c49c  test    rcx, rcx
0x18000c49f  jz      short loc_18000C4C8
0x18000c4a1  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c4ab  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000c4b0  mov     r9d, 124F8h; msWindowLength
0x18000c4b6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000c4bb  xor     r8d, r8d; msPeriod
0x18000c4be  call    cs:__imp_SetThreadpoolTimer
0x18000c4c4  mov     byte ptr [rdi+41h], 1
0x18000c4c8  mov     rcx, [rsp+48h+var_20]
0x18000c4cd  xor     rcx, rsp; StackCookie
0x18000c4d0  call    __security_check_cookie
0x18000c4d5  mov     rbx, [rsp+48h+arg_8]
0x18000c4da  mov     rbp, [rsp+48h+arg_10]
0x18000c4df  add     rsp, 30h
0x18000c4e3  pop     r14
0x18000c4e5  pop     rdi
0x18000c4e6  pop     rsi
0x18000c4e7  retn
```
