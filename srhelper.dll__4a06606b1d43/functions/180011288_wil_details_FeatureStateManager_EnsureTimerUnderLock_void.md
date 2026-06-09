# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180011288`
- end: `0x18001135c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012ce4`

## callees

- `0x180011288`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800112ae`
- `KERNEL32!GetLastError` at `0x1800112d5`
- `KERNEL32!GetLastError` at `0x1800112ae`
- `KERNEL32!GetLastError` at `0x1800112d5`
- `KERNEL32!SetLastError` at `0x180011307`
- `KERNEL32!SetLastError` at `0x180011313`
- `KERNEL32!SetLastError` at `0x180011307`
- `KERNEL32!SetLastError` at `0x180011313`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800112f6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800112f6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800112ff`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800112ff`
- `KERNEL32!SetThreadpoolTimer` at `0x1800112e8`
- `KERNEL32!SetThreadpoolTimer` at `0x18001133f`
- `KERNEL32!SetThreadpoolTimer` at `0x1800112e8`
- `KERNEL32!SetThreadpoolTimer` at `0x18001133f`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800112c3`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800112c3`

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
0x180011288  mov     [rsp+arg_8], rbx
0x18001128d  mov     [rsp+arg_10], rbp
0x180011292  push    rsi
0x180011293  push    rdi
0x180011294  push    r14
0x180011296  sub     rsp, 20h
0x18001129a  cmp     byte ptr [rcx+41h], 0
0x18001129e  mov     rdi, rcx
0x1800112a1  jnz     loc_180011349
0x1800112a7  cmp     qword ptr [rcx+30h], 0
0x1800112ac  jnz     short loc_180011319
0x1800112ae  call    cs:__imp_GetLastError
0x1800112b4  xor     r8d, r8d; pcbe
0x1800112b7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800112be  mov     rdx, rdi; pv
0x1800112c1  mov     ebp, eax
0x1800112c3  call    cs:__imp_CreateThreadpoolTimer
0x1800112c9  mov     rsi, [rdi+30h]
0x1800112cd  mov     r14, rax
0x1800112d0  test    rsi, rsi
0x1800112d3  jz      short loc_18001130D
0x1800112d5  call    cs:__imp_GetLastError
0x1800112db  xor     r9d, r9d; msWindowLength
0x1800112de  xor     r8d, r8d; msPeriod
0x1800112e1  xor     edx, edx; pftDueTime
0x1800112e3  mov     rcx, rsi; pti
0x1800112e6  mov     ebx, eax
0x1800112e8  call    cs:__imp_SetThreadpoolTimer
0x1800112ee  mov     edx, 1; fCancelPendingCallbacks
0x1800112f3  mov     rcx, rsi; pti
0x1800112f6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800112fc  mov     rcx, rsi; pti
0x1800112ff  call    cs:__imp_CloseThreadpoolTimer
0x180011305  mov     ecx, ebx; dwErrCode
0x180011307  call    cs:__imp_SetLastError
0x18001130d  mov     ecx, ebp; dwErrCode
0x18001130f  mov     [rdi+30h], r14
0x180011313  call    cs:__imp_SetLastError
0x180011319  mov     rcx, [rdi+30h]; pti
0x18001131d  test    rcx, rcx
0x180011320  jz      short loc_180011349
0x180011322  mov     rax, 0FFFFFFFF4D2FA200h
0x18001132c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180011331  mov     r9d, 124F8h; msWindowLength
0x180011337  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001133c  xor     r8d, r8d; msPeriod
0x18001133f  call    cs:__imp_SetThreadpoolTimer
0x180011345  mov     byte ptr [rdi+41h], 1
0x180011349  mov     rbx, [rsp+38h+arg_8]
0x18001134e  mov     rbp, [rsp+38h+arg_10]
0x180011353  add     rsp, 20h
0x180011357  pop     r14
0x180011359  pop     rdi
0x18001135a  pop     rsi
0x18001135b  retn
```
