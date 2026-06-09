# CTimer<CWdsService>::_TimerCallback(void *,uchar)

- ea: `0x18000eb30`
- end: `0x18000ebb6`
- name: `?_TimerCallback@?$CTimer@VCWdsService@@@@SAXPEAXE@Z`
- size: `134`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006f14`
- `0x18000ac40`
- `0x18000e180`
- `0x18000eb30`

## import_xrefs

- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000eb9e`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000eb9e`

## pseudocode

```c
void __fastcall CTimer<CWdsService>::_TimerCallback(__int64 a1)
{
  BOOL v2; // ebx
  _BYTE v3[8]; // [rsp+30h] [rbp-18h] BYREF
  int v4; // [rsp+38h] [rbp-10h]

  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v3, a1);
  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0) == 0;
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v3);
  if ( v2 )
    CWdsService::OnTimer(*(CWdsService **)(a1 + 32));
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v3);
  if ( v4 )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
}

```

## disassembly

```asm
0x18000eb30  mov     [rsp+arg_0], rbx
0x18000eb35  push    rdi
0x18000eb36  sub     rsp, 40h
0x18000eb3a  mov     rdi, rcx
0x18000eb3d  mov     rdx, rcx
0x18000eb40  lea     rcx, [rsp+48h+var_18]
0x18000eb45  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x18000eb4a  xor     eax, eax
0x18000eb4c  lock xadd [rdi+28h], eax
0x18000eb51  xor     ebx, ebx
0x18000eb53  lea     rcx, [rsp+48h+var_18]
0x18000eb58  test    eax, eax
0x18000eb5a  setz    bl
0x18000eb5d  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000eb62  test    ebx, ebx
0x18000eb64  jz      short loc_18000EB6F
0x18000eb66  mov     rcx, [rdi+20h]; this
0x18000eb6a  call    ?OnTimer@CWdsService@@QEAAXPEAV?$CTimer@VCWdsService@@@@@Z; CWdsService::OnTimer(CTimer<CWdsService> *)
0x18000eb6f  lea     rcx, [rsp+48h+var_18]
0x18000eb74  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000eb79  cmp     [rsp+48h+var_10], 0
0x18000eb7e  jz      short loc_18000EBAA
0x18000eb80  and     [rsp+48h+var_28], 0
0x18000eb85  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x18000eb8c  mov     r9d, 1
0x18000eb92  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x18000eb99  mov     edx, 16Bh
0x18000eb9e  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000eba5  nop     dword ptr [rax+rax+00h]
0x18000ebaa  mov     rbx, [rsp+48h+arg_0]
0x18000ebaf  add     rsp, 40h
0x18000ebb3  pop     rdi
0x18000ebb4  retn
```
