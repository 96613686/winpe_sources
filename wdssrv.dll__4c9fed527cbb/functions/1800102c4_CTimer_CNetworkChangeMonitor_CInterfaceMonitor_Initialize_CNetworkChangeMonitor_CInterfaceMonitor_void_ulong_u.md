# CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Initialize(CNetworkChangeMonitor<CInterfaceMonitor> *,void *,ulong,ulong,void *,ulong)

- ea: `0x1800102c4`
- end: `0x180010384`
- name: `?Initialize@?$CTimer@V?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@@@QEAAKPEAV?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@PEAXKK1K@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001010c`

## callees

- `0x180006f14`
- `0x18000e180`
- `0x1800102c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001032b`
- `KERNEL32!GetLastError` at `0x18001032b`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001031b`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001031b`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180010365`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180010365`

## pseudocode

```c
__int64 __fastcall CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Initialize(__int64 Parameter, __int64 a2)
{
  DWORD LastError; // esi
  _BYTE v6[8]; // [rsp+40h] [rbp-18h] BYREF
  int v7; // [rsp+48h] [rbp-10h]

  LastError = 0;
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v6, Parameter);
  *(_QWORD *)(Parameter + 16) = 0;
  *(_QWORD *)(Parameter + 48) = 0;
  *(_DWORD *)(Parameter + 40) = 0;
  *(_QWORD *)(Parameter + 32) = a2;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)(Parameter + 24),
          0,
          CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::_TimerCallback,
          (PVOID)Parameter,
          0xFFFFFFFE,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v6);
  if ( v7 )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
  return LastError;
}

```

## disassembly

```asm
0x1800102c4  mov     [rsp+arg_0], rbx
0x1800102c9  mov     [rsp+arg_8], rsi
0x1800102ce  push    rdi
0x1800102cf  sub     rsp, 50h
0x1800102d3  mov     rbx, rdx
0x1800102d6  mov     rdi, rcx
0x1800102d9  mov     rdx, rcx
0x1800102dc  xor     esi, esi
0x1800102de  lea     rcx, [rsp+58h+var_18]
0x1800102e3  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x1800102e8  and     [rdi+10h], rsi
0x1800102ec  lea     rcx, [rdi+18h]; phNewTimer
0x1800102f0  and     [rdi+30h], rsi
0x1800102f4  lea     r8, ?_TimerCallback@?$CTimer@V?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@@@SAXPEAXE@Z; Callback
0x1800102fb  and     [rdi+28h], esi
0x1800102fe  mov     eax, 0FFFFFFFEh
0x180010303  mov     [rdi+20h], rbx
0x180010307  mov     r9, rdi; Parameter
0x18001030a  lea     ebx, [rsi+1]
0x18001030d  xor     edx, edx; TimerQueue
0x18001030f  mov     [rsp+58h+Flags], ebx; Flags
0x180010313  mov     [rsp+58h+Period], eax; Period
0x180010317  mov     [rsp+58h+DueTime], eax; DueTime
0x18001031b  call    cs:__imp_CreateTimerQueueTimer
0x180010322  nop     dword ptr [rax+rax+00h]
0x180010327  test    eax, eax
0x180010329  jnz     short loc_180010339
0x18001032b  call    cs:__imp_GetLastError
0x180010332  nop     dword ptr [rax+rax+00h]
0x180010337  mov     esi, eax
0x180010339  lea     rcx, [rsp+58h+var_18]
0x18001033e  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x180010343  cmp     [rsp+58h+var_10], 0
0x180010348  jz      short loc_180010371
0x18001034a  and     [rsp+58h+DueTime], 0
0x18001034f  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180010356  mov     r9d, ebx
0x180010359  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x180010360  mov     edx, 16Bh
0x180010365  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001036c  nop     dword ptr [rax+rax+00h]
0x180010371  mov     rbx, [rsp+58h+arg_0]
0x180010376  mov     eax, esi
0x180010378  mov     rsi, [rsp+58h+arg_8]
0x18001037d  add     rsp, 50h
0x180010381  pop     rdi
0x180010382  retn
```
