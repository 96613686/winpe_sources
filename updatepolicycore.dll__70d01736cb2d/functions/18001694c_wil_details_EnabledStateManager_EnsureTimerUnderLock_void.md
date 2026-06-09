# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001694c`
- end: `0x180016a3c`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016a98`

## callees

- `0x18001694c`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800169d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800169d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800169c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800169c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016996`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016996`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800169bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016a12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800169bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016a12`

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
0x18001694c  mov     [rsp+arg_8], rbx
0x180016951  mov     [rsp+arg_10], rbp
0x180016956  push    rsi
0x180016957  push    rdi
0x180016958  push    r14
0x18001695a  sub     rsp, 30h
0x18001695e  mov     rax, cs:__security_cookie
0x180016965  xor     rax, rsp
0x180016968  mov     [rsp+48h+var_20], rax
0x18001696d  cmp     byte ptr [rcx+18h], 0
0x180016971  mov     rdi, rcx
0x180016974  jnz     loc_180016A1C
0x18001697a  cmp     qword ptr [rcx+10h], 0
0x18001697f  jnz     short loc_1800169EC
0x180016981  call    cs:__imp_GetLastError
0x180016987  xor     r8d, r8d; pcbe
0x18001698a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016991  mov     rdx, rdi; pv
0x180016994  mov     ebp, eax
0x180016996  call    cs:__imp_CreateThreadpoolTimer
0x18001699c  mov     rsi, [rdi+10h]
0x1800169a0  mov     r14, rax
0x1800169a3  test    rsi, rsi
0x1800169a6  jz      short loc_1800169E0
0x1800169a8  call    cs:__imp_GetLastError
0x1800169ae  xor     r9d, r9d; msWindowLength
0x1800169b1  xor     r8d, r8d; msPeriod
0x1800169b4  xor     edx, edx; pftDueTime
0x1800169b6  mov     rcx, rsi; pti
0x1800169b9  mov     ebx, eax
0x1800169bb  call    cs:__imp_SetThreadpoolTimer
0x1800169c1  mov     edx, 1; fCancelPendingCallbacks
0x1800169c6  mov     rcx, rsi; pti
0x1800169c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800169cf  mov     rcx, rsi; pti
0x1800169d2  call    cs:__imp_CloseThreadpoolTimer
0x1800169d8  mov     ecx, ebx; dwErrCode
0x1800169da  call    cs:__imp_SetLastError
0x1800169e0  mov     ecx, ebp; dwErrCode
0x1800169e2  mov     [rdi+10h], r14
0x1800169e6  call    cs:__imp_SetLastError
0x1800169ec  mov     rcx, [rdi+10h]; pti
0x1800169f0  test    rcx, rcx
0x1800169f3  jz      short loc_180016A1C
0x1800169f5  mov     rax, 0FFFFFFFF4D2FA200h
0x1800169ff  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180016a04  mov     r9d, 124F8h; msWindowLength
0x180016a0a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180016a0f  xor     r8d, r8d; msPeriod
0x180016a12  call    cs:__imp_SetThreadpoolTimer
0x180016a18  mov     byte ptr [rdi+18h], 1
0x180016a1c  mov     rcx, [rsp+48h+var_20]
0x180016a21  xor     rcx, rsp; StackCookie
0x180016a24  call    __security_check_cookie
0x180016a29  mov     rbx, [rsp+48h+arg_8]
0x180016a2e  mov     rbp, [rsp+48h+arg_10]
0x180016a33  add     rsp, 30h
0x180016a37  pop     r14
0x180016a39  pop     rdi
0x180016a3a  pop     rsi
0x180016a3b  retn
```
