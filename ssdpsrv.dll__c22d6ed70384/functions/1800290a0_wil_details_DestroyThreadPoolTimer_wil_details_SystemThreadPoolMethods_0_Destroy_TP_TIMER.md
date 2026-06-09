# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800290a0`
- end: `0x1800290d4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002314c`
- `0x1800231cc`
- `0x1800231e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800290bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800290bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800290cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800290b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800290b1`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x1800290a0  push    rbx
0x1800290a2  sub     rsp, 20h
0x1800290a6  xor     r9d, r9d; msWindowLength
0x1800290a9  xor     r8d, r8d; msPeriod
0x1800290ac  xor     edx, edx; pftDueTime
0x1800290ae  mov     rbx, rcx
0x1800290b1  call    cs:__imp_SetThreadpoolTimer
0x1800290b7  mov     edx, 1; fCancelPendingCallbacks
0x1800290bc  mov     rcx, rbx; pti
0x1800290bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800290c5  mov     rcx, rbx
0x1800290c8  add     rsp, 20h
0x1800290cc  pop     rbx
0x1800290cd  jmp     cs:__imp_CloseThreadpoolTimer
```
