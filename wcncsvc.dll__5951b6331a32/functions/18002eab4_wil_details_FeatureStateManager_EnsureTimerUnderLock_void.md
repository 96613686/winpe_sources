# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18002eab4`
- end: `0x18002eb88`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800316e4`

## callees

- `0x18002eab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002eaef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002eaef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002eb2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002eb2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002eb22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002eb22`

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
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

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
0x18002eab4  mov     [rsp+arg_8], rbx
0x18002eab9  mov     [rsp+arg_10], rbp
0x18002eabe  push    rsi
0x18002eabf  push    rdi
0x18002eac0  push    r14
0x18002eac2  sub     rsp, 20h
0x18002eac6  cmp     byte ptr [rcx+41h], 0
0x18002eaca  mov     rdi, rcx
0x18002eacd  jnz     loc_18002EB75
0x18002ead3  cmp     qword ptr [rcx+30h], 0
0x18002ead8  jnz     short loc_18002EB45
0x18002eada  call    cs:__imp_GetLastError
0x18002eae0  xor     r8d, r8d; pcbe
0x18002eae3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002eaea  mov     rdx, rdi; pv
0x18002eaed  mov     ebp, eax
0x18002eaef  call    cs:__imp_CreateThreadpoolTimer
0x18002eaf5  mov     rsi, [rdi+30h]
0x18002eaf9  mov     r14, rax
0x18002eafc  test    rsi, rsi
0x18002eaff  jz      short loc_18002EB39
0x18002eb01  call    cs:__imp_GetLastError
0x18002eb07  xor     r9d, r9d; msWindowLength
0x18002eb0a  xor     r8d, r8d; msPeriod
0x18002eb0d  xor     edx, edx; pftDueTime
0x18002eb0f  mov     rcx, rsi; pti
0x18002eb12  mov     ebx, eax
0x18002eb14  call    cs:__imp_SetThreadpoolTimer
0x18002eb1a  mov     edx, 1; fCancelPendingCallbacks
0x18002eb1f  mov     rcx, rsi; pti
0x18002eb22  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002eb28  mov     rcx, rsi; pti
0x18002eb2b  call    cs:__imp_CloseThreadpoolTimer
0x18002eb31  mov     ecx, ebx; dwErrCode
0x18002eb33  call    cs:__imp_SetLastError
0x18002eb39  mov     ecx, ebp; dwErrCode
0x18002eb3b  mov     [rdi+30h], r14
0x18002eb3f  call    cs:__imp_SetLastError
0x18002eb45  mov     rcx, [rdi+30h]; pti
0x18002eb49  test    rcx, rcx
0x18002eb4c  jz      short loc_18002EB75
0x18002eb4e  mov     rax, 0FFFFFFFF4D2FA200h
0x18002eb58  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18002eb5d  mov     r9d, 124F8h; msWindowLength
0x18002eb63  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18002eb68  xor     r8d, r8d; msPeriod
0x18002eb6b  call    cs:__imp_SetThreadpoolTimer
0x18002eb71  mov     byte ptr [rdi+41h], 1
0x18002eb75  mov     rbx, [rsp+38h+arg_8]
0x18002eb7a  mov     rbp, [rsp+38h+arg_10]
0x18002eb7f  add     rsp, 20h
0x18002eb83  pop     r14
0x18002eb85  pop     rdi
0x18002eb86  pop     rsi
0x18002eb87  retn
```
