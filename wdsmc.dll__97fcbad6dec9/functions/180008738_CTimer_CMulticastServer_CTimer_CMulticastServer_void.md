# CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)

- ea: `0x180008738`
- end: `0x180008814`
- name: `??1?$CTimer@VCMulticastServer@@@@QEAA@XZ`
- size: `220`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009130`
- `0x18000c6c0`
- `0x18000d978`
- `0x18000e2a0`
- `0x18000f130`
- `0x180011220`
- `0x18001198c`
- `0x180011bbc`
- `0x1800147e4`
- `0x1800150c0`
- `0x180017254`
- `0x18001a83c`

## callees

- `0x180008738`
- `0x180008d38`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800087ef`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800087ef`
- `KERNEL32!GetCurrentThreadId` at `0x180008763`
- `KERNEL32!GetCurrentThreadId` at `0x1800087a4`
- `KERNEL32!GetCurrentThreadId` at `0x180008763`
- `KERNEL32!GetCurrentThreadId` at `0x1800087a4`
- `KERNEL32!SwitchToThread` at `0x18000877e`
- `KERNEL32!SwitchToThread` at `0x18000877e`

## string_xrefs

- `0x1800087b9`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
__int64 __fastcall CTimer<CMulticastServer>::~CTimer<CMulticastServer>(__int64 a1)
{
  int v2; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v4; // eax
  void *v5; // rbp
  void *v6; // rdi
  DWORD v7; // eax
  int v8; // r9d
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  int v11; // [rsp+38h] [rbp-10h]

  v11 = 0;
  v10 = a1;
  while ( 1 )
  {
    v2 = 0;
    if ( *(_DWORD *)(a1 + 8) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)a1, CurrentThreadId, 0);
    if ( !v4 || v4 == CurrentThreadId )
      break;
    if ( (unsigned int)++v2 >= *(_DWORD *)(a1 + 8) )
      goto LABEL_6;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 4), 1u);
  v5 = *(void **)(a1 + 16);
  v6 = *(void **)(a1 + 24);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 40), 1);
  v11 = 0;
  v7 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0) != v7 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v8,
      0);
  if ( !_InterlockedDecrement((volatile signed __int32 *)(a1 + 4)) )
    _InterlockedExchange((volatile __int32 *)a1, 0);
  if ( v6 )
    DeleteTimerQueueTimer(v5, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  return CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v10);
}

```

## disassembly

```asm
0x180008738  mov     rax, rsp
0x18000873b  mov     [rax+8], rbx
0x18000873f  mov     [rax+10h], rbp
0x180008743  mov     [rax+18h], rsi
0x180008747  push    rdi
0x180008748  sub     rsp, 40h
0x18000874c  and     dword ptr [rax-10h], 0
0x180008750  mov     rbx, rcx
0x180008753  mov     [rax-18h], rcx
0x180008757  mov     esi, 1
0x18000875c  xor     edi, edi
0x18000875e  cmp     [rbx+8], edi
0x180008761  jbe     short loc_18000877E
0x180008763  call    cs:__imp_GetCurrentThreadId
0x180008769  mov     ecx, eax
0x18000876b  xor     eax, eax
0x18000876d  lock cmpxchg [rbx], ecx
0x180008771  jz      short loc_180008786
0x180008773  cmp     eax, ecx
0x180008775  jz      short loc_180008786
0x180008777  add     edi, esi
0x180008779  cmp     edi, [rbx+8]
0x18000877c  jb      short loc_180008763
0x18000877e  call    cs:__imp_SwitchToThread
0x180008784  jmp     short loc_18000875C
0x180008786  lock add [rbx+4], esi
0x18000878a  mov     rbp, [rbx+10h]
0x18000878e  mov     rdi, [rbx+18h]
0x180008792  and     qword ptr [rbx+10h], 0
0x180008797  and     qword ptr [rbx+18h], 0
0x18000879c  xchg    esi, [rbx+28h]
0x18000879f  and     [rsp+48h+var_10], 0
0x1800087a4  call    cs:__imp_GetCurrentThreadId
0x1800087aa  xor     ecx, ecx
0x1800087ac  lock xadd [rbx], ecx
0x1800087b0  cmp     ecx, eax
0x1800087b2  jz      short loc_1800087D1
0x1800087b4  and     [rsp+48h+var_28], 0
0x1800087b9  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x1800087c0  mov     edx, 99h; unsigned int
0x1800087c5  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x1800087cc  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800087d1  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800087d5  mov     eax, r8d
0x1800087d8  lock xadd [rbx+4], eax
0x1800087dd  add     eax, r8d
0x1800087e0  jnz     short loc_1800087E4
0x1800087e2  xchg    eax, [rbx]
0x1800087e4  test    rdi, rdi
0x1800087e7  jz      short loc_1800087F5
0x1800087e9  mov     rdx, rdi; Timer
0x1800087ec  mov     rcx, rbp; TimerQueue
0x1800087ef  call    cs:__imp_DeleteTimerQueueTimer
0x1800087f5  lea     rcx, [rsp+48h+var_18]
0x1800087fa  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800087ff  mov     rbx, [rsp+48h+arg_0]
0x180008804  mov     rbp, [rsp+48h+arg_8]
0x180008809  mov     rsi, [rsp+48h+arg_10]
0x18000880e  add     rsp, 40h
0x180008812  pop     rdi
0x180008813  retn
```
