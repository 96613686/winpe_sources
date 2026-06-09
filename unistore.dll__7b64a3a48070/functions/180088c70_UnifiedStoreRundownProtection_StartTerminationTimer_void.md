# UnifiedStoreRundownProtection::StartTerminationTimer(void)

- ea: `0x180088c70`
- end: `0x180088d37`
- name: `?StartTerminationTimer@UnifiedStoreRundownProtection@@UEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800068f0`
- `0x180088c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088cca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088cca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c97`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180088cef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180088d0f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180088cef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180088d0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180088d26`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180088d26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180088d1d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180088d1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180088c89`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180088c89`

## string_xrefs

- `0x180088cb2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`

## pseudocode

```c
__int64 __fastcall UnifiedStoreRundownProtection::StartTerminationTimer(struct _RTL_CRITICAL_SECTION *pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  signed int LastError; // eax
  unsigned int v4; // ebx
  struct _TP_TIMER *DebugInfo; // rdi
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp+10h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer(UnifiedStoreRundownProtection::_TpTerminationTimerCallback, pv, 0);
  if ( ThreadpoolTimer )
  {
    EnterCriticalSection(pv + 2);
    DebugInfo = (struct _TP_TIMER *)pv[3].DebugInfo;
    pv[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)ThreadpoolTimer;
    pftDueTime = (struct _FILETIME)-1200000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    LeaveCriticalSection(pv + 2);
    if ( DebugInfo )
    {
      SetThreadpoolTimer(DebugInfo, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(DebugInfo, 1);
      CloseThreadpoolTimer(DebugInfo);
    }
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    Log_UnistoreHREvent_0(
      v4,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
      682);
    return v4;
  }
}

```

## disassembly

```asm
0x180088c70  push    rbx
0x180088c72  push    rbp
0x180088c73  push    rsi
0x180088c74  push    rdi
0x180088c75  sub     rsp, 38h
0x180088c79  mov     rsi, rcx
0x180088c7c  mov     rdx, rcx; pv
0x180088c7f  lea     rcx, ?_TpTerminationTimerCallback@UnifiedStoreRundownProtection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180088c86  xor     r8d, r8d; pcbe
0x180088c89  call    cs:__imp_CreateThreadpoolTimer
0x180088c8f  mov     rbp, rax
0x180088c92  test    rax, rax
0x180088c95  jnz     short loc_180088CC6
0x180088c97  call    cs:__imp_GetLastError
0x180088c9d  mov     ebx, eax
0x180088c9f  test    eax, eax
0x180088ca1  jle     short loc_180088CAC
0x180088ca3  movzx   ebx, ax
0x180088ca6  or      ebx, 80070000h
0x180088cac  mov     r9d, 2AAh
0x180088cb2  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180088cb9  xor     edx, edx
0x180088cbb  mov     ecx, ebx
0x180088cbd  call    Log_UnistoreHREvent_0
0x180088cc2  mov     eax, ebx
0x180088cc4  jmp     short loc_180088D2E
0x180088cc6  lea     rcx, [rsi+50h]; lpCriticalSection
0x180088cca  call    cs:__imp_EnterCriticalSection
0x180088cd0  mov     rdi, [rsi+78h]
0x180088cd4  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180088cd9  xor     r9d, r9d; msWindowLength
0x180088cdc  mov     [rsi+78h], rbp
0x180088ce0  xor     r8d, r8d; msPeriod
0x180088ce3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x180088cec  mov     rcx, rbp; pti
0x180088cef  call    cs:__imp_SetThreadpoolTimer
0x180088cf5  lea     rcx, [rsi+50h]; lpCriticalSection
0x180088cf9  call    cs:__imp_LeaveCriticalSection
0x180088cff  test    rdi, rdi
0x180088d02  jz      short loc_180088D2C
0x180088d04  xor     r9d, r9d; msWindowLength
0x180088d07  xor     r8d, r8d; msPeriod
0x180088d0a  xor     edx, edx; pftDueTime
0x180088d0c  mov     rcx, rdi; pti
0x180088d0f  call    cs:__imp_SetThreadpoolTimer
0x180088d15  mov     edx, 1; fCancelPendingCallbacks
0x180088d1a  mov     rcx, rdi; pti
0x180088d1d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180088d23  mov     rcx, rdi; pti
0x180088d26  call    cs:__imp_CloseThreadpoolTimer
0x180088d2c  xor     eax, eax
0x180088d2e  add     rsp, 38h
0x180088d32  pop     rdi
0x180088d33  pop     rsi
0x180088d34  pop     rbp
0x180088d35  pop     rbx
0x180088d36  retn
```
