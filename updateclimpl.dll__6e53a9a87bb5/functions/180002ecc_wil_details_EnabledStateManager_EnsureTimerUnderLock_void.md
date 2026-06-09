# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x180002ecc`
- end: `0x180002fbc`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003248`

## callees

- `0x180002ecc`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f28`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002f16`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002f16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002f52`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002f52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002f49`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002f49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002f3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002f92`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002f3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002f92`

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
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x180002ecc  mov     [rsp+arg_8], rbx
0x180002ed1  mov     [rsp+arg_10], rbp
0x180002ed6  push    rsi
0x180002ed7  push    rdi
0x180002ed8  push    r14
0x180002eda  sub     rsp, 30h
0x180002ede  mov     rax, cs:__security_cookie
0x180002ee5  xor     rax, rsp
0x180002ee8  mov     [rsp+48h+var_20], rax
0x180002eed  cmp     byte ptr [rcx+18h], 0
0x180002ef1  mov     rdi, rcx
0x180002ef4  jnz     loc_180002F9C
0x180002efa  cmp     qword ptr [rcx+10h], 0
0x180002eff  jnz     short loc_180002F6C
0x180002f01  call    cs:__imp_GetLastError
0x180002f07  xor     r8d, r8d; pcbe
0x180002f0a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180002f11  mov     rdx, rdi; pv
0x180002f14  mov     ebp, eax
0x180002f16  call    cs:__imp_CreateThreadpoolTimer
0x180002f1c  mov     rsi, [rdi+10h]
0x180002f20  mov     r14, rax
0x180002f23  test    rsi, rsi
0x180002f26  jz      short loc_180002F60
0x180002f28  call    cs:__imp_GetLastError
0x180002f2e  xor     r9d, r9d; msWindowLength
0x180002f31  xor     r8d, r8d; msPeriod
0x180002f34  xor     edx, edx; pftDueTime
0x180002f36  mov     rcx, rsi; pti
0x180002f39  mov     ebx, eax
0x180002f3b  call    cs:__imp_SetThreadpoolTimer
0x180002f41  mov     edx, 1; fCancelPendingCallbacks
0x180002f46  mov     rcx, rsi; pti
0x180002f49  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002f4f  mov     rcx, rsi; pti
0x180002f52  call    cs:__imp_CloseThreadpoolTimer
0x180002f58  mov     ecx, ebx; dwErrCode
0x180002f5a  call    cs:__imp_SetLastError
0x180002f60  mov     ecx, ebp; dwErrCode
0x180002f62  mov     [rdi+10h], r14
0x180002f66  call    cs:__imp_SetLastError
0x180002f6c  mov     rcx, [rdi+10h]; pti
0x180002f70  test    rcx, rcx
0x180002f73  jz      short loc_180002F9C
0x180002f75  mov     rax, 0FFFFFFFF4D2FA200h
0x180002f7f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180002f84  mov     r9d, 124F8h; msWindowLength
0x180002f8a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180002f8f  xor     r8d, r8d; msPeriod
0x180002f92  call    cs:__imp_SetThreadpoolTimer
0x180002f98  mov     byte ptr [rdi+18h], 1
0x180002f9c  mov     rcx, [rsp+48h+var_20]
0x180002fa1  xor     rcx, rsp; StackCookie
0x180002fa4  call    __security_check_cookie
0x180002fa9  mov     rbx, [rsp+48h+arg_8]
0x180002fae  mov     rbp, [rsp+48h+arg_10]
0x180002fb3  add     rsp, 30h
0x180002fb7  pop     r14
0x180002fb9  pop     rdi
0x180002fba  pop     rsi
0x180002fbb  retn
```
