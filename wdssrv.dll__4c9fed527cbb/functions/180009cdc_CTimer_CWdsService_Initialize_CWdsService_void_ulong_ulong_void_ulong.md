# CTimer<CWdsService>::Initialize(CWdsService *,void *,ulong,ulong,void *,ulong)

- ea: `0x180009cdc`
- end: `0x180009d9c`
- name: `?Initialize@?$CTimer@VCWdsService@@@@QEAAKPEAVCWdsService@@PEAXKK1K@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x180006f14`
- `0x180009cdc`
- `0x18000e180`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009d43`
- `KERNEL32!GetLastError` at `0x180009d43`
- `KERNEL32!CreateTimerQueueTimer` at `0x180009d33`
- `KERNEL32!CreateTimerQueueTimer` at `0x180009d33`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180009d7d`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180009d7d`

## pseudocode

```c
__int64 __fastcall CTimer<CWdsService>::Initialize(__int64 Parameter, __int64 a2)
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
          CTimer<CWdsService>::_TimerCallback,
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
0x180009cdc  mov     [rsp+arg_0], rbx
0x180009ce1  mov     [rsp+arg_8], rsi
0x180009ce6  push    rdi
0x180009ce7  sub     rsp, 50h
0x180009ceb  mov     rbx, rdx
0x180009cee  mov     rdi, rcx
0x180009cf1  mov     rdx, rcx
0x180009cf4  xor     esi, esi
0x180009cf6  lea     rcx, [rsp+58h+var_18]
0x180009cfb  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180009d00  and     [rdi+10h], rsi
0x180009d04  lea     rcx, [rdi+18h]; phNewTimer
0x180009d08  and     [rdi+30h], rsi
0x180009d0c  lea     r8, ?_TimerCallback@?$CTimer@VCWdsService@@@@SAXPEAXE@Z; Callback
0x180009d13  and     [rdi+28h], esi
0x180009d16  mov     eax, 0FFFFFFFEh
0x180009d1b  mov     [rdi+20h], rbx
0x180009d1f  mov     r9, rdi; Parameter
0x180009d22  lea     ebx, [rsi+1]
0x180009d25  xor     edx, edx; TimerQueue
0x180009d27  mov     [rsp+58h+Flags], ebx; Flags
0x180009d2b  mov     [rsp+58h+Period], eax; Period
0x180009d2f  mov     [rsp+58h+DueTime], eax; DueTime
0x180009d33  call    cs:__imp_CreateTimerQueueTimer
0x180009d3a  nop     dword ptr [rax+rax+00h]
0x180009d3f  test    eax, eax
0x180009d41  jnz     short loc_180009D51
0x180009d43  call    cs:__imp_GetLastError
0x180009d4a  nop     dword ptr [rax+rax+00h]
0x180009d4f  mov     esi, eax
0x180009d51  lea     rcx, [rsp+58h+var_18]
0x180009d56  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x180009d5b  cmp     [rsp+58h+var_10], 0
0x180009d60  jz      short loc_180009D89
0x180009d62  and     [rsp+58h+DueTime], 0
0x180009d67  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180009d6e  mov     r9d, ebx
0x180009d71  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x180009d78  mov     edx, 16Bh
0x180009d7d  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180009d84  nop     dword ptr [rax+rax+00h]
0x180009d89  mov     rbx, [rsp+58h+arg_0]
0x180009d8e  mov     eax, esi
0x180009d90  mov     rsi, [rsp+58h+arg_8]
0x180009d95  add     rsp, 50h
0x180009d99  pop     rdi
0x180009d9a  retn
```
