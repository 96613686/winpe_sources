# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001005c`
- end: `0x18001014c`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800103d8`

## callees

- `0x18001005c`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100b8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800100e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800100e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800100cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010122`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800100cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010122`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800100d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800100d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800100a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800100a6`

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
0x18001005c  mov     [rsp+arg_8], rbx
0x180010061  mov     [rsp+arg_10], rbp
0x180010066  push    rsi
0x180010067  push    rdi
0x180010068  push    r14
0x18001006a  sub     rsp, 30h
0x18001006e  mov     rax, cs:__security_cookie
0x180010075  xor     rax, rsp
0x180010078  mov     [rsp+48h+var_20], rax
0x18001007d  cmp     byte ptr [rcx+18h], 0
0x180010081  mov     rdi, rcx
0x180010084  jnz     loc_18001012C
0x18001008a  cmp     qword ptr [rcx+10h], 0
0x18001008f  jnz     short loc_1800100FC
0x180010091  call    cs:__imp_GetLastError
0x180010097  xor     r8d, r8d; pcbe
0x18001009a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800100a1  mov     rdx, rdi; pv
0x1800100a4  mov     ebp, eax
0x1800100a6  call    cs:__imp_CreateThreadpoolTimer
0x1800100ac  mov     rsi, [rdi+10h]
0x1800100b0  mov     r14, rax
0x1800100b3  test    rsi, rsi
0x1800100b6  jz      short loc_1800100F0
0x1800100b8  call    cs:__imp_GetLastError
0x1800100be  xor     r9d, r9d; msWindowLength
0x1800100c1  xor     r8d, r8d; msPeriod
0x1800100c4  xor     edx, edx; pftDueTime
0x1800100c6  mov     rcx, rsi; pti
0x1800100c9  mov     ebx, eax
0x1800100cb  call    cs:__imp_SetThreadpoolTimer
0x1800100d1  mov     edx, 1; fCancelPendingCallbacks
0x1800100d6  mov     rcx, rsi; pti
0x1800100d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800100df  mov     rcx, rsi; pti
0x1800100e2  call    cs:__imp_CloseThreadpoolTimer
0x1800100e8  mov     ecx, ebx; dwErrCode
0x1800100ea  call    cs:__imp_SetLastError
0x1800100f0  mov     ecx, ebp; dwErrCode
0x1800100f2  mov     [rdi+10h], r14
0x1800100f6  call    cs:__imp_SetLastError
0x1800100fc  mov     rcx, [rdi+10h]; pti
0x180010100  test    rcx, rcx
0x180010103  jz      short loc_18001012C
0x180010105  mov     rax, 0FFFFFFFF4D2FA200h
0x18001010f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180010114  mov     r9d, 124F8h; msWindowLength
0x18001011a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001011f  xor     r8d, r8d; msPeriod
0x180010122  call    cs:__imp_SetThreadpoolTimer
0x180010128  mov     byte ptr [rdi+18h], 1
0x18001012c  mov     rcx, [rsp+48h+var_20]
0x180010131  xor     rcx, rsp; StackCookie
0x180010134  call    __security_check_cookie
0x180010139  mov     rbx, [rsp+48h+arg_8]
0x18001013e  mov     rbp, [rsp+48h+arg_10]
0x180010143  add     rsp, 30h
0x180010147  pop     r14
0x180010149  pop     rdi
0x18001014a  pop     rsi
0x18001014b  retn
```
