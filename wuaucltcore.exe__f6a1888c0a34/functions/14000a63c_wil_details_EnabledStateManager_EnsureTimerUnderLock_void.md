# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000a63c`
- end: `0x14000a72c`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a788`

## callees

- `0x14000a63c`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a6ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a6d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a6ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a6d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000a686`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000a686`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000a6c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000a6c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a6ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a702`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a6ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a702`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000a6b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000a6b9`

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
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x14000a63c  mov     [rsp+arg_8], rbx
0x14000a641  mov     [rsp+arg_10], rbp
0x14000a646  push    rsi
0x14000a647  push    rdi
0x14000a648  push    r14
0x14000a64a  sub     rsp, 30h
0x14000a64e  mov     rax, cs:__security_cookie
0x14000a655  xor     rax, rsp
0x14000a658  mov     [rsp+48h+var_20], rax
0x14000a65d  cmp     byte ptr [rcx+18h], 0
0x14000a661  mov     rdi, rcx
0x14000a664  jnz     loc_14000A70C
0x14000a66a  cmp     qword ptr [rcx+10h], 0
0x14000a66f  jnz     short loc_14000A6DC
0x14000a671  call    cs:__imp_GetLastError
0x14000a677  xor     r8d, r8d; pcbe
0x14000a67a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000a681  mov     rdx, rdi; pv
0x14000a684  mov     ebp, eax
0x14000a686  call    cs:__imp_CreateThreadpoolTimer
0x14000a68c  mov     rsi, [rdi+10h]
0x14000a690  mov     r14, rax
0x14000a693  test    rsi, rsi
0x14000a696  jz      short loc_14000A6D0
0x14000a698  call    cs:__imp_GetLastError
0x14000a69e  xor     r9d, r9d; msWindowLength
0x14000a6a1  xor     r8d, r8d; msPeriod
0x14000a6a4  xor     edx, edx; pftDueTime
0x14000a6a6  mov     rcx, rsi; pti
0x14000a6a9  mov     ebx, eax
0x14000a6ab  call    cs:__imp_SetThreadpoolTimer
0x14000a6b1  mov     edx, 1; fCancelPendingCallbacks
0x14000a6b6  mov     rcx, rsi; pti
0x14000a6b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a6bf  mov     rcx, rsi; pti
0x14000a6c2  call    cs:__imp_CloseThreadpoolTimer
0x14000a6c8  mov     ecx, ebx; dwErrCode
0x14000a6ca  call    cs:__imp_SetLastError
0x14000a6d0  mov     ecx, ebp; dwErrCode
0x14000a6d2  mov     [rdi+10h], r14
0x14000a6d6  call    cs:__imp_SetLastError
0x14000a6dc  mov     rcx, [rdi+10h]; pti
0x14000a6e0  test    rcx, rcx
0x14000a6e3  jz      short loc_14000A70C
0x14000a6e5  mov     rax, 0FFFFFFFF4D2FA200h
0x14000a6ef  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x14000a6f4  mov     r9d, 124F8h; msWindowLength
0x14000a6fa  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x14000a6ff  xor     r8d, r8d; msPeriod
0x14000a702  call    cs:__imp_SetThreadpoolTimer
0x14000a708  mov     byte ptr [rdi+18h], 1
0x14000a70c  mov     rcx, [rsp+48h+var_20]
0x14000a711  xor     rcx, rsp; StackCookie
0x14000a714  call    __security_check_cookie
0x14000a719  mov     rbx, [rsp+48h+arg_8]
0x14000a71e  mov     rbp, [rsp+48h+arg_10]
0x14000a723  add     rsp, 30h
0x14000a727  pop     r14
0x14000a729  pop     rdi
0x14000a72a  pop     rsi
0x14000a72b  retn
```
