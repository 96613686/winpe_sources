# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800126cc`
- end: `0x1800127bc`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012818`

## callees

- `0x1800126cc`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001275a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012766`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001275a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012728`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012716`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012716`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012752`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012752`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001273b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012792`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001273b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012792`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012749`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012749`

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
0x1800126cc  mov     [rsp+arg_8], rbx
0x1800126d1  mov     [rsp+arg_10], rbp
0x1800126d6  push    rsi
0x1800126d7  push    rdi
0x1800126d8  push    r14
0x1800126da  sub     rsp, 30h
0x1800126de  mov     rax, cs:__security_cookie
0x1800126e5  xor     rax, rsp
0x1800126e8  mov     [rsp+48h+var_20], rax
0x1800126ed  cmp     byte ptr [rcx+18h], 0
0x1800126f1  mov     rdi, rcx
0x1800126f4  jnz     loc_18001279C
0x1800126fa  cmp     qword ptr [rcx+10h], 0
0x1800126ff  jnz     short loc_18001276C
0x180012701  call    cs:__imp_GetLastError
0x180012707  xor     r8d, r8d; pcbe
0x18001270a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012711  mov     rdx, rdi; pv
0x180012714  mov     ebp, eax
0x180012716  call    cs:__imp_CreateThreadpoolTimer
0x18001271c  mov     rsi, [rdi+10h]
0x180012720  mov     r14, rax
0x180012723  test    rsi, rsi
0x180012726  jz      short loc_180012760
0x180012728  call    cs:__imp_GetLastError
0x18001272e  xor     r9d, r9d; msWindowLength
0x180012731  xor     r8d, r8d; msPeriod
0x180012734  xor     edx, edx; pftDueTime
0x180012736  mov     rcx, rsi; pti
0x180012739  mov     ebx, eax
0x18001273b  call    cs:__imp_SetThreadpoolTimer
0x180012741  mov     edx, 1; fCancelPendingCallbacks
0x180012746  mov     rcx, rsi; pti
0x180012749  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001274f  mov     rcx, rsi; pti
0x180012752  call    cs:__imp_CloseThreadpoolTimer
0x180012758  mov     ecx, ebx; dwErrCode
0x18001275a  call    cs:__imp_SetLastError
0x180012760  mov     ecx, ebp; dwErrCode
0x180012762  mov     [rdi+10h], r14
0x180012766  call    cs:__imp_SetLastError
0x18001276c  mov     rcx, [rdi+10h]; pti
0x180012770  test    rcx, rcx
0x180012773  jz      short loc_18001279C
0x180012775  mov     rax, 0FFFFFFFF4D2FA200h
0x18001277f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180012784  mov     r9d, 124F8h; msWindowLength
0x18001278a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001278f  xor     r8d, r8d; msPeriod
0x180012792  call    cs:__imp_SetThreadpoolTimer
0x180012798  mov     byte ptr [rdi+18h], 1
0x18001279c  mov     rcx, [rsp+48h+var_20]
0x1800127a1  xor     rcx, rsp; StackCookie
0x1800127a4  call    __security_check_cookie
0x1800127a9  mov     rbx, [rsp+48h+arg_8]
0x1800127ae  mov     rbp, [rsp+48h+arg_10]
0x1800127b3  add     rsp, 30h
0x1800127b7  pop     r14
0x1800127b9  pop     rdi
0x1800127ba  pop     rsi
0x1800127bb  retn
```
