# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1400109bc`
- end: `0x140010a90`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014f64`

## callees

- `0x1400109bc`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1400109f7`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400109f7`
- `KERNEL32!SetThreadpoolTimer` at `0x140010a1c`
- `KERNEL32!SetThreadpoolTimer` at `0x140010a73`
- `KERNEL32!SetThreadpoolTimer` at `0x140010a1c`
- `KERNEL32!SetThreadpoolTimer` at `0x140010a73`
- `KERNEL32!CloseThreadpoolTimer` at `0x140010a33`
- `KERNEL32!CloseThreadpoolTimer` at `0x140010a33`
- `KERNEL32!GetLastError` at `0x1400109e2`
- `KERNEL32!GetLastError` at `0x140010a09`
- `KERNEL32!GetLastError` at `0x1400109e2`
- `KERNEL32!GetLastError` at `0x140010a09`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140010a2a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140010a2a`
- `KERNEL32!SetLastError` at `0x140010a3b`
- `KERNEL32!SetLastError` at `0x140010a47`
- `KERNEL32!SetLastError` at `0x140010a3b`
- `KERNEL32!SetLastError` at `0x140010a47`

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
0x1400109bc  mov     [rsp+arg_8], rbx
0x1400109c1  mov     [rsp+arg_10], rbp
0x1400109c6  push    rsi
0x1400109c7  push    rdi
0x1400109c8  push    r14
0x1400109ca  sub     rsp, 20h
0x1400109ce  cmp     byte ptr [rcx+41h], 0
0x1400109d2  mov     rdi, rcx
0x1400109d5  jnz     loc_140010A7D
0x1400109db  cmp     qword ptr [rcx+30h], 0
0x1400109e0  jnz     short loc_140010A4D
0x1400109e2  call    cs:__imp_GetLastError
0x1400109e8  xor     r8d, r8d; pcbe
0x1400109eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400109f2  mov     rdx, rdi; pv
0x1400109f5  mov     ebp, eax
0x1400109f7  call    cs:__imp_CreateThreadpoolTimer
0x1400109fd  mov     rsi, [rdi+30h]
0x140010a01  mov     r14, rax
0x140010a04  test    rsi, rsi
0x140010a07  jz      short loc_140010A41
0x140010a09  call    cs:__imp_GetLastError
0x140010a0f  xor     r9d, r9d; msWindowLength
0x140010a12  xor     r8d, r8d; msPeriod
0x140010a15  xor     edx, edx; pftDueTime
0x140010a17  mov     rcx, rsi; pti
0x140010a1a  mov     ebx, eax
0x140010a1c  call    cs:__imp_SetThreadpoolTimer
0x140010a22  mov     edx, 1; fCancelPendingCallbacks
0x140010a27  mov     rcx, rsi; pti
0x140010a2a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010a30  mov     rcx, rsi; pti
0x140010a33  call    cs:__imp_CloseThreadpoolTimer
0x140010a39  mov     ecx, ebx; dwErrCode
0x140010a3b  call    cs:__imp_SetLastError
0x140010a41  mov     ecx, ebp; dwErrCode
0x140010a43  mov     [rdi+30h], r14
0x140010a47  call    cs:__imp_SetLastError
0x140010a4d  mov     rcx, [rdi+30h]; pti
0x140010a51  test    rcx, rcx
0x140010a54  jz      short loc_140010A7D
0x140010a56  mov     rax, 0FFFFFFFF4D2FA200h
0x140010a60  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140010a65  mov     r9d, 124F8h; msWindowLength
0x140010a6b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140010a70  xor     r8d, r8d; msPeriod
0x140010a73  call    cs:__imp_SetThreadpoolTimer
0x140010a79  mov     byte ptr [rdi+41h], 1
0x140010a7d  mov     rbx, [rsp+38h+arg_8]
0x140010a82  mov     rbp, [rsp+38h+arg_10]
0x140010a87  add     rsp, 20h
0x140010a8b  pop     r14
0x140010a8d  pop     rdi
0x140010a8e  pop     rsi
0x140010a8f  retn
```
