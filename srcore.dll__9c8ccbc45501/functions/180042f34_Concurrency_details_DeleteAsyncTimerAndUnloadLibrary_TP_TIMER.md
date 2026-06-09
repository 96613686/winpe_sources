# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x180042f34`
- end: `0x180042f68`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180042d10`
- `0x180044fc0`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180042f53`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180042f53`
- `KERNEL32!CloseThreadpoolTimer` at `0x180042f61`
- `KERNEL32!SetThreadpoolTimer` at `0x180042f45`
- `KERNEL32!SetThreadpoolTimer` at `0x180042f45`

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
0x180042f34  push    rbx
0x180042f36  sub     rsp, 20h
0x180042f3a  xor     r9d, r9d; msWindowLength
0x180042f3d  xor     r8d, r8d; msPeriod
0x180042f40  xor     edx, edx; pftDueTime
0x180042f42  mov     rbx, rcx
0x180042f45  call    cs:SetThreadpoolTimer
0x180042f4b  mov     edx, 1; fCancelPendingCallbacks
0x180042f50  mov     rcx, rbx; pti
0x180042f53  call    cs:WaitForThreadpoolTimerCallbacks
0x180042f59  mov     rcx, rbx
0x180042f5c  add     rsp, 20h
0x180042f60  pop     rbx
0x180042f61  jmp     cs:CloseThreadpoolTimer
```
