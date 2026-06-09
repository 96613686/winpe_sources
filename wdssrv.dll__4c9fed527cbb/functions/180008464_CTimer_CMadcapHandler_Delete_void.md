# CTimer<CMadcapHandler>::Delete(void)

- ea: `0x180008464`
- end: `0x18000850e`
- name: `?Delete@?$CTimer@VCMadcapHandler@@@@AEAAXXZ`
- size: `170`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007148`
- `0x18000d380`
- `0x18000fd14`
- `0x180015fac`
- `0x1800171d0`

## callees

- `0x180006f14`
- `0x180008464`
- `0x18000e180`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800084b6`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800084b6`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800084f1`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800084f1`

## pseudocode

```c
void __fastcall CTimer<CMadcapHandler>::Delete(__int64 a1)
{
  void *v2; // rsi
  void *v3; // rdi
  _BYTE v4[8]; // [rsp+30h] [rbp-18h] BYREF
  int v5; // [rsp+38h] [rbp-10h]

  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v4, a1);
  v2 = *(void **)(a1 + 16);
  v3 = *(void **)(a1 + 24);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 40), 1);
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v4);
  if ( v3 )
    DeleteTimerQueueTimer(v2, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v4);
  if ( v5 )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
}

```

## disassembly

```asm
0x180008464  mov     [rsp+arg_0], rbx
0x180008469  mov     [rsp+arg_8], rsi
0x18000846e  push    rdi
0x18000846f  sub     rsp, 40h
0x180008473  mov     rbx, rcx
0x180008476  mov     rdx, rcx
0x180008479  lea     rcx, [rsp+48h+var_18]
0x18000847e  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180008483  mov     rsi, [rbx+10h]
0x180008487  lea     rcx, [rsp+48h+var_18]
0x18000848c  mov     rdi, [rbx+18h]
0x180008490  mov     eax, 1
0x180008495  and     qword ptr [rbx+10h], 0
0x18000849a  and     qword ptr [rbx+18h], 0
0x18000849f  xchg    eax, [rbx+28h]
0x1800084a2  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800084a7  test    rdi, rdi
0x1800084aa  jz      short loc_1800084C2
0x1800084ac  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800084b0  mov     rdx, rdi; Timer
0x1800084b3  mov     rcx, rsi; TimerQueue
0x1800084b6  call    cs:__imp_DeleteTimerQueueTimer
0x1800084bd  nop     dword ptr [rax+rax+00h]
0x1800084c2  lea     rcx, [rsp+48h+var_18]
0x1800084c7  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800084cc  cmp     [rsp+48h+var_10], 0
0x1800084d1  jz      short loc_1800084FD
0x1800084d3  and     [rsp+48h+var_28], 0
0x1800084d8  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x1800084df  mov     r9d, 1
0x1800084e5  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x1800084ec  mov     edx, 16Bh
0x1800084f1  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800084f8  nop     dword ptr [rax+rax+00h]
0x1800084fd  mov     rbx, [rsp+48h+arg_0]
0x180008502  mov     rsi, [rsp+48h+arg_8]
0x180008507  add     rsp, 40h
0x18000850b  pop     rdi
0x18000850c  retn
```
