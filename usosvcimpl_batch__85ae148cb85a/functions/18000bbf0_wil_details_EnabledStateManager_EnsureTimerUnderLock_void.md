# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000bbf0`
- end: `0x18000bce0`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bfc8`

## callees

- `0x18000bbf0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bc5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bcb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bc5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bcb6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bc3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bc3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bc76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bc76`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bc6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bc6d`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 24) )
  {
    if ( !pv[2] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v4 = pv[2];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[2] = v5;
      SetLastError(LastError);
    }
    v7 = pv[2];
    if ( v7 )
    {
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x18000bbf0  mov     [rsp+arg_8], rbx
0x18000bbf5  mov     [rsp+arg_10], rbp
0x18000bbfa  push    rsi
0x18000bbfb  push    rdi
0x18000bbfc  push    r14
0x18000bbfe  sub     rsp, 30h
0x18000bc02  mov     rax, cs:__security_cookie
0x18000bc09  xor     rax, rsp
0x18000bc0c  mov     [rsp+48h+var_20], rax
0x18000bc11  cmp     byte ptr [rcx+18h], 0
0x18000bc15  mov     rdi, rcx
0x18000bc18  jnz     loc_18000BCC0
0x18000bc1e  cmp     qword ptr [rcx+10h], 0
0x18000bc23  jnz     short loc_18000BC90
0x18000bc25  call    cs:__imp_GetLastError
0x18000bc2b  xor     r8d, r8d; pcbe
0x18000bc2e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000bc35  mov     rdx, rdi; pv
0x18000bc38  mov     ebp, eax
0x18000bc3a  call    cs:__imp_CreateThreadpoolTimer
0x18000bc40  mov     rsi, [rdi+10h]
0x18000bc44  mov     r14, rax
0x18000bc47  test    rsi, rsi
0x18000bc4a  jz      short loc_18000BC84
0x18000bc4c  call    cs:__imp_GetLastError
0x18000bc52  xor     r9d, r9d; msWindowLength
0x18000bc55  xor     r8d, r8d; msPeriod
0x18000bc58  xor     edx, edx; pftDueTime
0x18000bc5a  mov     rcx, rsi; pti
0x18000bc5d  mov     ebx, eax
0x18000bc5f  call    cs:__imp_SetThreadpoolTimer
0x18000bc65  mov     edx, 1; fCancelPendingCallbacks
0x18000bc6a  mov     rcx, rsi; pti
0x18000bc6d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bc73  mov     rcx, rsi; pti
0x18000bc76  call    cs:__imp_CloseThreadpoolTimer
0x18000bc7c  mov     ecx, ebx; dwErrCode
0x18000bc7e  call    cs:__imp_SetLastError
0x18000bc84  mov     ecx, ebp; dwErrCode
0x18000bc86  mov     [rdi+10h], r14
0x18000bc8a  call    cs:__imp_SetLastError
0x18000bc90  mov     rcx, [rdi+10h]; pti
0x18000bc94  test    rcx, rcx
0x18000bc97  jz      short loc_18000BCC0
0x18000bc99  mov     rax, 0FFFFFFFF4D2FA200h
0x18000bca3  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000bca8  mov     r9d, 124F8h; msWindowLength
0x18000bcae  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000bcb3  xor     r8d, r8d; msPeriod
0x18000bcb6  call    cs:__imp_SetThreadpoolTimer
0x18000bcbc  mov     byte ptr [rdi+18h], 1
0x18000bcc0  mov     rcx, [rsp+48h+var_20]
0x18000bcc5  xor     rcx, rsp; StackCookie
0x18000bcc8  call    __security_check_cookie
0x18000bccd  mov     rbx, [rsp+48h+arg_8]
0x18000bcd2  mov     rbp, [rsp+48h+arg_10]
0x18000bcd7  add     rsp, 30h
0x18000bcdb  pop     r14
0x18000bcdd  pop     rdi
0x18000bcde  pop     rsi
0x18000bcdf  retn
```
