# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x18001e568`
- end: `0x18001e59c`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001dd74`
- `0x180021540`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e595`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e587`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e587`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e579`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e579`

## pseudocode

```c
void __fastcall Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(PTP_TIMER pti, struct _TP_TIMER *a2)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18001e568  push    rbx
0x18001e56a  sub     rsp, 20h
0x18001e56e  xor     r9d, r9d; msWindowLength
0x18001e571  xor     r8d, r8d; msPeriod
0x18001e574  xor     edx, edx; pftDueTime
0x18001e576  mov     rbx, rcx
0x18001e579  call    cs:SetThreadpoolTimer
0x18001e57f  mov     edx, 1; fCancelPendingCallbacks
0x18001e584  mov     rcx, rbx; pti
0x18001e587  call    cs:WaitForThreadpoolTimerCallbacks
0x18001e58d  mov     rcx, rbx
0x18001e590  add     rsp, 20h
0x18001e594  pop     rbx
0x18001e595  jmp     cs:CloseThreadpoolTimer
```
