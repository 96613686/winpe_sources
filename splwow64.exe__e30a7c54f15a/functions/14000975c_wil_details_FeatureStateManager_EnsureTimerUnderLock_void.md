# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000975c`
- end: `0x140009830`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a880`

## callees

- `0x14000975c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400097db`
- `KERNEL32!SetLastError` at `0x1400097e7`
- `KERNEL32!SetLastError` at `0x1400097db`
- `KERNEL32!SetLastError` at `0x1400097e7`
- `KERNEL32!GetLastError` at `0x140009782`
- `KERNEL32!GetLastError` at `0x1400097a9`
- `KERNEL32!GetLastError` at `0x140009782`
- `KERNEL32!GetLastError` at `0x1400097a9`
- `KERNEL32!SetThreadpoolTimer` at `0x1400097bc`
- `KERNEL32!SetThreadpoolTimer` at `0x140009813`
- `KERNEL32!SetThreadpoolTimer` at `0x1400097bc`
- `KERNEL32!SetThreadpoolTimer` at `0x140009813`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400097d3`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400097d3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400097ca`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400097ca`
- `KERNEL32!CreateThreadpoolTimer` at `0x140009797`
- `KERNEL32!CreateThreadpoolTimer` at `0x140009797`

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
0x14000975c  mov     [rsp+arg_8], rbx
0x140009761  mov     [rsp+arg_10], rbp
0x140009766  push    rsi
0x140009767  push    rdi
0x140009768  push    r14
0x14000976a  sub     rsp, 20h
0x14000976e  cmp     byte ptr [rcx+41h], 0
0x140009772  mov     rdi, rcx
0x140009775  jnz     loc_14000981D
0x14000977b  cmp     qword ptr [rcx+30h], 0
0x140009780  jnz     short loc_1400097ED
0x140009782  call    cs:__imp_GetLastError
0x140009788  xor     r8d, r8d; pcbe
0x14000978b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009792  mov     rdx, rdi; pv
0x140009795  mov     ebp, eax
0x140009797  call    cs:__imp_CreateThreadpoolTimer
0x14000979d  mov     rsi, [rdi+30h]
0x1400097a1  mov     r14, rax
0x1400097a4  test    rsi, rsi
0x1400097a7  jz      short loc_1400097E1
0x1400097a9  call    cs:__imp_GetLastError
0x1400097af  xor     r9d, r9d; msWindowLength
0x1400097b2  xor     r8d, r8d; msPeriod
0x1400097b5  xor     edx, edx; pftDueTime
0x1400097b7  mov     rcx, rsi; pti
0x1400097ba  mov     ebx, eax
0x1400097bc  call    cs:__imp_SetThreadpoolTimer
0x1400097c2  mov     edx, 1; fCancelPendingCallbacks
0x1400097c7  mov     rcx, rsi; pti
0x1400097ca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400097d0  mov     rcx, rsi; pti
0x1400097d3  call    cs:__imp_CloseThreadpoolTimer
0x1400097d9  mov     ecx, ebx; dwErrCode
0x1400097db  call    cs:__imp_SetLastError
0x1400097e1  mov     ecx, ebp; dwErrCode
0x1400097e3  mov     [rdi+30h], r14
0x1400097e7  call    cs:__imp_SetLastError
0x1400097ed  mov     rcx, [rdi+30h]; pti
0x1400097f1  test    rcx, rcx
0x1400097f4  jz      short loc_14000981D
0x1400097f6  mov     rax, 0FFFFFFFF4D2FA200h
0x140009800  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140009805  mov     r9d, 124F8h; msWindowLength
0x14000980b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140009810  xor     r8d, r8d; msPeriod
0x140009813  call    cs:__imp_SetThreadpoolTimer
0x140009819  mov     byte ptr [rdi+41h], 1
0x14000981d  mov     rbx, [rsp+38h+arg_8]
0x140009822  mov     rbp, [rsp+38h+arg_10]
0x140009827  add     rsp, 20h
0x14000982b  pop     r14
0x14000982d  pop     rdi
0x14000982e  pop     rsi
0x14000982f  retn
```
