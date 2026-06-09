# CVirtualFileCache::Item::WaitForTimer(ATL::CComCritSecLock<ATL::CComAutoCriticalSection> *,_TP_TIMER *)

- ea: `0x18006a5d0`
- end: `0x18006a63b`
- name: `?WaitForTimer@Item@CVirtualFileCache@@KAHPEAV?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@PEAU_TP_TIMER@@@Z`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800338f0`
- `0x180069974`

## callees

- `0x180060294`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18006a600`
- `KERNEL32!LeaveCriticalSection` at `0x18006a600`
- `KERNEL32!SetThreadpoolTimerEx` at `0x18006a5f0`
- `KERNEL32!SetThreadpoolTimerEx` at `0x18006a5f0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18006a612`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18006a612`
- `KERNEL32!CloseThreadpoolTimer` at `0x18006a623`
- `KERNEL32!CloseThreadpoolTimer` at `0x18006a623`

## pseudocode

```c
_BOOL8 __fastcall CVirtualFileCache::Item::WaitForTimer(__int64 a1, struct _TP_TIMER *a2)
{
  BOOL v4; // ebx

  v4 = !SetThreadpoolTimerEx(a2, 0, 0, 0);
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
  *(_BYTE *)(a1 + 8) = 0;
  WaitForThreadpoolTimerCallbacks(a2, 1);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(a1);
  CloseThreadpoolTimer(a2);
  return v4;
}

```

## disassembly

```asm
0x18006a5d0  mov     [rsp+arg_0], rbx
0x18006a5d5  mov     [rsp+arg_8], rsi
0x18006a5da  push    rdi
0x18006a5db  sub     rsp, 20h
0x18006a5df  mov     rsi, rdx
0x18006a5e2  mov     rdi, rcx
0x18006a5e5  mov     rcx, rsi; pti
0x18006a5e8  xor     r9d, r9d; msWindowLength
0x18006a5eb  xor     r8d, r8d; msPeriod
0x18006a5ee  xor     edx, edx; pftDueTime
0x18006a5f0  call    cs:__imp_SetThreadpoolTimerEx
0x18006a5f6  mov     rcx, [rdi]; lpCriticalSection
0x18006a5f9  xor     ebx, ebx
0x18006a5fb  test    eax, eax
0x18006a5fd  setz    bl
0x18006a600  call    cs:__imp_LeaveCriticalSection
0x18006a606  mov     edx, 1; fCancelPendingCallbacks
0x18006a60b  mov     byte ptr [rdi+8], 0
0x18006a60f  mov     rcx, rsi; pti
0x18006a612  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006a618  mov     rcx, rdi
0x18006a61b  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18006a620  mov     rcx, rsi; pti
0x18006a623  call    cs:__imp_CloseThreadpoolTimer
0x18006a629  mov     rsi, [rsp+28h+arg_8]
0x18006a62e  mov     eax, ebx
0x18006a630  mov     rbx, [rsp+28h+arg_0]
0x18006a635  add     rsp, 20h
0x18006a639  pop     rdi
0x18006a63a  retn
```
