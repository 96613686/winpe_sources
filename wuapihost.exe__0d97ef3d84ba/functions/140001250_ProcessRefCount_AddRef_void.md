# ProcessRefCount::AddRef(void)

- ea: `0x140001250`
- end: `0x14000129f`
- name: `?AddRef@ProcessRefCount@@UEAAKXZ`
- size: `79`
- prototype: `unsigned int __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001250`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140001278`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140001278`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x140001262`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x140001262`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140001287`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140001287`

## pseudocode

```c
__int64 __fastcall ProcessRefCount::AddRef(ProcessRefCount *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  if ( v2 && IsThreadpoolTimerSet(v2) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 3), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x140001250  push    rbx
0x140001252  sub     rsp, 20h
0x140001256  mov     rbx, rcx
0x140001259  mov     rcx, [rcx+18h]; pti
0x14000125d  test    rcx, rcx
0x140001260  jz      short loc_14000128D
0x140001262  call    cs:__imp_IsThreadpoolTimerSet
0x140001268  test    eax, eax
0x14000126a  jz      short loc_14000128D
0x14000126c  mov     rcx, [rbx+18h]; pti
0x140001270  xor     r9d, r9d; msWindowLength
0x140001273  xor     r8d, r8d; msPeriod
0x140001276  xor     edx, edx; pftDueTime
0x140001278  call    cs:__imp_SetThreadpoolTimer
0x14000127e  mov     rcx, [rbx+18h]; pti
0x140001282  mov     edx, 1; fCancelPendingCallbacks
0x140001287  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000128d  mov     eax, 1
0x140001292  lock xadd [rbx+8], eax
0x140001297  inc     eax
0x140001299  add     rsp, 20h
0x14000129d  pop     rbx
0x14000129e  retn
```
