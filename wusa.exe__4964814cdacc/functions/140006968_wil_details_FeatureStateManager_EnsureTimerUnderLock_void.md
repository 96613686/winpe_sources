# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140006968`
- end: `0x140006a3c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000954c`

## callees

- `0x140006968`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1400069c8`
- `KERNEL32!SetThreadpoolTimer` at `0x140006a1f`
- `KERNEL32!SetThreadpoolTimer` at `0x1400069c8`
- `KERNEL32!SetThreadpoolTimer` at `0x140006a1f`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400069a3`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400069a3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400069d6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400069d6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400069df`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400069df`
- `KERNEL32!GetLastError` at `0x14000698e`
- `KERNEL32!GetLastError` at `0x1400069b5`
- `KERNEL32!GetLastError` at `0x14000698e`
- `KERNEL32!GetLastError` at `0x1400069b5`
- `KERNEL32!SetLastError` at `0x1400069e7`
- `KERNEL32!SetLastError` at `0x1400069f3`
- `KERNEL32!SetLastError` at `0x1400069e7`
- `KERNEL32!SetLastError` at `0x1400069f3`

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
0x140006968  mov     [rsp+arg_8], rbx
0x14000696d  mov     [rsp+arg_10], rbp
0x140006972  push    rsi
0x140006973  push    rdi
0x140006974  push    r14
0x140006976  sub     rsp, 20h
0x14000697a  cmp     byte ptr [rcx+41h], 0
0x14000697e  mov     rdi, rcx
0x140006981  jnz     loc_140006A29
0x140006987  cmp     qword ptr [rcx+30h], 0
0x14000698c  jnz     short loc_1400069F9
0x14000698e  call    cs:__imp_GetLastError
0x140006994  xor     r8d, r8d; pcbe
0x140006997  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000699e  mov     rdx, rdi; pv
0x1400069a1  mov     ebp, eax
0x1400069a3  call    cs:__imp_CreateThreadpoolTimer
0x1400069a9  mov     rsi, [rdi+30h]
0x1400069ad  mov     r14, rax
0x1400069b0  test    rsi, rsi
0x1400069b3  jz      short loc_1400069ED
0x1400069b5  call    cs:__imp_GetLastError
0x1400069bb  xor     r9d, r9d; msWindowLength
0x1400069be  xor     r8d, r8d; msPeriod
0x1400069c1  xor     edx, edx; pftDueTime
0x1400069c3  mov     rcx, rsi; pti
0x1400069c6  mov     ebx, eax
0x1400069c8  call    cs:__imp_SetThreadpoolTimer
0x1400069ce  mov     edx, 1; fCancelPendingCallbacks
0x1400069d3  mov     rcx, rsi; pti
0x1400069d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400069dc  mov     rcx, rsi; pti
0x1400069df  call    cs:__imp_CloseThreadpoolTimer
0x1400069e5  mov     ecx, ebx; dwErrCode
0x1400069e7  call    cs:__imp_SetLastError
0x1400069ed  mov     ecx, ebp; dwErrCode
0x1400069ef  mov     [rdi+30h], r14
0x1400069f3  call    cs:__imp_SetLastError
0x1400069f9  mov     rcx, [rdi+30h]; pti
0x1400069fd  test    rcx, rcx
0x140006a00  jz      short loc_140006A29
0x140006a02  mov     rax, 0FFFFFFFF4D2FA200h
0x140006a0c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140006a11  mov     r9d, 124F8h; msWindowLength
0x140006a17  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140006a1c  xor     r8d, r8d; msPeriod
0x140006a1f  call    cs:__imp_SetThreadpoolTimer
0x140006a25  mov     byte ptr [rdi+41h], 1
0x140006a29  mov     rbx, [rsp+38h+arg_8]
0x140006a2e  mov     rbp, [rsp+38h+arg_10]
0x140006a33  add     rsp, 20h
0x140006a37  pop     r14
0x140006a39  pop     rdi
0x140006a3a  pop     rsi
0x140006a3b  retn
```
