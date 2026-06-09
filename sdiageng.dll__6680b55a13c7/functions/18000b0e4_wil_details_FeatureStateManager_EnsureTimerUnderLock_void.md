# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000b0e4`
- end: `0x18000b1b8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb14`

## callees

- `0x18000b0e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b10a`
- `KERNEL32!GetLastError` at `0x18000b131`
- `KERNEL32!GetLastError` at `0x18000b10a`
- `KERNEL32!GetLastError` at `0x18000b131`
- `KERNEL32!SetLastError` at `0x18000b163`
- `KERNEL32!SetLastError` at `0x18000b16f`
- `KERNEL32!SetLastError` at `0x18000b163`
- `KERNEL32!SetLastError` at `0x18000b16f`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b144`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b19b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b144`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b19b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000b152`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000b152`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000b15b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000b15b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b11f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b11f`

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
0x18000b0e4  mov     [rsp+arg_8], rbx
0x18000b0e9  mov     [rsp+arg_10], rbp
0x18000b0ee  push    rsi
0x18000b0ef  push    rdi
0x18000b0f0  push    r14
0x18000b0f2  sub     rsp, 20h
0x18000b0f6  cmp     byte ptr [rcx+41h], 0
0x18000b0fa  mov     rdi, rcx
0x18000b0fd  jnz     loc_18000B1A5
0x18000b103  cmp     qword ptr [rcx+30h], 0
0x18000b108  jnz     short loc_18000B175
0x18000b10a  call    cs:__imp_GetLastError
0x18000b110  xor     r8d, r8d; pcbe
0x18000b113  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b11a  mov     rdx, rdi; pv
0x18000b11d  mov     ebp, eax
0x18000b11f  call    cs:__imp_CreateThreadpoolTimer
0x18000b125  mov     rsi, [rdi+30h]
0x18000b129  mov     r14, rax
0x18000b12c  test    rsi, rsi
0x18000b12f  jz      short loc_18000B169
0x18000b131  call    cs:__imp_GetLastError
0x18000b137  xor     r9d, r9d; msWindowLength
0x18000b13a  xor     r8d, r8d; msPeriod
0x18000b13d  xor     edx, edx; pftDueTime
0x18000b13f  mov     rcx, rsi; pti
0x18000b142  mov     ebx, eax
0x18000b144  call    cs:__imp_SetThreadpoolTimer
0x18000b14a  mov     edx, 1; fCancelPendingCallbacks
0x18000b14f  mov     rcx, rsi; pti
0x18000b152  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b158  mov     rcx, rsi; pti
0x18000b15b  call    cs:__imp_CloseThreadpoolTimer
0x18000b161  mov     ecx, ebx; dwErrCode
0x18000b163  call    cs:__imp_SetLastError
0x18000b169  mov     ecx, ebp; dwErrCode
0x18000b16b  mov     [rdi+30h], r14
0x18000b16f  call    cs:__imp_SetLastError
0x18000b175  mov     rcx, [rdi+30h]; pti
0x18000b179  test    rcx, rcx
0x18000b17c  jz      short loc_18000B1A5
0x18000b17e  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b188  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000b18d  mov     r9d, 124F8h; msWindowLength
0x18000b193  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000b198  xor     r8d, r8d; msPeriod
0x18000b19b  call    cs:__imp_SetThreadpoolTimer
0x18000b1a1  mov     byte ptr [rdi+41h], 1
0x18000b1a5  mov     rbx, [rsp+38h+arg_8]
0x18000b1aa  mov     rbp, [rsp+38h+arg_10]
0x18000b1af  add     rsp, 20h
0x18000b1b3  pop     r14
0x18000b1b5  pop     rdi
0x18000b1b6  pop     rsi
0x18000b1b7  retn
```
