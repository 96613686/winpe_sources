# CTimer<CMadcapHandler>::Initialize(CMadcapHandler *,void *,ulong,ulong,void *,ulong)

- ea: `0x18001687c`
- end: `0x18001693f`
- name: `?Initialize@?$CTimer@VCMadcapHandler@@@@QEAAKPEAVCMadcapHandler@@PEAXKK1K@Z`
- size: `195`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016948`

## callees

- `0x180006f14`
- `0x18000e180`
- `0x18001687c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800168e6`
- `KERNEL32!GetLastError` at `0x1800168e6`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800168d6`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800168d6`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180016920`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180016920`

## pseudocode

```c
__int64 __fastcall CTimer<CMadcapHandler>::Initialize(__int64 Parameter, __int64 a2)
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
          CTimer<CMadcapHandler>::_TimerCallback,
          (PVOID)Parameter,
          0xDBBA0u,
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
0x18001687c  mov     [rsp+arg_0], rbx
0x180016881  mov     [rsp+arg_8], rsi
0x180016886  push    rdi
0x180016887  sub     rsp, 50h
0x18001688b  mov     rbx, rdx
0x18001688e  mov     rdi, rcx
0x180016891  mov     rdx, rcx
0x180016894  xor     esi, esi
0x180016896  lea     rcx, [rsp+58h+var_18]
0x18001689b  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x1800168a0  and     [rdi+10h], rsi
0x1800168a4  lea     rcx, [rdi+18h]; phNewTimer
0x1800168a8  and     [rdi+30h], rsi
0x1800168ac  lea     r8, ?_TimerCallback@?$CTimer@VCMadcapHandler@@@@SAXPEAXE@Z; Callback
0x1800168b3  and     [rdi+28h], esi
0x1800168b6  mov     r9, rdi; Parameter
0x1800168b9  mov     [rdi+20h], rbx
0x1800168bd  xor     edx, edx; TimerQueue
0x1800168bf  lea     ebx, [rsi+1]
0x1800168c2  mov     [rsp+58h+Flags], ebx; Flags
0x1800168c6  mov     [rsp+58h+Period], 0FFFFFFFEh; Period
0x1800168ce  mov     [rsp+58h+DueTime], 0DBBA0h; DueTime
0x1800168d6  call    cs:__imp_CreateTimerQueueTimer
0x1800168dd  nop     dword ptr [rax+rax+00h]
0x1800168e2  test    eax, eax
0x1800168e4  jnz     short loc_1800168F4
0x1800168e6  call    cs:__imp_GetLastError
0x1800168ed  nop     dword ptr [rax+rax+00h]
0x1800168f2  mov     esi, eax
0x1800168f4  lea     rcx, [rsp+58h+var_18]
0x1800168f9  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800168fe  cmp     [rsp+58h+var_10], 0
0x180016903  jz      short loc_18001692C
0x180016905  and     [rsp+58h+DueTime], 0
0x18001690a  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180016911  mov     r9d, ebx
0x180016914  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x18001691b  mov     edx, 16Bh
0x180016920  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180016927  nop     dword ptr [rax+rax+00h]
0x18001692c  mov     rbx, [rsp+58h+arg_0]
0x180016931  mov     eax, esi
0x180016933  mov     rsi, [rsp+58h+arg_8]
0x180016938  add     rsp, 50h
0x18001693c  pop     rdi
0x18001693d  retn
```
