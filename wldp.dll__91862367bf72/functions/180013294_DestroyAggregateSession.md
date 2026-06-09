# DestroyAggregateSession

- ea: `0x180013294`
- end: `0x1800132ff`
- name: `DestroyAggregateSession`
- size: `107`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f90`
- `0x18001c620`

## callees

- `0x180013294`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800132f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800132f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800132e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800132e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800132b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800132b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800132d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800132d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800132c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800132c7`

## pseudocode

```c
void __fastcall DestroyAggregateSession(LPVOID lpMem)
{
  struct _TP_TIMER *v2; // rcx
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    v2 = (struct _TP_TIMER *)*((_QWORD *)lpMem + 43);
    if ( v2 )
    {
      SetThreadpoolTimer(v2, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)lpMem + 43), 1);
      CloseThreadpoolTimer(*((PTP_TIMER *)lpMem + 43));
      *((_QWORD *)lpMem + 43) = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180013294  test    rcx, rcx
0x180013297  jz      short locret_1800132FE
0x180013299  push    rbx
0x18001329a  sub     rsp, 20h
0x18001329e  mov     rbx, rcx
0x1800132a1  mov     rcx, [rcx+158h]; pti
0x1800132a8  test    rcx, rcx
0x1800132ab  jz      short loc_1800132E5
0x1800132ad  xor     r9d, r9d; msWindowLength
0x1800132b0  xor     r8d, r8d; msPeriod
0x1800132b3  xor     edx, edx; pftDueTime
0x1800132b5  call    cs:__imp_SetThreadpoolTimer
0x1800132bb  mov     rcx, [rbx+158h]; pti
0x1800132c2  mov     edx, 1; fCancelPendingCallbacks
0x1800132c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800132cd  mov     rcx, [rbx+158h]; pti
0x1800132d4  call    cs:__imp_CloseThreadpoolTimer
0x1800132da  mov     qword ptr [rbx+158h], 0
0x1800132e5  call    cs:__imp_GetProcessHeap
0x1800132eb  mov     r8, rbx; lpMem
0x1800132ee  xor     edx, edx; dwFlags
0x1800132f0  mov     rcx, rax; hHeap
0x1800132f3  call    cs:__imp_HeapFree
0x1800132f9  add     rsp, 20h
0x1800132fd  pop     rbx
0x1800132fe  retn
```
