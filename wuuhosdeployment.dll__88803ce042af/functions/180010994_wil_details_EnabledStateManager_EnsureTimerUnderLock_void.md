# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x180010994`
- end: `0x180010a84`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010c18`

## callees

- `0x180010994`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010a11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010a11`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010a1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010a1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800109de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800109de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010a03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010a5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010a03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010a5a`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 24) )
  {
    if ( !pv[2] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, pv, 0);
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
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x180010994  mov     [rsp+arg_8], rbx
0x180010999  mov     [rsp+arg_10], rbp
0x18001099e  push    rsi
0x18001099f  push    rdi
0x1800109a0  push    r14
0x1800109a2  sub     rsp, 30h
0x1800109a6  mov     rax, cs:__security_cookie
0x1800109ad  xor     rax, rsp
0x1800109b0  mov     [rsp+48h+var_20], rax
0x1800109b5  cmp     byte ptr [rcx+18h], 0
0x1800109b9  mov     rdi, rcx
0x1800109bc  jnz     loc_180010A64
0x1800109c2  cmp     qword ptr [rcx+10h], 0
0x1800109c7  jnz     short loc_180010A34
0x1800109c9  call    cs:__imp_GetLastError
0x1800109cf  xor     r8d, r8d; pcbe
0x1800109d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800109d9  mov     rdx, rdi; pv
0x1800109dc  mov     ebp, eax
0x1800109de  call    cs:__imp_CreateThreadpoolTimer
0x1800109e4  mov     rsi, [rdi+10h]
0x1800109e8  mov     r14, rax
0x1800109eb  test    rsi, rsi
0x1800109ee  jz      short loc_180010A28
0x1800109f0  call    cs:__imp_GetLastError
0x1800109f6  xor     r9d, r9d; msWindowLength
0x1800109f9  xor     r8d, r8d; msPeriod
0x1800109fc  xor     edx, edx; pftDueTime
0x1800109fe  mov     rcx, rsi; pti
0x180010a01  mov     ebx, eax
0x180010a03  call    cs:__imp_SetThreadpoolTimer
0x180010a09  mov     edx, 1; fCancelPendingCallbacks
0x180010a0e  mov     rcx, rsi; pti
0x180010a11  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010a17  mov     rcx, rsi; pti
0x180010a1a  call    cs:__imp_CloseThreadpoolTimer
0x180010a20  mov     ecx, ebx; dwErrCode
0x180010a22  call    cs:__imp_SetLastError
0x180010a28  mov     ecx, ebp; dwErrCode
0x180010a2a  mov     [rdi+10h], r14
0x180010a2e  call    cs:__imp_SetLastError
0x180010a34  mov     rcx, [rdi+10h]; pti
0x180010a38  test    rcx, rcx
0x180010a3b  jz      short loc_180010A64
0x180010a3d  mov     rax, 0FFFFFFFF4D2FA200h
0x180010a47  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180010a4c  mov     r9d, 124F8h; msWindowLength
0x180010a52  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180010a57  xor     r8d, r8d; msPeriod
0x180010a5a  call    cs:__imp_SetThreadpoolTimer
0x180010a60  mov     byte ptr [rdi+18h], 1
0x180010a64  mov     rcx, [rsp+48h+var_20]
0x180010a69  xor     rcx, rsp; StackCookie
0x180010a6c  call    __security_check_cookie
0x180010a71  mov     rbx, [rsp+48h+arg_8]
0x180010a76  mov     rbp, [rsp+48h+arg_10]
0x180010a7b  add     rsp, 30h
0x180010a7f  pop     r14
0x180010a81  pop     rdi
0x180010a82  pop     rsi
0x180010a83  retn
```
