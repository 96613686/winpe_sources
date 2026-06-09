# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140009e94`
- end: `0x140009f84`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bb94`

## callees

- `0x140005360`
- `0x140009e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ef0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009f03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009f5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009f03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009f5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009f1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009f1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009ede`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009ede`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009f11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009f11`

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
0x140009e94  mov     [rsp+arg_8], rbx
0x140009e99  mov     [rsp+arg_10], rbp
0x140009e9e  push    rsi
0x140009e9f  push    rdi
0x140009ea0  push    r14
0x140009ea2  sub     rsp, 30h
0x140009ea6  mov     rax, cs:__security_cookie
0x140009ead  xor     rax, rsp
0x140009eb0  mov     [rsp+48h+var_20], rax
0x140009eb5  cmp     byte ptr [rcx+41h], 0
0x140009eb9  mov     rdi, rcx
0x140009ebc  jnz     loc_140009F64
0x140009ec2  cmp     qword ptr [rcx+30h], 0
0x140009ec7  jnz     short loc_140009F34
0x140009ec9  call    cs:__imp_GetLastError
0x140009ecf  xor     r8d, r8d; pcbe
0x140009ed2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009ed9  mov     rdx, rdi; pv
0x140009edc  mov     ebp, eax
0x140009ede  call    cs:__imp_CreateThreadpoolTimer
0x140009ee4  mov     rsi, [rdi+30h]
0x140009ee8  mov     r14, rax
0x140009eeb  test    rsi, rsi
0x140009eee  jz      short loc_140009F28
0x140009ef0  call    cs:__imp_GetLastError
0x140009ef6  xor     r9d, r9d; msWindowLength
0x140009ef9  xor     r8d, r8d; msPeriod
0x140009efc  xor     edx, edx; pftDueTime
0x140009efe  mov     rcx, rsi; pti
0x140009f01  mov     ebx, eax
0x140009f03  call    cs:__imp_SetThreadpoolTimer
0x140009f09  mov     edx, 1; fCancelPendingCallbacks
0x140009f0e  mov     rcx, rsi; pti
0x140009f11  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009f17  mov     rcx, rsi; pti
0x140009f1a  call    cs:__imp_CloseThreadpoolTimer
0x140009f20  mov     ecx, ebx; dwErrCode
0x140009f22  call    cs:__imp_SetLastError
0x140009f28  mov     ecx, ebp; dwErrCode
0x140009f2a  mov     [rdi+30h], r14
0x140009f2e  call    cs:__imp_SetLastError
0x140009f34  mov     rcx, [rdi+30h]; pti
0x140009f38  test    rcx, rcx
0x140009f3b  jz      short loc_140009F64
0x140009f3d  mov     rax, 0FFFFFFFF4D2FA200h
0x140009f47  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140009f4c  mov     r9d, 124F8h; msWindowLength
0x140009f52  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x140009f57  xor     r8d, r8d; msPeriod
0x140009f5a  call    cs:__imp_SetThreadpoolTimer
0x140009f60  mov     byte ptr [rdi+41h], 1
0x140009f64  mov     rcx, [rsp+48h+var_20]
0x140009f69  xor     rcx, rsp; StackCookie
0x140009f6c  call    __security_check_cookie
0x140009f71  mov     rbx, [rsp+48h+arg_8]
0x140009f76  mov     rbp, [rsp+48h+arg_10]
0x140009f7b  add     rsp, 30h
0x140009f7f  pop     r14
0x140009f81  pop     rdi
0x140009f82  pop     rsi
0x140009f83  retn
```
