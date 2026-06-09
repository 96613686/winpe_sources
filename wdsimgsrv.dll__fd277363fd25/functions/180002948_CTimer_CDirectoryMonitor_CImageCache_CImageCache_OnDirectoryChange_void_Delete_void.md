# CTimer<CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>>::Delete(void)

- ea: `0x180002948`
- end: `0x1800029c1`
- name: `?Delete@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@AEAAXXZ`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800027c8`
- `0x180006bf0`

## callees

- `0x1800025f0`
- `0x18000277c`
- `0x180002948`
- `0x180006da4`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18000299a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000299a`

## pseudocode

```c
__int64 __fastcall CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::Delete(
        __int64 a1)
{
  void *v2; // rsi
  void *v3; // rdi
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v5, a1);
  v2 = *(void **)(a1 + 16);
  v3 = *(void **)(a1 + 24);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 40), 1);
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v5);
  if ( v3 )
    DeleteTimerQueueTimer(v2, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  return CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(v5);
}

```

## disassembly

```asm
0x180002948  mov     [rsp+arg_0], rbx
0x18000294d  mov     [rsp+arg_8], rsi
0x180002952  push    rdi
0x180002953  sub     rsp, 30h
0x180002957  mov     rbx, rcx
0x18000295a  mov     rdx, rcx
0x18000295d  lea     rcx, [rsp+38h+var_18]
0x180002962  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180002967  mov     rsi, [rbx+10h]
0x18000296b  lea     rcx, [rsp+38h+var_18]
0x180002970  mov     rdi, [rbx+18h]
0x180002974  mov     eax, 1
0x180002979  and     qword ptr [rbx+10h], 0
0x18000297e  and     qword ptr [rbx+18h], 0
0x180002983  xchg    eax, [rbx+28h]
0x180002986  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000298b  test    rdi, rdi
0x18000298e  jz      short loc_1800029A6
0x180002990  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180002994  mov     rdx, rdi; Timer
0x180002997  mov     rcx, rsi; TimerQueue
0x18000299a  call    cs:__imp_DeleteTimerQueueTimer
0x1800029a1  nop     dword ptr [rax+rax+00h]
0x1800029a6  lea     rcx, [rsp+38h+var_18]
0x1800029ab  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800029b0  mov     rbx, [rsp+38h+arg_0]
0x1800029b5  mov     rsi, [rsp+38h+arg_8]
0x1800029ba  add     rsp, 30h
0x1800029be  pop     rdi
0x1800029bf  retn
```
