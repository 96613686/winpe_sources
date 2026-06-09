# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000cb38`
- end: `0x18000cc0c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d6fc`

## callees

- `0x18000cb38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbc3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cbaf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cbaf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cb98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cbef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cb98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cbef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cba6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cba6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cb73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cb73`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18000cb38  mov     [rsp+arg_8], rbx
0x18000cb3d  mov     [rsp+arg_10], rbp
0x18000cb42  push    rsi
0x18000cb43  push    rdi
0x18000cb44  push    r14
0x18000cb46  sub     rsp, 20h
0x18000cb4a  cmp     byte ptr [rcx+41h], 0
0x18000cb4e  mov     rdi, rcx
0x18000cb51  jnz     loc_18000CBF9
0x18000cb57  cmp     qword ptr [rcx+30h], 0
0x18000cb5c  jnz     short loc_18000CBC9
0x18000cb5e  call    cs:__imp_GetLastError
0x18000cb64  xor     r8d, r8d; pcbe
0x18000cb67  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cb6e  mov     rdx, rdi; pv
0x18000cb71  mov     ebp, eax
0x18000cb73  call    cs:__imp_CreateThreadpoolTimer
0x18000cb79  mov     rsi, [rdi+30h]
0x18000cb7d  mov     r14, rax
0x18000cb80  test    rsi, rsi
0x18000cb83  jz      short loc_18000CBBD
0x18000cb85  call    cs:__imp_GetLastError
0x18000cb8b  xor     r9d, r9d; msWindowLength
0x18000cb8e  xor     r8d, r8d; msPeriod
0x18000cb91  xor     edx, edx; pftDueTime
0x18000cb93  mov     rcx, rsi; pti
0x18000cb96  mov     ebx, eax
0x18000cb98  call    cs:__imp_SetThreadpoolTimer
0x18000cb9e  mov     edx, 1; fCancelPendingCallbacks
0x18000cba3  mov     rcx, rsi; pti
0x18000cba6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cbac  mov     rcx, rsi; pti
0x18000cbaf  call    cs:__imp_CloseThreadpoolTimer
0x18000cbb5  mov     ecx, ebx; dwErrCode
0x18000cbb7  call    cs:__imp_SetLastError
0x18000cbbd  mov     ecx, ebp; dwErrCode
0x18000cbbf  mov     [rdi+30h], r14
0x18000cbc3  call    cs:__imp_SetLastError
0x18000cbc9  mov     rcx, [rdi+30h]; pti
0x18000cbcd  test    rcx, rcx
0x18000cbd0  jz      short loc_18000CBF9
0x18000cbd2  mov     rax, 0FFFFFFFF4D2FA200h
0x18000cbdc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000cbe1  mov     r9d, 124F8h; msWindowLength
0x18000cbe7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000cbec  xor     r8d, r8d; msPeriod
0x18000cbef  call    cs:__imp_SetThreadpoolTimer
0x18000cbf5  mov     byte ptr [rdi+41h], 1
0x18000cbf9  mov     rbx, [rsp+38h+arg_8]
0x18000cbfe  mov     rbp, [rsp+38h+arg_10]
0x18000cc03  add     rsp, 20h
0x18000cc07  pop     r14
0x18000cc09  pop     rdi
0x18000cc0a  pop     rsi
0x18000cc0b  retn
```
