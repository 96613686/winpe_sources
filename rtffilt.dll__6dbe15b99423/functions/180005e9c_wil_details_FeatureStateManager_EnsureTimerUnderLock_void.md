# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005e9c`
- end: `0x180005f70`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008614`

## callees

- `0x180005e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ee9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005efc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005efc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005ed7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005ed7`

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
0x180005e9c  mov     [rsp+arg_8], rbx
0x180005ea1  mov     [rsp+arg_10], rbp
0x180005ea6  push    rsi
0x180005ea7  push    rdi
0x180005ea8  push    r14
0x180005eaa  sub     rsp, 20h
0x180005eae  cmp     byte ptr [rcx+41h], 0
0x180005eb2  mov     rdi, rcx
0x180005eb5  jnz     loc_180005F5D
0x180005ebb  cmp     qword ptr [rcx+30h], 0
0x180005ec0  jnz     short loc_180005F2D
0x180005ec2  call    cs:__imp_GetLastError
0x180005ec8  xor     r8d, r8d; pcbe
0x180005ecb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005ed2  mov     rdx, rdi; pv
0x180005ed5  mov     ebp, eax
0x180005ed7  call    cs:__imp_CreateThreadpoolTimer
0x180005edd  mov     rsi, [rdi+30h]
0x180005ee1  mov     r14, rax
0x180005ee4  test    rsi, rsi
0x180005ee7  jz      short loc_180005F21
0x180005ee9  call    cs:__imp_GetLastError
0x180005eef  xor     r9d, r9d; msWindowLength
0x180005ef2  xor     r8d, r8d; msPeriod
0x180005ef5  xor     edx, edx; pftDueTime
0x180005ef7  mov     rcx, rsi; pti
0x180005efa  mov     ebx, eax
0x180005efc  call    cs:__imp_SetThreadpoolTimer
0x180005f02  mov     edx, 1; fCancelPendingCallbacks
0x180005f07  mov     rcx, rsi; pti
0x180005f0a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005f10  mov     rcx, rsi; pti
0x180005f13  call    cs:__imp_CloseThreadpoolTimer
0x180005f19  mov     ecx, ebx; dwErrCode
0x180005f1b  call    cs:__imp_SetLastError
0x180005f21  mov     ecx, ebp; dwErrCode
0x180005f23  mov     [rdi+30h], r14
0x180005f27  call    cs:__imp_SetLastError
0x180005f2d  mov     rcx, [rdi+30h]; pti
0x180005f31  test    rcx, rcx
0x180005f34  jz      short loc_180005F5D
0x180005f36  mov     rax, 0FFFFFFFF4D2FA200h
0x180005f40  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005f45  mov     r9d, 124F8h; msWindowLength
0x180005f4b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005f50  xor     r8d, r8d; msPeriod
0x180005f53  call    cs:__imp_SetThreadpoolTimer
0x180005f59  mov     byte ptr [rdi+41h], 1
0x180005f5d  mov     rbx, [rsp+38h+arg_8]
0x180005f62  mov     rbp, [rsp+38h+arg_10]
0x180005f67  add     rsp, 20h
0x180005f6b  pop     r14
0x180005f6d  pop     rdi
0x180005f6e  pop     rsi
0x180005f6f  retn
```
